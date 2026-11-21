# Danh sách lớp v0 — Triệu Hoàng Hiếu · G01

Danh sách dựa trên Guideline Cabin v1.0 và ảnh G01. Các lớp/thuộc tính dưới đây là đầu ra cần nhận biết; bài lab không yêu cầu tự bổ sung nhãn vào schema CVAT.

## DMS

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng DMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | person / seat | driver | Xác định người lái để liên kết mặt và hoạt động của họ | Có khi thấy cơ thể; bị che có thể khó xác định |
| 2 | eye_left / eye_right | open / closed / unknown | Theo dõi trạng thái từng mắt; cần chuỗi thời gian để đánh giá nhắm mắt kéo dài | Có khi thấy mí; phản xạ hoặc che khuất có thể làm mất thông tin |
| 3 | glasses | none / clear / sun / unknown | Nhận biết kính để xét khả năng quan sát mắt | Có thể khó phân biệt loại kính trên NIR; không chắc chọn unknown |
| 4 | gaze_zone | road / mirror_l / mirror_r / mirror_c / cluster / center / lap / other | Nhận biết vùng nhìn để theo dõi sự chú ý tới đường | Dựa vào mắt và đầu nếu đủ rõ; không chắc chọn other và ghi lý do |
| 5 | face13 | 13 điểm, cờ occluded / outside | Biểu diễn hình học khuôn mặt cho phân tích mắt và tư thế đầu | Có khi đủ rõ; điểm bị che cần cờ; mặt dưới 60 px không gán |
| 6 | hand / on_wheel | yes / no / unknown | Theo dõi tay có tiếp xúc vô lăng trong khung hình hay không | Có khi tay và vô lăng nhìn thấy rõ |
| 7 | phone / state | held / mounted / lap | Nhận biết điện thoại và trạng thái sử dụng | Có thể nhận bằng cạnh, góc, màn hình; không suy từ tư thế tay |
| 8 | person / seatbelt | worn_correct / worn_incorrect / not_worn / unknown | Kiểm tra trạng thái thắt dây của người lái | Có nếu thấy dải dây; tối hoặc bị che chọn unknown |

## OMS

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng OMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | person | Có box khi thấy người | Xác định người hiện diện trong cabin | Có qua hình dạng phần cơ thể thấy được |
| 2 | seat | driver / front_passenger / rear_left / rear_middle / rear_right | Gắn người hoặc vật với vị trí ghế theo xe | Có thể suy vị trí từ bố cục cabin; phải tuân theo hướng camera |
| 3 | child_seat / occupied | no / unknown / yes | Phân biệt ghế trẻ em trống và trường hợp không quan sát được bên trong | Dựa vào hình dạng; bị phủ thì occupied=unknown; schema cập nhật có yes khi ghế có trẻ |
| 4 | infant_seat / facing | rear / front | Nhận biết nôi/ghế em bé và hướng đặt | Có nếu hình dạng, hướng ghế đủ rõ |
| 5 | object / type | bag / box / cup / other | Phân biệt đồ vật mang theo với người và ghế trẻ em | Dựa vào hình dạng, không suy từ màu; không chắc chọn other |
| 6 | person / seatbelt | worn_correct / worn_incorrect / not_worn / unknown | Kiểm tra dây an toàn theo người ngồi | Phụ thuộc độ rõ của dây; riêng SVIRO chỉ not_worn hoặc unknown |
| 7 | face | Box khuôn mặt nếu nhìn thấy | Định vị mặt người trong cabin để phục vụ bước phân tích tiếp theo | Có nếu thấy mặt; OMS lab chỉ vẽ box, không vẽ face13 |

## 2 câu hỏi leo thang từ dữ liệu G01

1. **Trẻ em trong child_seat được biểu diễn thế nào?** GUIDE §3 nói không có trẻ em ngồi và yêu cầu báo coach nếu gặp, nhưng S03_rgb và S05_ir có trẻ trong ghế. Có cần thêm person cho trẻ không, và có cần liên kết person với ghế khi schema mới đã có occupied=yes?
   - Khung ví dụ: G01 S03_rgb, rear_left; S05_ir, cả hai ghế bên.
   - Xử lý sau hướng dẫn bổ sung do sinh viên truyền đạt: gán child_seat.occupied=yes theo labels_cabin_v1.json cập nhật; không tự thêm person/face cho trẻ. Câu hỏi còn lại là có mở rộng person/face cho trẻ trong phiên bản guideline sau hay không.
2. **Ghế em bé đang có em bé có nằm ngoài phạm vi lab hay cần nhãn bổ sung?** GUIDE §4.1 và §4.8 chỉ mô tả ghế em bé trống, infant_seat không có thuộc tính occupied. Khi có em bé, cần hai box hay đổi schema?
   - Khung ví dụ: G01 S02_rgb, rear_right; S07_ir, rear_middle; S08_rgb, rear_right.
   - Xử lý: gán infant_seat với seat/facing theo schema hiện có, không thêm occupied vì schema không có trường này. Không gán em bé thành object. Câu hỏi về thuộc tính occupancy cho infant_seat còn phù hợp cho phiên bản guideline tiếp theo.
