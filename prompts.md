# Khai báo dùng AI — Triệu Hoàng Hiếu

Dùng Codex để chuẩn bị CVAT, hỗ trợ gán nhãn, kiểm tra export và soạn báo cáo theo thông tin sinh viên cung cấp rằng giảng viên cho phép mở rộng phạm vi sử dụng công cụ.

| Công cụ | Nội dung yêu cầu | Cách sử dụng và kiểm tra |
|---|---|---|
| Codex | Chuẩn bị dữ liệu, CVAT và schema | Tạo task G01 với 22 ảnh, cập nhật occupied=yes theo file nhãn mới; kiểm metadata và JSON |
| Codex | Gán nhãn và sửa sau rà soát | Xem ảnh, tạo box/thuộc tính/face13 qua CVAT API; kiểm lại ảnh, cờ điểm và export |
| Codex | Review chéo và xử lý nhận xét | Chạy check/diff, viết nhận xét chấm Dũng, phản hồi log Quốc Anh; giữ log gốc và ghi thay đổi |
| Codex | Hoàn thiện tài liệu | Soạn danh sách lớp, quan sát IR, tự đánh giá, đáp án exit ticket và báo cáo; đối chiếu guideline, phép tính và kết quả kiểm |

Bản cuối có 22 ảnh, cabin_check báo 0 lỗi và 0 cảnh báo; ZIP không chứa ảnh.
