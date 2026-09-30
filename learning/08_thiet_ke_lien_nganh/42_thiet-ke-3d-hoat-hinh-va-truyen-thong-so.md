# 42. Thiết kế 3D hoạt hình và truyền thông số

**Nhóm:** Thiết kế & liên ngành · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Mesh topology.
2. Modeling modifier.
3. UV và material.
4. Lighting camera render.
5. Keyframe và animation.
6. Storyboard.
7. Compositing.
8. Video/audio export.
9. Asset optimization và bản quyền.

## Giảng nhanh

Model 3D gồm hình học và vật liệu; ánh sáng và camera quyết định sản phẩm cuối có truyền đạt đúng cấu trúc hay không. Animation dùng keyframe mô tả các thời điểm chính rồi nội suy các frame giữa. Với một mô hình robot, kích thước và vị trí cảm biến có ý nghĩa kỹ thuật, nên ghi tỷ lệ bản vẽ.

## Bài tập ngắn

1. Vẽ storyboard bốn khung mô tả sensor phát hiện vật cản.
2. Mô hình một bánh xe từ primitive và ghi kích thước.

## Project portfolio: Video giải thích robot chở hàng 20–30 giây

**Các bước thực hiện:**

1. Viết kịch bản có ba ý input xử lý output.
2. Mô hình thân xe đơn giản và vị trí LiDAR.
3. Đặt camera ánh sáng và nhãn chú giải.
4. Tạo hoạt cảnh đến gần vật cản và dừng.
5. Render độ phân giải vừa phải và đóng gói file nguồn ảnh preview kịch bản.

**Kiểm tra kết quả:**

- Người xem thấy rõ sensor và đường dữ liệu.
- README phân biệt mô hình minh họa với thiết kế cơ khí thực.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Có thể bắt đầu bằng storyboard SVG; render 3D ở máy lab nếu PC không đủ dung lượng

## Học sâu từ tài liệu gốc

- [Blender Manual](https://docs.blender.org/manual/en/latest/modeling/meshes/introduction.html)
- [FPT Digital Arts](https://daihoc.fpt.edu.vn/chuyen-nganh/thiet-ke-do-hoa-va-my-thuat-so/)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
