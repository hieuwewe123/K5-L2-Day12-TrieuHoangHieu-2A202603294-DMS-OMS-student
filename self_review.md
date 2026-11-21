# Tự đánh giá — Triệu Hoàng Hiếu · G01

## 1. Rà soát 4 khung

| Ảnh | Đối tượng | Loại lỗi | Ghi chú | Đã sửa? |
|---|---|---|---|---|
| S01_rgb | child_seat rear_left | guess | Lòng ghế tối nhưng bản cũ ghi no; đọc riêng RGB thay vì suy từ IR | Có: occupied=unknown |
| S03_ir | object rear_middle | wrong_class | Vật phẳng chưa đủ đặc trưng túi | Có: type=other |
| D01 | person | guess | Vùng ngực tối, not_worn quá chắc | Có: seatbelt=unknown |
| D05 | face | guess | NIR chưa đủ chắc loại tròng | Có: glasses=unknown |

## 2. Lỗi lặp lại và cách tránh

Lỗi: gán thuộc tính quá chắc khi vùng ảnh tối hoặc bị che; ban đầu box tay cũng ăn vào cẳng tay.

Nguyên nhân: xem toàn ảnh rồi suy theo ngữ cảnh/cặp RGB–IR thay vì kiểm bằng chứng ngay trong từng ảnh.

Cách tránh: đọc riêng từng mắt/từng ảnh, dùng unknown hoặc other khi chưa chắc; box tay từ đầu ngón đến cổ tay. Đã thu lại 3 box tay D03/D04/D05 trước lượt review và sửa 6 thuộc tính sau review.

## 3. Bài học từ review

Khi review bản Dũng, D01 seatbelt=unknown và S03 object.type=other thận trọng hơn bản ban đầu. Đã áp dụng các sửa đổi phù hợp cho bản mình. Log Quốc Anh gửi có 5 dòng ưu tiên cách gán của Hiếu và 93 ambiguous; đã ghi phản hồi từng dòng, không xem ambiguous là lỗi tự động.

## 4. Xử lý bổ sung

Sinh viên xác nhận vùng sát biên trái D01 là bàn tay phải; đã thêm hand, side=right, on_wheel=unknown. S02/S04 đã kiểm có box face ở cả RGB và IR. OMS không cần face13. Chi tiết phiên bản ở REWORK.md.
