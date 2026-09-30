# 07. Backend API và kiến trúc dịch vụ

**Nhóm:** Phần mềm & dữ liệu · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. HTTP method status code.
2. REST và tài nguyên.
3. JSON schema validation.
4. CRUD và transaction.
5. Authentication authorization.
6. Pagination filtering.
7. API versioning.
8. Logging metrics.
9. Unit integration API tests.

## Giảng nhanh

API là hợp đồng giữa client và server. `POST /readings` tạo bản ghi; `GET /readings?device=...` truy xuất bản ghi đã lưu. Trả 400 cho input sai và 404 cho ID không tồn tại giúp client xử lý rõ ràng; đừng dùng status 200 kèm thông báo lỗi mơ hồ.

## Bài tập ngắn

1. Viết hợp đồng JSON cho bản ghi cảm biến có timestamp và đơn vị.
2. Nêu kết quả mong muốn với dữ liệu thiếu giá trị.

## Project portfolio: API nhật ký cảm biến cho xe mẫu

**Các bước thực hiện:**

1. Tạo FastAPI với endpoint nhận và liệt kê dữ liệu.
2. Kiểm tra kiểu dải giá trị và timestamp.
3. Lưu vào SQLite để máy gọn nhẹ.
4. Thêm filter theo thiết bị và thời gian.
5. Tạo script gọi API và 5 bài thử input hợp lệ sai thiếu.

**Kiểm tra kết quả:**

- Endpoint có tài liệu truy cập được và ví dụ request response.
- Trường hợp sai trả status và thông báo kiểm tra được.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Python + SQLite trên Windows hoặc Codespaces; không cần Docker

## Học sâu từ tài liệu gốc

- [FastAPI First Steps](https://fastapi.tiangolo.com/tutorial/first-steps/)
- [MDN HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
