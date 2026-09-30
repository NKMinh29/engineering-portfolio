# 30. Vi mạch bán dẫn và thiết kế IC

**Nhóm:** Phần cứng & nhúng · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Transistor MOS và CMOS.
2. Standard cell.
3. RTL verification.
4. Synthesis.
5. Static timing analysis.
6. Floorplan placement routing.
7. PDK và DRC LVS.
8. Power area performance.
9. Thiết kế analog và fabrication ở mức khái niệm.

## Giảng nhanh

Thiết kế IC số thường đi từ RTL tới netlist cổng, rồi tới layout vật lý và kiểm tra timing/quy tắc chế tạo. Vẽ PCB kết nối chip thương mại ở ngoài chip; tapeout tạo dữ liệu sản xuất bên trong chip. Bài đầu nên là mạch logic nhỏ và simulation, chưa đòi tự chế tạo.

## Bài tập ngắn

1. Phân loại yêu cầu 10 ns thành yêu cầu timing không phải độ chính xác.
2. Vẽ pipeline RTL → synthesis → place-route → GDS.

## Project portfolio: Mạch đếm sự kiện 8-bit mô phỏng

**Các bước thực hiện:**

1. Viết đặc tả input clock reset enable và output count.
2. Viết RTL testbench cho rollover 255 về 0.
3. Mô phỏng và lưu waveform.
4. Đọc báo cáo synthesis của một luồng học tập khi có quyền truy cập.
5. Viết báo cáo phân biệt giả định mô phỏng với đặc tính silicon thật.

**Kiểm tra kết quả:**

- Testbench kiểm thử reset enable rollover.
- Không tuyên bố đã sản xuất chip chỉ vì RTL chạy.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** HDLBits hoặc môi trường web; bước physical design để sau khi có máy lab

## Học sâu từ tài liệu gốc

- [Tiny Tapeout Making ASICs](https://tinytapeout.com/making_asics/)
- [Nand2Tetris Hardware](https://www.nand2tetris.org/course)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
