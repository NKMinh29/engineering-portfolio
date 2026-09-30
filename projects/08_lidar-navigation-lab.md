# 08. Nhận biết vật cản và tìm đường từ LiDAR

**Tên repo đề xuất:** `lidar-navigation-lab`  
**Ưu tiên:** P2 — học thuật toán trước tích hợp ROS  
**Năng lực:** Robotics, LiDAR, geometry, planning, ROS 2, ADAS concepts  
**Ước lượng lập kế hoạch:** 35–60 giờ cho bản 2D. Không phải cam kết; chưa tính toàn bộ thời gian học nền tảng.

> Trạng thái: bản thiết kế. Prototype CAN Log Workbench được chuẩn bị riêng; các sản phẩm khác cần triển khai hoặc nhập artifact gốc. Tiêu chí nghiệm thu là mục tiêu, chưa phải kết quả đã đạt.

## 1. Người dùng và bài toán

Robot chở hàng cần biểu diễn khoảng trống/vật cản và tìm đường trên bản đồ nhỏ, có thể xem lại lý do planner thất bại.

## 2. MVP — phiên bản nhỏ nhất đủ demo

- Tạo/đọc scan 2D, chuyển polar sang Cartesian, rasterize occupancy grid.
- A* trên bản đồ có obstacle inflation theo bán kính robot.
- Viewer chạy offline: scan, map, start/goal và path.

## 3. Kiến trúc và hợp đồng dữ liệu

Scan replay + known pose → coordinate transform → occupancy grid → inflated costmap → planner → viewer. ROS adapter thêm sau bằng topic và tf khi có môi trường phù hợp.

**Hợp đồng:** Scan {timestamp, angle_min_rad, angle_increment_rad, ranges_m, sensor_pose}; map {resolution_m, origin, width, height, occupancy}. Ghi rõ frame trục và đơn vị; invalid range không biến thành vật cản tại gốc.

## 4. Công cụ và môi trường

Python/NumPy + viewer nhẹ trên Windows; map synthetic nhỏ. ROS/Gazebo hoặc dataset lớn chạy trên máy lab/remote khi tới mốc tích hợp.

## 5. Cấu trúc repo đề xuất

- `scan/`: parser/transforms
- `mapping/`: grid
- `planning/`: A* và inflation
- `scenarios/`: seed và map nhỏ
- `viewer/`: replay
- `ros_adapter/`: giai đoạn sau

## 6. Milestones để chuyển thành GitHub Issues

1. Tự tính tọa độ ba tia rồi kiểm tra transform.
2. Tạo map hành lang có ground truth.
3. Cài A* và so đường đi với vài map nhỏ có đáp án.
4. Thêm robot radius; kiểm tra đường hẹp không thể đi.
5. Replay dữ liệu có pose đã biết; đánh giá map/path.
6. Tạo ROS publisher/subscriber adapter sau khi core chạy.

Mỗi milestone là một issue cha; tách task chỉ khi đủ nhỏ để có output và cách kiểm tra trong một buổi làm. Commit theo thay đổi thật, không tạo lịch sử đóng góp giả.

## 7. Nghiệm thu

- Đường không xuyên obstacle đã inflate trong toàn bộ suite.
- Start/goal ngoài map và không có đường trả lỗi rõ.
- Lưu path length, số node mở, planning time cho từng scenario.
- Nếu dùng pose đã biết thì mô tả là mapping/planning; chưa gọi là SLAM.

## 8. Bằng chứng đưa lên portfolio

Điều chỉnh bán kính robot làm hành lang trở nên không đi được; giải thích costmap và kết quả.

README cần: bài toán → demo → cách chạy → kiến trúc → kết quả đo → hạn chế → phần đóng góp của Minh → nguồn và license. Số đo phải gắn thiết bị/cấu hình/dataset; không đặt badge test pass trước khi có workflow chạy thật.

## 9. Giảng nhanh

LiDAR cho khoảng cách theo frame sensor; muốn đặt điểm vào map cần phép biến đổi theo pose. SLAM còn phải ước lượng vị trí và bản đồ, khó hơn pipeline replay với pose có sẵn.

## 10. Phạm vi và bước tiếp theo

Chưa có điều khiển robot thật hoặc tuyên bố ADAS đạt chuẩn. ROS là mốc nối tiếp, không phải yêu cầu cài ngay với 20 GB trống.

## Tài liệu gốc

- ROS 2 documentation — https://docs.ros.org/en/jazzy/

Tình trạng kiểm tra liên kết ghi trong `../NGUON_VA_PHAM_VI.md`. Tài liệu là điểm bắt đầu học; thiết kế MVP và nghiệm thu ở đây là đề xuất riêng cho portfolio của Minh.
