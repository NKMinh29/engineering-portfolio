# 06. Nền tảng IoT theo dõi đội robot/thiết bị

**Tên repo đề xuất:** `fleet-telemetry-console`  
**Ưu tiên:** P1/P2 — chọn nếu muốn mở rộng web từ automotive  
**Năng lực:** IoT, backend, frontend, database, data engineering, DevOps  
**Ước lượng lập kế hoạch:** 40–70 giờ. Không phải cam kết; chưa tính toàn bộ thời gian học nền tảng.

> Trạng thái: bản thiết kế. Prototype CAN Log Workbench được chuẩn bị riêng; các sản phẩm khác cần triển khai hoặc nhập artifact gốc. Tiêu chí nghiệm thu là mục tiêu, chưa phải kết quả đã đạt.

## 1. Người dùng và bài toán

Một lab có nhiều robot/ECU cần xem trạng thái thiết bị, lịch sử cảnh báo và chất lượng dữ liệu ở một màn hình.

## 2. MVP — phiên bản nhỏ nhất đủ demo

- Ba thiết bị giả lập gửi telemetry; ingest API kiểm tra schema và lưu SQLite.
- Dashboard danh sách thiết bị, online/stale, biểu đồ và alarm history.
- Replay theo timestamp, khử trùng lặp message; xuất báo cáo CSV.

## 3. Kiến trúc và hợp đồng dữ liệu

Device simulator → ingest API → validation/dedup → SQLite → query API → web dashboard. MQTT adapter và PostgreSQL là mở rộng khi có nhu cầu concurrency.

**Hợp đồng:** Telemetry {device_id, session_id, sequence, measured_at, received_at, temperature_c, voltage_v, status}; khóa chống trùng (device_id, session_id, sequence). measured_at và received_at tách biệt để thấy dữ liệu đến muộn.

## 4. Công cụ và môi trường

Python FastAPI + SQLite + HTML/JavaScript giai đoạn đầu, Windows. React, broker và Docker là tùy chọn sau MVP; không cài tất cả ngay.

## 5. Cấu trúc repo đề xuất

- `simulator/`: seed cố định và lỗi mạng
- `api/`: ingest/query
- `storage/`: schema/migrations
- `web/`: dashboard
- `tests/`: duplicate, late data, stale

## 6. Milestones để chuyển thành GitHub Issues

1. Vẽ 3 màn hình và xác định API tối thiểu.
2. Viết simulator tạo dữ liệu gắn nhãn synthetic.
3. Tạo database constraint, ingest và idempotency test.
4. Thêm dashboard và status stale theo received_at.
5. Replay lỗi mất mạng/duplicate; lưu cách khôi phục.
6. Đo ingestion rate, query latency và dung lượng trên máy ghi rõ cấu hình.

Mỗi milestone là một issue cha; tách task chỉ khi đủ nhỏ để có output và cách kiểm tra trong một buổi làm. Commit theo thay đổi thật, không tạo lịch sử đóng góp giả.

## 7. Nghiệm thu

- Gửi cùng message hai lần không tạo hai record.
- Thiết bị không gửi quá timeout chuyển stale.
- API từ chối dữ liệu sai unit/range theo schema.
- Có backup/restore demo và log số record trước/sau.

## 8. Bằng chứng đưa lên portfolio

Ba thiết bị, một node mất mạng rồi gửi bù; dashboard thể hiện cả thời gian đo và thời gian nhận.

README cần: bài toán → demo → cách chạy → kiến trúc → kết quả đo → hạn chế → phần đóng góp của Minh → nguồn và license. Số đo phải gắn thiết bị/cấu hình/dataset; không đặt badge test pass trước khi có workflow chạy thật.

## 9. Giảng nhanh

Idempotency nghĩa là thực hiện lại một request không làm thay đổi kết quả thêm lần nữa. Nó cần thiết khi thiết bị retry sau lỗi mạng.

## 10. Phạm vi và bước tiếp theo

Dữ liệu giả lập đủ cho MVP. Xác thực thiết bị và phân quyền là điều kiện của bản dùng ngoài local demo; chưa cần đa tenant hoặc Kubernetes.

## Tài liệu gốc

- FastAPI tutorial — https://fastapi.tiangolo.com/tutorial/

Tình trạng kiểm tra liên kết ghi trong `../NGUON_VA_PHAM_VI.md`. Tài liệu là điểm bắt đầu học; thiết kế MVP và nghiệm thu ở đây là đề xuất riêng cho portfolio của Minh.
