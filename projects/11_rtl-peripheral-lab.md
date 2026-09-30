# 11. IP số UART, FIFO và PWM có testbench

**Tên repo đề xuất:** `rtl-peripheral-lab`  
**Ưu tiên:** P2 — cửa vào FPGA/IC số  
**Năng lực:** Verilog/SystemVerilog, digital design, verification, FPGA, IC flow  
**Ước lượng lập kế hoạch:** 35–65 giờ. Không phải cam kết; chưa tính toàn bộ thời gian học nền tảng.

> Trạng thái: bản thiết kế. Prototype CAN Log Workbench được chuẩn bị riêng; các sản phẩm khác cần triển khai hoặc nhập artifact gốc. Tiêu chí nghiệm thu là mục tiêu, chưa phải kết quả đã đạt.

## 1. Người dùng và bài toán

Cần một IP ngoại vi nhỏ có spec rõ và testbench tự kiểm tra để học luồng thiết kế phần cứng số.

## 2. MVP — phiên bản nhỏ nhất đủ demo

- FIFO đồng bộ depth cấu hình được với full/empty và policy overflow.
- UART TX đơn giản và PWM, ghép sau khi FIFO có test hoàn chỉnh.
- Testbench tự so scoreboard; waveform và synthesis report nếu đã chạy.

## 3. Kiến trúc và hợp đồng dữ liệu

Register interface → FIFO → UART TX; PWM độc lập. Dùng một clock domain cho MVP để tránh đưa CDC chưa kiểm chứng vào thiết kế.

**Hợp đồng:** Chốt width, depth, reset polarity, synchronous/asynchronous reset, read latency và hành vi read/write đồng thời. Reset và overflow là một phần spec.

## 4. Công cụ và môi trường

HDL source + simulator nhẹ nếu có bản tương thích Windows; chạy simulation/synthesis trên máy lab hoặc CI khi cần. Không cài full EDA backend ASIC ngay.

## 5. Cấu trúc repo đề xuất

- `rtl/`: module
- `tb/`: stimulus và scoreboard
- `spec/`: timing/interface
- `constraints/`: giả định clock
- `reports/`: phiên bản tool, commands, results

## 6. Milestones để chuyển thành GitHub Issues

1. Vẽ waveform mong muốn cho 6 trường hợp FIFO.
2. Viết FIFO và scoreboard độc lập.
3. Kiểm tra wraparound, reset giữa chừng và read/write đồng thời.
4. Thêm UART TX rồi test decode bit stream.
5. Synthesis với constraints rõ, lưu warning và resource report.
6. Physical design thử nghiệm là mốc sau với PDK được phép dùng.

Mỗi milestone là một issue cha; tách task chỉ khi đủ nhỏ để có output và cách kiểm tra trong một buổi làm. Commit theo thay đổi thật, không tạo lịch sử đóng góp giả.

## 7. Nghiệm thu

- Testbench tự fail khi output sai; seed và simulator command được lưu.
- Không mất/lặp byte qua FIFO ở suite random có seed.
- UART timing được so theo baud divisor trong spec.
- Synthesis result không được trình bày như kết quả silicon đã chế tạo.

## 8. Bằng chứng đưa lên portfolio

Waveform một packet đi qua FIFO/UART và log scoreboard pass; giải thích một bug tìm được.

README cần: bài toán → demo → cách chạy → kiến trúc → kết quả đo → hạn chế → phần đóng góp của Minh → nguồn và license. Số đo phải gắn thiết bị/cấu hình/dataset; không đặt badge test pass trước khi có workflow chạy thật.

## 9. Giảng nhanh

Simulation kiểm tra hành vi theo stimulus; synthesis biến mô tả thành phần tử logic. Timing closure và silicon validation là các mốc khác, không thể suy ra chỉ từ testbench pass.

## 10. Phạm vi và bước tiếp theo

Repo số chưa bao phủ analog IC, RF IC hoặc fabrication process; các chuyên đề đó có bài tập riêng trong learning atlas.

## Tài liệu gốc

- Yosys documentation — https://yosyshq.readthedocs.io/projects/yosys/en/latest/

Tình trạng kiểm tra liên kết ghi trong `../NGUON_VA_PHAM_VI.md`. Tài liệu là điểm bắt đầu học; thiết kế MVP và nghiệm thu ở đây là đề xuất riêng cho portfolio của Minh.
