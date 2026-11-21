# Khai báo dùng AI — Triệu Hoàng Hiếu

| # | Công cụ | Yêu cầu | Sử dụng kết quả | Đã kiểm bằng gì? |
|---|---|---|---|---|
| 1 | Codex | Giải thích đề và cách nhóm review | Checklist E1–E5, vòng Quốc Anh → Hiếu → Dũng → Quốc Anh | Đối chiếu GUIDE, RULES, CHECKPOINTS, SUBMISSION |
| 2 | Codex | Chuẩn bị G01 và CVAT | Giải nén G01; tạo project/task 22 ảnh và schema 9 nhãn | Metadata CVAT, danh sách ảnh, gitignore |
| 3 | Codex | Hỗ trợ gán nhãn toàn bộ | Xem ảnh, tạo box/thuộc tính/face13 và ghi vào CVAT qua API; chỉnh 3 box tay | Xem lại ảnh/overlay, kiểm cờ và cabin_check |
| 4 | Codex | Cập nhật labels_cabin_v1.json mới | Đồng bộ occupied=yes cho child_seat, sửa 6 box ở S03/S05; cập nhật cabin_schema.py | So JSON cũ/mới, kiểm giá trị trên CVAT và XML export |
| 5 | Codex | Chuẩn bị báo cáo và exit ticket | Viết danh sách lớp, quan sát IR, bản rà soát, đáp án exit ticket | Đối chiếu guideline và phép tính; chưa có slide 54 để đối chiếu trực tiếp |
| 6 | Codex | Hiếu review Dũng | Kiểm export, 52 dòng diff và nhận xét; giữ ca chưa rõ là ambiguous | Xem lại ảnh liên quan, gắn mục guideline; chưa có xác nhận Dũng sửa xong |
| 7 | Codex | Xử lý log Quốc Anh chấm Hiếu | Giữ file gốc 98 dòng; ghi phản hồi bản Hiếu; sửa 6 thuộc tính sau rà soát | Đối chiếu giá trị XML trước/sau; export thật từ CVAT và cabin_check |
| 8 | Codex | Hoàn thiện bộ nộp | Tổng hợp file và kiểm ZIP không chứa ảnh | Kiểm cấu trúc file, CSV và các export lồng bên trong |

Sinh viên cho biết thầy cho phép dùng AI hỗ trợ toàn bộ bài. AI đã xem ảnh và gán nhãn, không chỉ góp ý câu chữ. File ảnh/overlay không được đưa vào gói nộp. Không tạo lời xác nhận đồng thuận hoặc việc coach duyệt khi chưa có. Sau khi sinh viên xác nhận D01 sát mép trái là hand, đã bổ sung tay phải; không ghi đó là xác nhận của coach.

Bổ sung: kiểm trực tiếp CVAT và XML xác nhận S02/S04 có face trên RGB/IR; D01 thêm hand khiến tổng hand=12. Export v2 mới vẫn 22 ảnh, 0 lỗi/0 cảnh báo.

Hoàn tất hồ sơ: cập nhật trạng thái theo xác nhận sinh viên đã làm xong các bước rà/review/gửi nhận xét; giữ log gốc và đóng gói bản cuối.
