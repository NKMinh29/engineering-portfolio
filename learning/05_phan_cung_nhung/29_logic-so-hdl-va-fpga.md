# 29. Logic số HDL và FPGA

**Nhóm:** Phần cứng & nhúng · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Boolean và cổng logic.
2. Mạch tổ hợp.
3. Flip-flop thanh ghi.
4. FSM.
5. Timing setup hold.
6. Verilog module testbench.
7. Simulation waveform.
8. Synthesis và LUT FPGA.
9. Clock domain crossing.

## Giảng nhanh

Verilog mô tả cấu trúc và hành vi mạch; `always` theo cạnh clock mô tả thay đổi trạng thái đồng bộ, còn logic tổ hợp phải trả output cho mọi trường hợp. Một FSM có state và điều kiện chuyển; cần reset xác định để tránh trạng thái khởi động không biết.

## Bài tập ngắn

1. Viết bảng chân trị full adder.
2. Tạo FSM ba trạng thái đèn giao thông và đo trường hợp reset.

## Project portfolio: Bộ phát hiện chuỗi bit bằng Verilog

**Các bước thực hiện:**

1. Định nghĩa chuỗi 1011 và hành vi overlap.
2. Vẽ FSM Moore hoặc Mealy rồi lập bảng chuyển.
3. Viết module RTL và testbench ít nhất sáu chuỗi.
4. Chạy mô phỏng waveform trên nền tảng web hoặc tool đã có.
5. Ghi điểm khác nhau khi reset đồng bộ và bất đồng bộ.

**Kiểm tra kết quả:**

- Testbench có cả chuỗi overlap và không có mẫu.
- Waveform khớp bảng chuyển trạng thái.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** HDLBits và Wokwi trong trình duyệt; không cần mua FPGA

## Học sâu từ tài liệu gốc

- [HDLBits](https://hdlbits.01xz.net/wiki/Main_Page)
- [Tiny Tapeout Digital Design](https://tinytapeout.com/digital_design/)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
