# 05. Mạng máy tính và truyền thông

**Nhóm:** Nền tảng · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Bitrate latency bandwidth.
2. Ethernet IP TCP UDP.
3. Địa chỉ cổng DNS HTTP.
4. Socket và timeout.
5. Wi-Fi Bluetooth và CAN.
6. MQTT publish subscribe.
7. QoS và mất gói.
8. TLS và định danh.
9. Wireshark và đọc trace.

## Giảng nhanh

TCP bảo đảm luồng byte có thứ tự theo cơ chế riêng; UDP cung cấp datagram mà ứng dụng cần tự xử lý nếu mất hoặc đảo thứ tự. CAN có phân xử ưu tiên khác với Ethernet; không thể lấy bitrate chia độ dài payload rồi xem đó là toàn bộ trễ ứng dụng.

## Bài tập ngắn

1. Tính thời gian tuần tự hóa cho ba khung dữ liệu và nêu overhead chưa tính.
2. Phân loại lỗi kết nối DNS timeout và lỗi HTTP theo tầng.

## Project portfolio: Bộ mô phỏng telemetry mất gói

**Các bước thực hiện:**

1. Viết sender phát số thứ tự và timestamp theo UDP localhost.
2. Viết receiver kiểm tra gap duplicate và trễ.
3. Thêm cấu hình ngẫu nhiên bỏ một số gói trên sender.
4. Xuất CSV rồi tạo biểu đồ khoảng trống.
5. Viết báo cáo vì sao receiver không thể suy ra tuyệt đối mọi nguyên nhân mất dữ liệu.

**Kiểm tra kết quả:**

- Phát hiện gap có thể tái lập bằng seed.
- Không dùng giá trị âm làm độ trễ khi đồng hồ hoặc thứ tự khác nhau.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Python socket localhost trên Windows; không cần Internet khi chạy

## Học sâu từ tài liệu gốc

- [MDN How Web Works](https://developer.mozilla.org/en-US/docs/Learn_web_development/Getting_started/Web_standards/How_the_web_works)
- [MQTT Overview](https://mqtt.org/)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
