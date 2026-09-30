# 39. LiDAR point cloud SLAM và dẫn đường

**Nhóm:** Robot & drone · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. ToF và độ phân giải.
2. 2D scan vs 3D cloud.
3. Tọa độ và transform.
4. Outlier và downsample.
5. Odometry.
6. Scan matching.
7. Mapping và localization.
8. Occupancy grid.
9. Nav2 planner và costmap.

## Giảng nhanh

LiDAR đo hình học của môi trường; SLAM vừa dựng bản đồ vừa ước lượng vị trí khi chưa có tọa độ tuyệt đối tin cậy. Downsample giúp giảm tính toán nhưng có thể xóa vật nhỏ. Nhiễu, mặt phản xạ và chuyển động khiến scan khác môi trường thực; ghi frame và đơn vị là bắt buộc.

## Bài tập ngắn

1. Đổi ba điểm polar (r,θ) sang x,y.
2. Lập occupancy grid 5×5 từ sáu tia đơn giản.

## Project portfolio: Bộ xử lý point cloud mẫu

**Các bước thực hiện:**

1. Chọn point cloud mẫu nhỏ từ thư viện hoặc dữ liệu tự sinh.
2. Đọc và trực quan tọa độ XYZ.
3. Lọc theo phạm vi và bỏ outlier thô.
4. Chia vùng trước trái phải rồi báo khoảng cách gần nhất.
5. Tạo 3 cảnh chướng ngại và case không có điểm hợp lệ.

**Kiểm tra kết quả:**

- Không báo khoảng cách 0 khi scan rỗng.
- Kết quả đổi hệ trục kiểm được bằng tính tay.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Mẫu point cloud nhỏ trên Colab hoặc máy Windows; ROS/Nav2 sau

## Học sâu từ tài liệu gốc

- [Open3D Point Cloud](https://www.open3d.org/docs/latest/tutorial/geometry/pointcloud.html)
- [Nav2 Mapping Localization](https://docs.nav2.org/rolling/configuration_and_development/first_time_robot_setup_guide/sensors/mapping_localization/)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
