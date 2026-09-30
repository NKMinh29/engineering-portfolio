# 33. IoT cảm biến và mạng không dây

**Nhóm:** Phần cứng & nhúng · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Sensor calibration.
2. Sampling và timestamp.
3. UART I2C SPI.
4. MQTT và HTTP.
5. Wi-Fi BLE LoRa.
6. Provisioning.
7. Edge gateway.
8. Mất kết nối và retry.
9. Tiêu thụ điện và quản lý pin.

## Giảng nhanh

IoT gồm thiết bị đo, liên kết truyền, nơi lưu dữ liệu và người xem dữ liệu. Một cảm biến đo sai được truyền thành công vẫn là dữ liệu sai; timestamp và trạng thái hiệu chuẩn nên đi cùng mẫu. MQTT phù hợp truyền tin kiểu publish/subscribe, còn LoRa là một cách truyền vật lý/vô tuyến khác lớp.

## Bài tập ngắn

1. Thiết kế JSON ghi nhiệt độ có đơn vị và trạng thái sensor.
2. Nêu hành vi khi mất kết nối 30 giây.

## Project portfolio: Thiết bị telemetry giả lập tới dashboard

**Các bước thực hiện:**

1. Tạo script mô phỏng sensor mỗi giây với timestamp sequence và trạng thái.
2. Gửi tới API hoặc MQTT broker thử nghiệm có kiểm soát.
3. Thêm khả năng mất mạng giả lập và buffer hữu hạn.
4. Hiển thị dữ liệu cùng độ mới của mẫu.
5. Đo số mẫu mất lặp và thời gian phục hồi.

**Kiểm tra kết quả:**

- Dashboard phân biệt đang kết nối và dữ liệu cũ.
- Dữ liệu lặp không làm đếm sai cảnh báo.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Mô phỏng trên Windows trước; board ESP32 chỉ là tùy chọn khi có sẵn

## Học sâu từ tài liệu gốc

- [MQTT Introduction](https://mqtt.org/)
- [ESP-IDF Getting Started](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
