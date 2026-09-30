# 26. An ninh mạng và phòng thủ hệ thống

**Nhóm:** Bảo mật · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Threat model và tài sản.
2. TCP IP và bề mặt tấn công.
3. IAM và nguyên tắc tối thiểu quyền.
4. Logging và giám sát.
5. Mã hóa khi truyền.
6. Phân đoạn mạng.
7. Vulnerability management.
8. Incident response.
9. Báo cáo tái lập và ranh giới thử nghiệm.

## Giảng nhanh

Bảo mật bắt đầu từ câu hỏi tài sản nào cần bảo vệ và ai có thể tác động. Một thiết bị IoT dùng chung mật khẩu có bề mặt rủi ro khác thiết bị chỉ chạy trong mạng lab. Quan sát log có ích khi timestamp và ID sự kiện thống nhất; phát hiện không đồng nghĩa đã ngăn chặn.

## Bài tập ngắn

1. Vẽ sơ đồ trust boundary cho laptop USB-CAN và board.
2. Viết ba dấu hiệu quan sát được khi thiết bị mất kết nối.

## Project portfolio: Threat model cho hệ thống telemetry lab

**Các bước thực hiện:**

1. Vẽ node dữ liệu và các đường truyền.
2. Liệt kê tài sản tấn công giả định và hậu quả.
3. Xếp ưu tiên theo xác suất/ảnh hưởng có giải thích.
4. Chọn hai biện pháp kiểm soát và một tình huống kiểm tra cho mỗi biện pháp.
5. Viết báo cáo kết quả trong môi trường sở hữu hoặc mô phỏng.

**Kiểm tra kết quả:**

- Mỗi rủi ro gắn với bề mặt thật của sơ đồ.
- Có phạm vi thử nghiệm và không công bố bí mật truy cập.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Chỉ phân tích hệ thống mình sở hữu hoặc bộ mô phỏng

## Học sâu từ tài liệu gốc

- [OWASP Top 10](https://top10.owasp.org/2025/)
- [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
