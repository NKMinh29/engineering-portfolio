# 28. Bảo mật xe robot và IoT

**Nhóm:** Bảo mật · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. CAN spoofing và replay.
2. IDS detection vs prevention.
3. Secure boot và firmware.
4. Khóa thiết bị.
5. ROS DDS security.
6. MAVLink signing.
7. Threat model sensor spoof.
8. Bảo mật OTA.
9. Failsafe khi mất tin cậy.

## Giảng nhanh

IDS có thể gắn cờ một frame nghi ngờ nhưng không tự xác thực nguồn gốc bản tin CAN. ROS 2 có công cụ SROS2 dựa trên DDS Security cho danh tính và chính sách giao tiếp; MAVLink 2 có message signing cho xác thực. Mỗi biện pháp bảo vệ một ranh giới khác nhau.

## Bài tập ngắn

1. Vẽ đường truyền CAN MCU ROS và máy điều khiển và đánh dấu điểm tin cậy.
2. Phân loại replay và dữ liệu nhiễu cảm biến theo lớp bị ảnh hưởng.

## Project portfolio: Bộ thử khả năng phát hiện sự cố CAN

**Các bước thực hiện:**

1. Tái sử dụng bộ nhận CAN lab hoặc dữ liệu log hợp pháp.
2. Xây tập gói bình thường và 3 mẫu sai có ghi provenance.
3. Chạy detector và ghi confusion matrix cùng độ trễ.
4. Thử trường hợp mất gói hoặc đảo thứ tự không phải tấn công.
5. Viết khuyến nghị tách phát hiện và chính sách phản ứng an toàn.

**Kiểm tra kết quả:**

- Có dữ liệu bình thường và lỗi kỹ thuật để so false alarm.
- Không tuyên bố IDS ngăn chặn frame khi chỉ quan sát.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Lab sở hữu của mình hoặc dữ liệu giả lập; không thử trên phương tiện giao thông

## Học sâu từ tài liệu gốc

- [SROS2](https://github.com/ros2/sros2)
- [MAVLink Signing](https://mavlink.io/en/guide/message_signing.html)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
