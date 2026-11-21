# Cập nhật schema cabin

Nguồn: labels_cabin_v1.json do sinh viên cung cấp từ Downloads.

Thay đổi duy nhất so với bản repo gốc: child_seat.occupied từ [unknown, no] thành [unknown, no, yes]. Các lớp và thuộc tính còn lại giữ nguyên.

Đã đồng bộ labels_cabin_v1.json, scripts/cabin_schema.py và schema project Day12 trong CVAT. Không sửa logic kiểm tra nào khác. Bộ kiểm tra cũ từ repo chưa cập nhật sẽ báo occupied=yes không hợp lệ; cần dùng schema mới đi kèm khi kiểm bản v2.

S03/S05: 6 shape child_seat (3 ghế × 2 modality) đổi unknown thành yes do thấy trẻ. Infant_seat không có occupied nên giữ seat/facing.

Bản nhãn mới nhất: export_final_v2.zip. Bản trước cập nhật: export_final.zip. V2 ở đây do cập nhật schema, không phải xác nhận review chéo đã hoàn tất.
