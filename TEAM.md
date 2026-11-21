# TEAM — Ngày 12

Mã bộ ảnh: **G01** · Nhóm 3 người · Review vòng tròn

| Họ tên | MSSV | Đã có đủ 22 ảnh? | Review cho | Được review bởi | Bằng chứng |
|---|---|---|---|---|---|
| Triệu Hoàng Hiếu | 2A202603294 | Có | Hà Huy Dũng | Dương Quốc Anh | Log chấm Dũng 52 dòng; log nhận từ Quốc Anh 98 dòng, đã ghi phản hồi |
| Hà Huy Dũng | 2A202603271 | Export nhận được đủ 22 ảnh | Dương Quốc Anh | Triệu Hoàng Hiếu | Đã nhận bài để Hiếu review; chưa xác nhận Dũng sửa xong |
| Dương Quốc Anh | 2A202603286 | Export nhận được đủ 22 ảnh | Triệu Hoàng Hiếu | Hà Huy Dũng | Đã gửi log review Hiếu; chưa xác nhận phần Dũng review Quốc Anh |

Vòng: **Quốc Anh → Hiếu → Dũng → Quốc Anh**, mũi tên từ người chấm đến người được chấm.

## Cá nhân — Triệu Hoàng Hiếu

- Hoàn thành bản nhãn 22 ảnh; kiểm cấu trúc, review bài Dũng và xử lý log Quốc Anh gửi. Đã sửa 6 thuộc tính trên bản mình sau rà soát.
- Bài học: khác biệt không đồng nghĩa có lỗi; cần căn cứ từng ảnh và mục guideline, không suy thuộc tính từ cặp RGB/IR.
- Sinh viên xác nhận vùng sát mép trái D01 là hand; đã bổ sung tay phải, on_wheel=unknown. Không ghi là coach đã duyệt.

## Hướng dẫn cập nhật

Child_seat.occupied có unknown/no/yes theo labels_cabin_v1.json mới. S03/S05 có trẻ dùng yes. Infant_seat không có occupied; giữ seat/facing, không tự thêm nhãn cho trẻ ngoài phạm vi hướng dẫn.

## Xác nhận hoàn tất review

Sinh viên xác nhận đã rà trực quan bản cuối, gửi lại export_final_v2.zip cho Quốc Anh, trao đổi các quyết định giữ/sửa và gửi gói nhận xét cho Dũng. Giữ nguyên log gốc để thể hiện quá trình trước sửa; các phản hồi xử lý nằm trong disagreement_log.csv và REWORK.md.
