# Review chéo — Hiếu chấm Hà Huy Dũng

Người review: Triệu Hoàng Hiếu — 2A202603294

Bài được review: Hà Huy Dũng — 2A202603271, G01. Nguồn: gói zip Dũng được cung cấp trong Downloads, file export_final.zip bên trong. Không sửa file nộp của Dũng.

Bản đối chiếu: export_final_v2.zip của Hiếu. Trong CSV, **mine=Hiếu, peer=Dũng**; verdict=peer nghĩa là đề nghị giữ cách gán của Dũng, không phải đánh dấu Dũng sai.

## Kiểm tra cấu trúc

- 22 ảnh G01, đủ 22 frame_meta, export không kèm ảnh.
- cabin_check theo schema mới: **0 lỗi, 1 cảnh báo D03**.
- Cảnh báo D03 so trục x không tự kết luận sai trái/phải ở ảnh xoay. Cần xem trục y; mắt trái phải có y lớn hơn mắt phải khi áp dụng hướng ảnh mô tả trong GUIDE.

## Nhận xét chính gửi Dũng

1. **Đồng bộ schema mới:** S03_rgb/ir (rear_left), S05_rgb/ir (rear_left và rear_right) có trẻ nhưng occupied vẫn unknown. Bản labels_cabin_v1.json mới đã thêm yes: đề nghị đổi thành yes ở 6 shape. Đây là cập nhật so với schema cũ, không quy lỗi hồi tố cho bản cũ.
2. **S04_rgb/ir, box face:** box hiện gồm nhiều tóc. Thu box sát vùng mặt thấy được; không lấy tóc làm mép mặt. Xem GUIDE 4.1 và 4.4-5.
3. **D02, điểm miệng:** chai che vùng môi; không đặt điểm cho đủ. Nếu không định vị chắc mép/khóe, dùng outside; occluded chỉ khi vẫn định vị chắc. Có nhiều dòng CSV vì so từng cờ của cùng điểm.
4. **D05, loại kính:** Hiếu ghi clear, Dũng ghi sun. NIR không đủ chắc chỉ từ độ tối của tròng; khuyến nghị cả hai dùng unknown và giữ mắt unknown.
5. **Các ca cần cùng xem lại:** D01 tay sát biên ảnh và cờ môi; D03 điểm mắt phải; D04 box tay/cổ tay và loại kính; D05 hai box tay; D06 dải dây an toàn. CSV đánh ambiguous, chưa phải kết luận được hai người đồng ý.
6. **Thuộc tính face ở S02:** OMS chỉ yêu cầu box face. Chênh lệch mắt/kính giữa hai bản không nên bị tính như yêu cầu thuộc tính DMS bị sai.

## Những chỗ bản Dũng được khuyến nghị giữ

- D01 seatbelt=unknown vì chưa đủ bằng chứng khẳng định không có dây trong vùng tối.
- S01_rgb occupied=unknown nếu chưa nhìn rõ lòng ghế trên chính RGB.
- S03 object.type=other, S06_rgb object.type=other: không khẳng định bag khi hình dạng chưa đủ rõ.

## Kết quả đối chiếu

- Đã điền verdict/rule/action cho **52 dòng**: ambiguous=29, both_wrong=1, mine=17, peer=5.
- 52 dòng là chênh lệch máy phát hiện, không phải 52 lỗi độc lập: một điểm mặt có thể sinh hai dòng cờ; một box IoU thấp sinh cặp mine/peer; cùng cảnh RGB/IR lặp quyết định.
- Đây là nhận xét của người review, **chưa có xác nhận Dũng đồng ý hoặc đã sửa**. Các dòng ambiguous cần hai bạn mở CVAT để chốt hoặc hỏi coach.

## Dũng làm tiếp

Cập nhật schema, kiểm từng nhận xét, tự sửa trên CVAT rồi export lại không kèm ảnh. Chạy cabin_check sau sửa; giải thích cảnh báo D03 nếu còn. Không sửa XML trực tiếp và không thay file export bằng bản của Hiếu.

Vòng nhóm: Quốc Anh chấm Hiếu → Hiếu chấm Dũng → Dũng chấm Quốc Anh. File này là lượt Hiếu chấm Dũng, không thay thế kết quả Quốc Anh chấm Hiếu.
