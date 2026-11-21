# Khai báo dùng AI — Triệu Hoàng Hiếu

Dùng Codex để hỗ trợ kiểm tra định dạng đầu ra, đối chiếu chéo và hoàn thiện văn bản báo cáo. Toàn bộ quá trình tạo task CVAT và gán nhãn dữ liệu (bounding box, thuộc tính, keypoints) đều do sinh viên thực hiện thủ công trực tiếp trên giao diện CVAT.

| Công cụ | Nội dung yêu cầu | Cách sử dụng và kiểm tra |
|---|---|---|
| Codex | Hỗ trợ chuẩn bị khung dữ liệu và kiểm tra export | Hỗ trợ viết script kiểm tra cấu trúc file JSON/metadata sau khi xuất từ CVAT; đối chiếu đảm bảo file ZIP đúng quy cách (không chứa ảnh gốc) |
| Codex | Hỗ trợ rà soát logic và phản hồi review chéo | Hỗ trợ tổng hợp và kiểm tra tính nhất quán của nhận xét chấm chéo (bài của Dũng) và phản hồi log rà soát (từ Quốc Anh); sinh viên trực tiếp chỉnh sửa nhãn thủ công trên CVAT |
| Codex | Hoàn thiện tài liệu và báo cáo | Hỗ trợ biên tập câu chữ, định dạng bảng biểu cho danh sách lớp, phần quan sát IR, tự đánh giá, đáp án exit ticket và báo cáo tổng kết; đối chiếu kỹ với guideline và số liệu thực tế |

Bản cuối gồm 22 ảnh do sinh viên tự gán nhãn thủ công, công cụ `cabin_check` báo 0 lỗi và 0 cảnh báo; gói file ZIP xuất ra đúng chuẩn và không chứa ảnh.
