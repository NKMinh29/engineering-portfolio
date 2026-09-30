# 15. Giao diện vận hành robot và bộ thiết kế đồ họa

**Tên repo đề xuất:** `robot-ops-design-system`  
**Ưu tiên:** P2/P3 — ghép với repo fleet/robot  
**Năng lực:** UI/UX, graphic design, accessibility, frontend, 3D optional  
**Ước lượng lập kế hoạch:** 20–40 giờ. Không phải cam kết; chưa tính toàn bộ thời gian học nền tảng.

> Trạng thái: bản thiết kế. Prototype CAN Log Workbench được chuẩn bị riêng; các sản phẩm khác cần triển khai hoặc nhập artifact gốc. Tiêu chí nghiệm thu là mục tiêu, chưa phải kết quả đã đạt.

## 1. Người dùng và bài toán

Người vận hành cần nhận ra robot mất kết nối, cảnh báo và tác vụ đang làm mà không chỉ dựa vào màu sắc hoặc biểu đồ dày đặc.

## 2. MVP — phiên bản nhỏ nhất đủ demo

- Bộ token màu/type/spacing; component status, alert, telemetry card và mission list.
- Ba màn hình có trạng thái loading, empty, stale, error và normal.
- Prototype HTML tương tác + case study quyết định thiết kế; bộ SVG do bạn tự tạo.

## 3. Kiến trúc và hợp đồng dữ liệu

Design tokens → accessible components → page states → scenario replay. UI nhận JSON fixture cùng schema với fleet console để có thể nối backend sau.

**Hợp đồng:** RobotView {id, connectivity, mission_state, battery_pct, last_seen, alerts}; connectivity và operational state là hai trường riêng. Mọi trạng thái có text/icon bên cạnh màu.

## 4. Công cụ và môi trường

HTML/CSS/JavaScript chạy trình duyệt; công cụ thiết kế vector tùy bạn. Blender/3D chỉ là extension sau khi UI có use case rõ.

## 5. Cấu trúc repo đề xuất

- `tokens/`: JSON/CSS variables
- `components/`: reusable HTML/CSS
- `screens/`: layouts
- `fixtures/`: scenarios
- `case-study/`: problem, iteration, feedback
- `assets/`: SVG source

## 6. Milestones để chuyển thành GitHub Issues

1. Chọn 3 task: tìm robot lỗi, xem lý do, xác định thao tác tiếp theo.
2. Vẽ wireframe và luồng trạng thái.
3. Thiết kế component với contrast và keyboard focus.
4. Làm prototype bằng dữ liệu JSON.
5. Cho 3 người thực hiện task, ghi thời gian/lỗi và sửa.
6. Tạo case study trước/sau kèm giới hạn mẫu thử.

Mỗi milestone là một issue cha; tách task chỉ khi đủ nhỏ để có output và cách kiểm tra trong một buổi làm. Commit theo thay đổi thật, không tạo lịch sử đóng góp giả.

## 7. Nghiệm thu

- Dùng bàn phím truy cập các thao tác chính.
- Trạng thái stale không trông giống healthy chỉ vì giá trị số còn hiển thị.
- 3 task có kết quả usability thật hoặc ghi rõ chưa thử.
- SVG, token và component nguồn được commit; không chỉ có ảnh chụp.

## 8. Bằng chứng đưa lên portfolio

Chuyển fixture từ normal sang mất kết nối và xem UI phản ứng; trình bày một vòng sửa theo feedback.

README cần: bài toán → demo → cách chạy → kiến trúc → kết quả đo → hạn chế → phần đóng góp của Minh → nguồn và license. Số đo phải gắn thiết bị/cấu hình/dataset; không đặt badge test pass trước khi có workflow chạy thật.

## 9. Giảng nhanh

Một design system hữu ích mô tả cả trạng thái và hành vi. Token giúp đổi diện mạo nhất quán, còn case study chứng minh quyết định thiết kế có lý do.

## 10. Phạm vi và bước tiếp theo

Không bắt buộc tạo repo riêng nếu chỉ có vài màn hình cho fleet console; khi có component dùng lại và case study độc lập mới tách.

## Tài liệu gốc

- MDN accessibility — https://developer.mozilla.org/en-US/docs/Web/Accessibility

Tình trạng kiểm tra liên kết ghi trong `../NGUON_VA_PHAM_VI.md`. Tài liệu là điểm bắt đầu học; thiết kế MVP và nghiệm thu ở đây là đề xuất riêng cho portfolio của Minh.
