# 13. Ứng dụng quản lý hoạt động câu lạc bộ

**Tên repo đề xuất:** `clubops`  
**Ưu tiên:** P1 — lựa chọn web có người dùng cụ thể  
**Năng lực:** Full-stack, database, product design, security, reporting, PWA  
**Ước lượng lập kế hoạch:** 45–75 giờ. Không phải cam kết; chưa tính toàn bộ thời gian học nền tảng.

> Trạng thái: bản thiết kế. Prototype CAN Log Workbench được chuẩn bị riêng; các sản phẩm khác cần triển khai hoặc nhập artifact gốc. Tiêu chí nghiệm thu là mục tiêu, chưa phải kết quả đã đạt.

## 1. Người dùng và bài toán

Ban chủ nhiệm cần theo dõi thành viên, hoạt động, đóng quỹ và soạn báo cáo tháng từ dữ liệu có cấu trúc. Đây là ý tưởng sản phẩm phù hợp môi trường CLB của bạn.

## 2. MVP — phiên bản nhỏ nhất đủ demo

- Thành viên, sự kiện, attendance và fee ledger có audit trail.
- Vai trò member/editor/treasurer/admin với test phân quyền.
- Báo cáo tháng ở dạng preview có thể chỉnh trước khi xuất; không tự gửi mail.

## 3. Kiến trúc và hợp đồng dữ liệu

Web/PWA → authenticated API → domain services → relational DB → report renderer. Dữ liệu cá nhân và dòng tiền dùng dataset giả lập cho demo công khai.

**Hợp đồng:** Entities: Member, Event, Attendance, FeeEntry, Report, AuditEvent. FeeEntry dùng số nguyên VND, trạng thái và reference; corrections tạo bút toán điều chỉnh hoặc lịch sử, không âm thầm ghi đè.

## 4. Công cụ và môi trường

FastAPI + SQLite và UI đơn giản trước; PostgreSQL, migration và hosting sau MVP. PWA cho thao tác điện thoại trước khi nghĩ tới native app.

## 5. Cấu trúc repo đề xuất

- `api/`: routes/services
- `db/`: schema/migrations
- `web/`: member, event, fund, report screens
- `seed/`: dữ liệu giả lập
- `tests/`: permissions và reconciliation

## 6. Milestones để chuyển thành GitHub Issues

1. Viết 5 user stories với một người dùng thử.
2. Vẽ ERD và quyết định cách lưu trạng thái hội viên/đóng quỹ.
3. Làm member/event/attendance trước, rồi fee ledger.
4. Thêm quyền server-side và audit event.
5. Sinh draft báo cáo từ tháng được chọn; cho phép xem lại.
6. Dùng 3 task usability để sửa UI; ghi nhận consent nếu dùng feedback người thật.

Mỗi milestone là một issue cha; tách task chỉ khi đủ nhỏ để có output và cách kiểm tra trong một buổi làm. Commit theo thay đổi thật, không tạo lịch sử đóng góp giả.

## 7. Nghiệm thu

- Member không đọc được fee ledger toàn CLB hoặc dữ liệu quản trị qua API.
- Tổng thu/chi truy được về từng entry; correction có lịch sử.
- Report giới hạn đúng tháng, không lẫn sự kiện tháng sau.
- Demo seed không chứa thông tin thành viên thật.

## 8. Bằng chứng đưa lên portfolio

Tạo event → điểm danh → nhập fee entry → xem report preview; tài khoản member bị từ chối thao tác quản trị.

README cần: bài toán → demo → cách chạy → kiến trúc → kết quả đo → hạn chế → phần đóng góp của Minh → nguồn và license. Số đo phải gắn thiết bị/cấu hình/dataset; không đặt badge test pass trước khi có workflow chạy thật.

## 9. Giảng nhanh

Phân quyền phải được kiểm tra ở server: ẩn nút trên UI không ngăn người dùng tự gửi request. Audit trail giúp trả lời ai thay đổi gì và khi nào.

## 10. Phạm vi và bước tiếp theo

MVP tạo bản nháp báo cáo và dữ liệu demo; việc đưa vào vận hành cần chốt quy trình của CLB. Không tạo job gửi mail hay báo cáo tự động trong bản prototype này.

## Tài liệu gốc

- FastAPI tutorial — https://fastapi.tiangolo.com/tutorial/

Tình trạng kiểm tra liên kết ghi trong `../NGUON_VA_PHAM_VI.md`. Tài liệu là điểm bắt đầu học; thiết kế MVP và nghiệm thu ở đây là đề xuất riêng cho portfolio của Minh.
