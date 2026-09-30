# 10. Cơ sở dữ liệu SQL và NoSQL

**Nhóm:** Phần mềm & dữ liệu · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Bảng khóa chính khóa ngoại.
2. Chuẩn hóa dữ liệu.
3. SELECT JOIN GROUP BY.
4. Index và query plan.
5. Transaction và isolation.
6. Constraint.
7. Lược đồ thời gian.
8. Document store.
9. Backup và migration.

## Giảng nhanh

Index giống mục lục tra cứu: giúp tìm một nhóm bản ghi nhanh hơn nhưng phải cập nhật khi ghi. Transaction giữ nhiều thao tác như một đơn vị; ví dụ ghi đơn hàng và lịch sử thanh toán phải cùng thành công hoặc cùng thất bại. Dữ liệu cảm biến thường cần index theo `device_id,time`.

## Bài tập ngắn

1. Thiết kế ba bảng robot readings alerts với quan hệ.
2. Viết truy vấn đếm cảnh báo theo ngày và thiết bị.

## Project portfolio: Kho dữ liệu telemetry cỡ nhỏ

**Các bước thực hiện:**

1. Thiết kế schema và constraint dải giá trị không âm.
2. Tạo bộ dữ liệu 1000 mẫu bằng seed cố định.
3. Viết truy vấn lọc theo robot khoảng thời gian và tổng hợp lỗi.
4. So sánh truy vấn trước sau index bằng query plan.
5. Tạo script nhập dữ liệu và xuất báo cáo CSV.

**Kiểm tra kết quả:**

- Có lệnh dựng mới database từ đầu.
- Dữ liệu sai vi phạm constraint thay vì âm thầm ghi vào bảng.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** SQLite nhẹ trên Windows; PostgreSQL có thể học tài liệu trước

## Học sâu từ tài liệu gốc

- [PostgreSQL SQL Tutorial](https://www.postgresql.org/docs/current/tutorial-sql.html)
- [SQLite Documentation](https://www.sqlite.org/docs.html)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
