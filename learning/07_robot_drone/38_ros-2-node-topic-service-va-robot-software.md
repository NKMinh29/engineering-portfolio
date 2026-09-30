# 38. ROS 2 node topic service và robot software

**Nhóm:** Robot & drone · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. ROS graph.
2. Nodes topics messages.
3. Services actions.
4. Parameters launch.
5. TF2 frames.
6. URDF robot model.
7. QoS.
8. rosbag.
9. Testing và quan sát rqt RViz.

## Giảng nhanh

Topic phù hợp luồng dữ liệu cảm biến liên tục; service phù hợp yêu cầu phản hồi ngắn; action phù hợp việc kéo dài có phản hồi/hủy như đi tới mục tiêu. ROS chạy ở tầng máy tính của robot; S32K144 xử lý ngắt và điều khiển mức thấp rồi trao đổi qua một giao tiếp xác định.

## Bài tập ngắn

1. Chọn topic service action cho dữ liệu LiDAR lệnh bật đèn nhiệm vụ giao hàng.
2. Vẽ tf tree map → odom → base_link → lidar.

## Project portfolio: Kiến trúc ROS robot chở hàng tối giản

**Các bước thực hiện:**

1. Định nghĩa node lidar obstacle detector planner motor bridge.
2. Định nghĩa message type tần suất và giới hạn trễ.
3. Chạy bài talker listener trong môi trường ROS trên máy lab/cloud nếu có.
4. Dùng dữ liệu mẫu tạo một node báo chướng ngại.
5. Xuất sơ đồ graph cùng log và ghi rõ node nào đã chạy thật.

**Kiểm tra kết quả:**

- Không nhầm topic với service trong sơ đồ.
- README ghi môi trường ROS và cách tái chạy.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Học docs trên Windows; ROS thực hành trên máy lab hoặc từ xa với dung lượng lớn hơn

## Học sâu từ tài liệu gốc

- [ROS2 Jazzy Tutorials](https://repo.test.ros2.org/en/jazzy/Tutorials.html)
- [ROS2 Basic Concepts](https://repo.test.ros2.org/en/jazzy/Concepts/Basic.html)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
