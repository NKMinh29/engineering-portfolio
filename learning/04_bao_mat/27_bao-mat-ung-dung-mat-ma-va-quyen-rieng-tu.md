# 27. Bảo mật ứng dụng mật mã và quyền riêng tư

**Nhóm:** Bảo mật · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Hash password và salt.
2. Chữ ký số và xác minh.
3. Mã hóa đối xứng bất đối xứng.
4. TLS.
5. Phân quyền và session.
6. Input validation.
7. SQL injection và XSS.
8. Quản lý secret.
9. Privacy by design.

## Giảng nhanh

Hash một chiều hữu ích đối chiếu nội dung; chữ ký số chứng minh thông điệp gắn với khóa riêng tương ứng; mã hóa giữ nội dung bí mật. Ba mục tiêu này khác nhau. Dùng thư viện đáng tin cậy và API chuẩn thay vì tự thiết kế thuật toán mật mã cho ứng dụng.

## Bài tập ngắn

1. Tìm điểm có thể SQL injection trong API nối chuỗi query.
2. Phân loại ba tình huống cần hash cần ký và cần mã hóa.

## Project portfolio: Làm cứng API telemetry

**Các bước thực hiện:**

1. Lấy API chuyên đề 07 và thêm kiểm tra input.
2. Sử dụng parameterized query.
3. Viết test cho script đầu vào độc hại trên dữ liệu mẫu của mình.
4. Đưa secret qua biến môi trường và rà log.
5. Viết bảng threat → test → kết quả cùng hướng dẫn chạy.

**Kiểm tra kết quả:**

- Test input bất thường không thay đổi database ngoài ý định.
- Repo không có credential hoặc dữ liệu thật.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** API chạy localhost với dữ liệu giả

## Học sâu từ tài liệu gốc

- [OWASP Top 10](https://top10.owasp.org/2025/)
- [Python Secrets](https://docs.python.org/3/library/secrets.html)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
