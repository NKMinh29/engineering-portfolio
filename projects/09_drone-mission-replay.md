# 09. Phân tích và phát lại nhiệm vụ drone

**Tên repo đề xuất:** `drone-mission-replay`  
**Ưu tiên:** P2 — trước SITL hoặc bay thật  
**Năng lực:** Drone, MAVLink concepts, GIS, telemetry, control  
**Ước lượng lập kế hoạch:** 25–45 giờ. Không phải cam kết; chưa tính toàn bộ thời gian học nền tảng.

> Trạng thái: bản thiết kế. Prototype CAN Log Workbench được chuẩn bị riêng; các sản phẩm khác cần triển khai hoặc nhập artifact gốc. Tiêu chí nghiệm thu là mục tiêu, chưa phải kết quả đã đạt.

## 1. Người dùng và bài toán

Người học cần nhìn lại quỹ đạo, thời gian mất dữ liệu và vi phạm geofence từ một mission, trước khi viết autopilot.

## 2. MVP — phiên bản nhỏ nhất đủ demo

- CSV telemetry có tọa độ, altitude, speed, battery và timestamp.
- Map/viewer replay, timeline và cảnh báo ra khỏi geofence.
- Báo cáo khoảng trống dữ liệu và sai khác kế hoạch/thực tế nếu có waypoint.

## 3. Kiến trúc và hợp đồng dữ liệu

CSV replay → unit/frame normalization → mission checks → timeline/map. Adapter MAVLink/ULog là phần tiếp theo sau khi xác định format cụ thể.

**Hợp đồng:** Record {time_s, latitude_deg, longitude_deg, altitude_m, altitude_reference, speed_mps, battery_pct}; altitude_reference bắt buộc vì relative altitude và MSL không thể trộn trực tiếp.

## 4. Công cụ và môi trường

Python + HTML/JavaScript trên Windows; dữ liệu synthetic và map phẳng local trước, không cần simulator nặng.

## 5. Cấu trúc repo đề xuất

- `parsers/`: CSV rồi adapter
- `mission/`: waypoint/geofence
- `analysis/`: gaps và summary
- `web/`: replay
- `fixtures/`: synthetic missions

## 6. Milestones để chuyển thành GitHub Issues

1. Thiết kế mission hình chữ nhật bằng tọa độ local mét.
2. Viết kiểm tra point-in-polygon và boundary policy.
3. Thêm timestamp gaps, battery missing và speed outlier.
4. Render play/pause/speed và mốc cảnh báo.
5. Nhập log có provenance được phép dùng.
6. SITL trên máy phù hợp là mốc tiếp theo.

Mỗi milestone là một issue cha; tách task chỉ khi đủ nhỏ để có output và cách kiểm tra trong một buổi làm. Commit theo thay đổi thật, không tạo lịch sử đóng góp giả.

## 7. Nghiệm thu

- Điểm trên biên geofence có quy tắc nhất quán và test.
- Gaps được đánh dấu, không nội suy rồi coi là dữ liệu thật.
- Nhật ký nêu hệ tọa độ, đơn vị và nguồn altitude.
- Replay cùng file tạo cùng danh sách sự kiện.

## 8. Bằng chứng đưa lên portfolio

Mission synthetic rời geofence một lần, mất telemetry 3 giây; timeline cho phép bấm vào từng sự kiện.

README cần: bài toán → demo → cách chạy → kiến trúc → kết quả đo → hạn chế → phần đóng góp của Minh → nguồn và license. Số đo phải gắn thiết bị/cấu hình/dataset; không đặt badge test pass trước khi có workflow chạy thật.

## 9. Giảng nhanh

Latitude/longitude là góc, không phải khoảng cách mét. Với lab nhỏ có thể dùng frame local đã định nghĩa; muốn xử lý khu vực lớn phải dùng phép chiếu phù hợp.

## 10. Phạm vi và bước tiếp theo

Đây là công cụ phân tích offline; không gửi lệnh bay. Không cần mua drone để hoàn thành MVP.

## Tài liệu gốc

- MAVLink guide — https://mavlink.io/en/guide/overview.html

Tình trạng kiểm tra liên kết ghi trong `../NGUON_VA_PHAM_VI.md`. Tài liệu là điểm bắt đầu học; thiết kế MVP và nghiệm thu ở đây là đề xuất riêng cho portfolio của Minh.
