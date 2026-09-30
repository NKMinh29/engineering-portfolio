# 40. Drone autopilot PX4 ArduPilot và MAVLink

**Nhóm:** Robot & drone · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Multirotor dynamics.
2. IMU GPS barometer.
3. Estimation và control loop.
4. Flight modes.
5. Mission planning.
6. SITL.
7. MAVLink telemetry.
8. Failsafe.
9. Geofence và an toàn thử nghiệm.

## Giảng nhanh

Autopilot giữ ổn định bay bằng vòng điều khiển nhanh và dùng cảm biến để ước lượng trạng thái. SITL chạy phần mềm autopilot trong mô phỏng, cho phép quan sát trạng thái và thử logic nhiệm vụ trước phần cứng. Một lệnh bay có thể nguy hiểm nếu mất GPS hoặc link; kiểm thử đầu tiên cần tình huống dừng an toàn.

## Bài tập ngắn

1. Phân biệt attitude position và mission control.
2. Viết bảng phản ứng với mất GPS pin thấp và mất link.

## Project portfolio: Kịch bản telemetry drone trên SITL

**Các bước thực hiện:**

1. Chọn ArduPilot SITL Windows hoặc môi trường lab PX4 theo hướng dẫn.
2. Chạy chuyến mô phỏng tối thiểu và lưu log.
3. Trích timestamp mode độ cao pin mô phỏng.
4. Thử một tình huống mất link theo khả năng simulator.
5. Viết bảng trạng thái mong muốn thực tế quan sát và sai khác.

**Kiểm tra kết quả:**

- README ghi rõ chỉ là mô phỏng.
- Không có bước triển khai bay thật trong demo nhập môn.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Đọc trước; nếu mô phỏng nặng dùng máy lab; Mission Planner có bản Windows

## Học sâu từ tài liệu gốc

- [ArduPilot SITL](https://ardupilot.org/dev/docs/SITL-setup-landingpage.html)
- [PX4 Simulation](https://docs.px4.io/main/en/simulation/)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
