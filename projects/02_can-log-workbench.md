# 02. Công cụ phân tích log CAN dùng trên PC

**Tên repo đề xuất:** `can-log-workbench`  
**Ưu tiên:** P0 — demo nhỏ có sẵn trong bản prototype  
**Năng lực:** Python, data analysis, CLI, frontend nhẹ, automotive tooling  
**Ước lượng lập kế hoạch:** 12–24 giờ để mở rộng từ demo hiện có. Không phải cam kết; chưa tính toàn bộ thời gian học nền tảng.

> Trạng thái: bản thiết kế. Prototype CAN Log Workbench được chuẩn bị riêng; các sản phẩm khác cần triển khai hoặc nhập artifact gốc. Tiêu chí nghiệm thu là mục tiêu, chưa phải kết quả đã đạt.

## 1. Người dùng và bài toán

Sinh viên cần biết log CAN có bao nhiêu ID, chu kỳ quan sát của từng ID và bản ghi nào sai định dạng, trước khi mở công cụ phức tạp.

## 2. MVP — phiên bản nhỏ nhất đủ demo

- Nhập CSV có timestamp_us, can_id, dlc, data; kiểm tra Classic CAN 11-bit.
- Bảng theo ID: số frame, tổng payload byte, khoảng thời gian giữa bản ghi liên tiếp.
- Xuất JSON và báo cáo HTML mở offline; ghi rõ sample tổng hợp hay dữ liệu thực.

## 3. Kiến trúc và hợp đồng dữ liệu

CSV → parser nghiêm ngặt → danh sách frame chuẩn hóa → aggregator theo ID → JSON + HTML. Bản demo trong bản prototype chỉ dùng Python standard library.

**Hợp đồng:** timestamp_us là số nguyên không âm, toàn file không giảm; can_id là hexadecimal 000–7FF; DLC 0–8; data là các byte hex cách nhau bằng dấu cách, số byte bằng DLC. Chưa hỗ trợ CAN FD, extended ID hoặc remote frame.

## 4. Công cụ và môi trường

Python 3.10+ trên Windows; không cần pip cho demo. HTML dùng trình duyệt. Bản mở rộng có thể thêm adapter định dạng log theo file thật của bạn.

## 5. Cấu trúc repo đề xuất

- `analyze.py`: parser và CLI
- `sample.csv`: dữ liệu tổng hợp có nhãn
- `tests/`: trường hợp biên và lỗi input
- `README.md`: cách chạy và giới hạn
- `out/`: báo cáo sinh ra, không commit mặc định

## 6. Milestones để chuyển thành GitHub Issues

1. Chạy sample, tính tay khoảng thời gian ID 123 để đối chiếu báo cáo.
2. Viết adapter cho đúng định dạng xuất của công cụ CAN bạn dùng, giữ parser chuẩn làm lõi.
3. Thêm lọc khoảng thời gian và ID; viết test các biên.
4. Thêm biểu đồ timeline nếu có nhu cầu; đo thời gian và RAM trên log lớn.
5. Chụp màn hình báo cáo bằng log đã làm sạch và quay video hướng dẫn.

Mỗi milestone là một issue cha; tách task chỉ khi đủ nhỏ để có output và cách kiểm tra trong một buổi làm. Commit theo thay đổi thật, không tạo lịch sử đóng góp giả.

## 7. Nghiệm thu

- Input sai DLC/payload, ID ngoài 11-bit, timestamp giảm bị từ chối kèm số dòng.
- Test xác nhận khoảng thời gian được tính trong từng ID; timestamp bằng nhau được giữ với interval 0.
- Báo cáo chạy offline, không tải JS hoặc dữ liệu ngoài.
- Không suy ra bus utilization, mất frame hay realtime guarantee chỉ từ khoảng cách trong log.

## 8. Bằng chứng đưa lên portfolio

Sample 8 frame đã đóng gói. README có lệnh tạo HTML/JSON và chạy unittest; báo cáo mẫu kèm theo được sinh trong lần chuẩn bị này.

README cần: bài toán → demo → cách chạy → kiến trúc → kết quả đo → hạn chế → phần đóng góp của Minh → nguồn và license. Số đo phải gắn thiết bị/cấu hình/dataset; không đặt badge test pass trước khi có workflow chạy thật.

## 9. Giảng nhanh

Chu kỳ quan sát là hiệu hai timestamp liên tiếp của cùng ID. Nó khác thời gian xử lý trên MCU và khác thời gian frame chiếm đường truyền. Giữ tách ba đại lượng giúp báo cáo không kết luận quá dữ liệu.

## 10. Phạm vi và bước tiếp theo

Demo ban đầu đọc toàn file vào RAM, phù hợp log nhỏ. Streaming parser và dataset lớn là việc mở rộng. Đây là tool log riêng; không dùng nó thay decoder binary của bài IMCOM.

## Tài liệu gốc

- Python csv — https://docs.python.org/3/library/csv.html

Tình trạng kiểm tra liên kết ghi trong `../NGUON_VA_PHAM_VI.md`. Tài liệu là điểm bắt đầu học; thiết kế MVP và nghiệm thu ở đây là đề xuất riêng cho portfolio của Minh.
