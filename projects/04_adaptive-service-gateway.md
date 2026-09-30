# 04. Gateway dịch vụ để học kiến trúc Adaptive

**Tên repo đề xuất:** `adaptive-service-gateway`  
**Ưu tiên:** P2 — sau Classic và networking  
**Năng lực:** C++, service-oriented architecture, Adaptive concepts, distributed systems  
**Ước lượng lập kế hoạch:** 35–60 giờ. Không phải cam kết; chưa tính toàn bộ thời gian học nền tảng.

> Trạng thái: bản thiết kế. Prototype CAN Log Workbench được chuẩn bị riêng; các sản phẩm khác cần triển khai hoặc nhập artifact gốc. Tiêu chí nghiệm thu là mục tiêu, chưa phải kết quả đã đạt.

## 1. Người dùng và bài toán

Một ứng dụng chẩn đoán cần đọc trạng thái xe qua dịch vụ và xử lý lúc producer biến mất hoặc khởi động lại.

## 2. MVP — phiên bản nhỏ nhất đủ demo

- Producer giả lập VehicleState, gateway kiểm tra freshness, consumer hiển thị trạng thái.
- Service contract có version và trạng thái unavailable/stale.
- Lifecycle startup/shutdown, health report và retry có giới hạn.

## 3. Kiến trúc và hợp đồng dữ liệu

Telemetry source → service adapter → VehicleState service → consumer. Supervisor quản lý process; persistency lưu cấu hình nhỏ. Transport host đơn giản trước, SOME/IP hoặc ara::com adapter sau nếu có stack phù hợp.

**Hợp đồng:** VehicleState {schema_version, source_id, sequence, timestamp_ms, speed_kph, light_mode, quality}. Mất dữ liệu phải trả quality=stale, không tự điền tốc độ 0 làm người dùng hiểu nhầm.

## 4. Công cụ và môi trường

Host prototype C++ có thể chạy trên Windows; nghiên cứu runtime Adaptive/POSIX thực tế ở máy lab hoặc máy Linux từ xa. Không coi HTTP prototype là AUTOSAR Adaptive runtime.

## 5. Cấu trúc repo đề xuất

- `contracts/`: schema và compatibility rules
- `producer/`: nguồn dữ liệu mẫu
- `gateway/`: validation và caching
- `consumer/`: client demo
- `supervisor/`: lifecycle
- `docs/`: concept-to-implementation mapping

## 6. Milestones để chuyển thành GitHub Issues

1. Định nghĩa timeout, error model và yêu cầu version.
2. Viết producer/consumer host với test clock.
3. Thêm restart và stale detection; kiểm tra sequence reset theo session.
4. Đo latency trong điều kiện network delay nhân tạo.
5. Đọc architecture Adaptive rồi viết bảng phần nào đã làm/phần nào chưa.
6. Chỉ tích hợp ara::com khi chốt runtime và license.

Mỗi milestone là một issue cha; tách task chỉ khi đủ nhỏ để có output và cách kiểm tra trong một buổi làm. Commit theo thay đổi thật, không tạo lịch sử đóng góp giả.

## 7. Nghiệm thu

- Consumer phát hiện producer dừng, hiển thị stale theo thời gian đã cấu hình.
- Restart không nhầm sequence cũ thành dữ liệu mới.
- Schema không tương thích bị từ chối rõ ràng.
- Log có request/session ID để truy vết qua các process.

## 8. Bằng chứng đưa lên portfolio

Dừng producer, restart gateway, đổi schema; client vẫn hiển thị trạng thái hợp lý.

README cần: bài toán → demo → cách chạy → kiến trúc → kết quả đo → hạn chế → phần đóng góp của Minh → nguồn và license. Số đo phải gắn thiết bị/cấu hình/dataset; không đặt badge test pass trước khi có workflow chạy thật.

## 9. Giảng nhanh

Service contract gồm cả dữ liệu thành công, lỗi và vòng đời. Khi các process khởi động độc lập, phải thiết kế timeout, retry và tương thích phiên bản ngay từ đầu.

## 10. Phạm vi và bước tiếp theo

Giá trị portfolio ở kiến trúc, failure handling và mapping tiêu chuẩn. Không đặt badge chứng nhận AUTOSAR cho prototype.

## Tài liệu gốc

- AUTOSAR Standards — https://www.autosar.org/standards
- Adaptive working groups — https://www.autosar.org/working-groups/adaptive-platform

Tình trạng kiểm tra liên kết ghi trong `../NGUON_VA_PHAM_VI.md`. Tài liệu là điểm bắt đầu học; thiết kế MVP và nghiệm thu ở đây là đề xuất riêng cho portfolio của Minh.
