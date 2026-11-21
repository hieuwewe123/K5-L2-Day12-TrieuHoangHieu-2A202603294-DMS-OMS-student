# Báo cáo Lab Ngày 12 — DMS & OMS

**Triệu Hoàng Hiếu — 2A202603294 — G01**

## Kết quả

Đã gán 22 ảnh cốt lõi (S01–S08, mỗi cảnh RGB và IR-sim; D01–D06 NIR), mỗi ảnh đúng một frame_meta. Project Day12, task Day12-G01 (id 27), job 26 trên CVAT local.

Bản nhãn mới nhất là **export_final_v2.zip**. Kiểm tra theo schema cập nhật: **0 lỗi, 0 cảnh báo**. Export chỉ chứa annotations.xml, không kèm ảnh.

## OMS

Ghế gọi theo xe; bên trái ảnh là rear_right. Person và face chỉ cho người lớn theo phạm vi bài. Nôi xách dùng infant_seat; ghế trẻ em lưng cao dùng child_seat. Không vẽ box ghế xe trống.

Schema mới bổ sung child_seat.occupied=yes: đã dùng ở S03/S05 khi có trẻ. Infant_seat giữ seat/facing, không tự thêm occupied. Hai câu hỏi về mở rộng nhãn người/trẻ và trạng thái nôi có trẻ được ghi trong class_list_v0.md.

Ảnh được đọc riêng: S01_rgb giữ occupied=unknown khi lòng ghế tối; S06_rgb object.type=other trong khi S06_ir=bag. S03 vật phẳng ở ghế giữa dùng other, cốc ở rear_right dùng cup. S04 có object box ở rear_right.

## DMS

Giữ ảnh xoay gốc; trái/phải mắt và tay theo người. Cả 6 ảnh có face và face13, các điểm che có cờ phù hợp. Có 12 hand và 1 phone. D02 chai nước không được gán thành phone; D06 kính cầm trên tay nên glasses=none. Không suy buồn ngủ từ một khung mắt closed.

Sau rà soát, D01 seatbelt=unknown và D05 glasses=unknown để tránh khẳng định khi chưa đủ bằng chứng. Chi tiết sửa trước/sau ở REWORK.md.

## Tự kiểm và review

- check_cpA: phạm vi S01/S02, 4 ảnh; check_cpB: D01/D02, 2 ảnh. Đây là lượt kiểm giới hạn sau khi có bản nhãn, không khẳng định được thực hiện đúng giờ checkpoint trên lớp.
- check_final: bản export_final.zip trước cập nhật cuối; check_final_v2: bản hiện hành sau xử lý review.
- Quốc Anh → Hiếu → Dũng → Quốc Anh. Hiếu review Dũng qua 52 dòng diff. Nhận log Quốc Anh review Hiếu gồm 98 dòng, 5 peer/93 ambiguous.
- Giữ nguyên log Quốc Anh tại review_QuocAnh_cho_Hieu.csv. Bản làm việc disagreement_log.csv có thêm response_Hieu/resolution_status, ghi rõ quyết định riêng của Hiếu; không sửa verdict gốc thành đồng thuận chung.
- Bản Quốc Anh đã xem trước lượt sửa cuối được lưu ở export_reviewed_by_QuocAnh.zip. Sáu thuộc tính đã sửa sau rà soát được liệt kê ở REWORK.md.

## Xử lý ca D01 và kiểm mặt OMS

Sinh viên xác nhận vùng tay phải sát mép trái D01 là hand. Đã bổ sung box, side=right, on_wheel=unknown do không thấy chắc tiếp xúc vô lăng. Sinh viên đã xác nhận hoàn tất rà trực quan, gửi lại bản mới cho Quốc Anh và chốt trao đổi các quyết định giữ/sửa.

S02 và S04 đều có box face trên RGB/IR. OMS chỉ yêu cầu box mặt; face13 chỉ gán ở DMS.

## Bằng chứng kèm theo

E1: hai export nhãn; E2: checkpoint và check cuối; E3: log nhận về, phản hồi và log review Dũng; E4: 9 quan sát IR (tách IR_sim/real_IR); E5: 8 mục DMS, 7 mục OMS và 2 câu hỏi có khung ví dụ. Có self_review, exit_ticket, TEAM và prompts theo danh sách nộp.

Ghi nhận khi đối chiếu XML: box child_seat rear_left ở S03_rgb trong CVAT hiện có cạnh phải x=851,50 thay vì x=845,00 ở bản Quốc Anh đã review. Giữ cạnh mới theo nhãn hiện có trong CVAT; các cạnh còn lại giữ nguyên. Ngoài thay đổi hình học này, khác biệt thuộc tính so bản đã review là 6 mục nêu trong REWORK.md.

## Hoàn tất review

Theo xác nhận của sinh viên, đã hoàn thành các bước rà trực quan, gửi lại bản cuối cho Quốc Anh, trao đổi xử lý nhận xét và gửi gói chấm Dũng. File reviewer gốc vẫn giữ các verdict tại thời điểm nhận; không thay thế bằng dữ liệu mới để làm mất lịch sử.
