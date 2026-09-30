# 32. Lập trình nhúng và RTOS

**Nhóm:** Phần cứng & nhúng · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. GPIO ADC PWM UART SPI I2C CAN.
2. ISR và ưu tiên.
3. Task scheduler.
4. Queue mutex semaphore.
5. Deadline và watchdog.
6. Driver abstraction.
7. Memory static vs heap.
8. State machine.
9. Profiling và lỗi thời gian thực.

## Giảng nhanh

Task thường chịu scheduler; ISR phải ngắn và báo sự kiện để task xử lý phần dài. Queue truyền dữ liệu giữa task đồng thời tránh chia sẻ biến không đồng bộ. Với nhiệm vụ đọc cảm biến 10 ms, cần đo cả thời gian chạy và jitter chứ không chỉ thấy LED hoạt động.

## Bài tập ngắn

1. Vẽ lịch ba task chu kỳ 10 50 100 ms.
2. Viết pseudo-code ISR đẩy sự kiện cho task mà không in log dài trong ngắt.

## Project portfolio: Bộ ghi log có deadline trên S32K144

**Các bước thực hiện:**

1. Tạo task đọc input task xử lý task ghi kết quả.
2. Dùng queue có kích thước giới hạn và counter overflow.
3. Tạo tải nền có thể bật tắt.
4. Đo thời gian phản hồi và bỏ lỡ deadline 1000 sự kiện.
5. Viết biểu đồ và lý giải giới hạn công cụ đo.

**Kiểm tra kết quả:**

- Có cách chứng minh queue tràn được ghi nhận.
- Nêu clock và cấu hình ưu tiên task ISR.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Dùng project FreeRTOS S32K144 đã clean build; không cần thêm OS trên PC

## Học sâu từ tài liệu gốc

- [FreeRTOS Docs](https://docs.freertos.org/)
- [NXP S32K Data Sheet](https://www.nxp.com/docs/en/data-sheet/S32K1xx.pdf)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
