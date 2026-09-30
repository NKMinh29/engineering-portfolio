# 35. AUTOSAR Adaptive và kiến trúc ECU hiệu năng cao

**Nhóm:** Automotive · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. POSIX OS và process.
2. Service-oriented architecture.
3. ara::com.
4. Service discovery.
5. Execution management.
6. Persistency.
7. Update configuration.
8. Security và IAM.
9. Classic-Adaptive interaction.

## Giảng nhanh

Adaptive hướng tới ứng dụng cần dịch vụ có thể tìm và kết nối trong runtime trên nền POSIX. Một sơ đồ kiến trúc Adaptive có thể học bằng giấy và code mock khi chưa có stack thương mại; đừng gọi một chương trình C++ Linux bất kỳ là triển khai AUTOSAR Adaptive đầy đủ.

## Bài tập ngắn

1. Vẽ hai service Camera và Perception với interface.
2. Nêu đường chuyển tín hiệu từ Classic ECU sang dịch vụ xử lý của Adaptive.

## Project portfolio: Prototype kiến trúc service mô phỏng

**Các bước thực hiện:**

1. Định nghĩa hai process publisher và consumer với JSON interface.
2. Cho consumer tự tìm endpoint từ một registry nhỏ.
3. Mô phỏng service biến mất và quay lại.
4. Viết sequence diagram startup discovery reconnect.
5. So sánh từng khối với thuật ngữ Adaptive và ghi rõ chỗ mô phỏng khác chuẩn.

**Kiểm tra kết quả:**

- Service outage có log và cách phục hồi.
- README nói rõ đây là prototype minh họa không phải AUTOSAR stack.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Vẽ kiến trúc và prototype trên Windows; chạy stack POSIX đầy đủ khi có máy lab

## Học sâu từ tài liệu gốc

- [AUTOSAR Adaptive Platform](https://www.autosar.org/standards/adaptive-platform)
- [AUTOSAR Standards](https://www.autosar.org/standards)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
