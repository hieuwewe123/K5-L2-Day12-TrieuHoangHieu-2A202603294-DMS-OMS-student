# Xử lý sau review — G01

Bản được Quốc Anh review: export_reviewed_by_QuocAnh.zip (bản v2 trước đợt sửa này). Bản mới nhất sau sửa: export_final_v2.zip.

## Nhãn đã sửa trực tiếp trên CVAT

| Khung | Thuộc tính | Trước | Sau | Căn cứ |
|---|---|---|---|---|
| D01 | person.seatbelt | not_worn | unknown | GUIDE 4.4-1, 4.7: thân tối, không khẳng định không có dây |
| D05 | face.glasses | clear | unknown | GUIDE 4.5: chưa đủ chắc loại tròng trên NIR |
| S01_rgb | child_seat.occupied | no | unknown | GUIDE 4.4-1, 4.8: đọc riêng RGB tối, không suy từ IR |
| S03_rgb | object.type, ghế giữa | bag | other | GUIDE 4.8: vật phẳng chưa đủ đặc trưng túi |
| S03_ir | object.type, ghế giữa | bag | other | GUIDE 4.8: không khẳng định loại khi hình dạng chưa chắc |
| S06_rgb | object.type | bag | other | GUIDE 4.4-1, 4.8: RGB tối; S06_ir vẫn bag |

Giữ 6 box child_seat có trẻ ở S03/S05 là occupied=yes theo schema cập nhật. Không đổi schema infant_seat.

## Đọc log

- review_QuocAnh_cho_Hieu.csv giữ nguyên file reviewer gửi: mine=Quốc Anh, peer=Hiếu, 5 peer và 93 ambiguous.
- disagreement_log.csv giữ nguyên 9 cột reviewer và thêm response_Hieu/resolution_status. Các cột bổ sung là quyết định xử lý bản Hiếu, không đổi thành kết luận chung của nhóm.
- disagreement_HaHuyDung.csv là lượt Hiếu review Dũng, mine=Hiếu, peer=Dũng, không trộn với log nhận về.
- Các dòng đã sửa ở S03 object.type là kết quả rà soát cả lượt review Dũng, không phải kết luận trực tiếp trong log nhận về của Quốc Anh.

## Bổ sung tay phải D01

Sinh viên xác nhận vùng sát mép trái là hand. Đã thêm box x=0..179,y=320..660, whose=driver, side=right. On_wheel=unknown vì không thấy chắc điểm tiếp xúc vô lăng. Đây là xác nhận của sinh viên, không ghi thành coach đã duyệt.

S02/S04 trên cả RGB và IR đều có face. OMS chỉ yêu cầu box face, không gán face13.

File gốc Quốc Anh giữ nguyên; phản hồi riêng của Hiếu đã cập nhật, không thay verdict của reviewer.

Ghi nhận khi đối chiếu XML: box child_seat rear_left ở S03_rgb trong CVAT hiện có cạnh phải x=851,50 thay vì x=845,00 ở bản Quốc Anh đã review. Giữ cạnh mới theo nhãn hiện có trong CVAT; các cạnh còn lại giữ nguyên. Ngoài thay đổi hình học này, khác biệt thuộc tính so bản đã review là 6 mục nêu trong REWORK.md.

## Xác nhận sau cùng

Sinh viên xác nhận đã rà trực quan, gửi lại bản mới nhất cho Quốc Anh, trao đổi xong các quyết định giữ/sửa và gửi nhận xét cho Dũng. Các verdict reviewer trong file gốc vẫn giữ nguyên như lúc nhận để truy vết.
