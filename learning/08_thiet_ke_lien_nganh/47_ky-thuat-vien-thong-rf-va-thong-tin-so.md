# 47. Kỹ thuật viễn thông RF và thông tin số

**Nhóm:** Thiết kế & liên ngành · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Tần số bước sóng dB.
2. Modulation.
3. Noise và SNR.
4. BER.
5. Link budget.
6. Antenna gain.
7. LoRa và Wi-Fi.
8. Spectrum regulations ở mức nhận biết.
9. Interference.
10. Protocol framing.

## Giảng nhanh

dB là thang log; cộng gain/loss theo dB thuận tiện cho link budget, nhưng phải phân biệt dBm công suất tuyệt đối và dB tỷ số. Nhiễu và vật cản làm link radio kém đi; không thể suy ra khoảng cách thật chỉ từ thông số nhà sản xuất. Mô phỏng giúp đặt giả thiết trước khi đo thực.

## Bài tập ngắn

1. Cộng một link budget gồm công suất phát gain antenna và hai suy hao.
2. Vẽ BER khi SNR tăng theo một mô hình đồ chơi.

## Project portfolio: Bảng tính link budget có giả thiết

**Các bước thực hiện:**

1. Định nghĩa các đầu vào công suất phát dBm gain suy hao và ngưỡng thu.
2. Viết script hoặc spreadsheet tính margin.
3. Tạo 3 môi trường với suy hao giả định nêu nguồn hoặc ghi là giả thiết.
4. Vẽ độ nhạy margin theo khoảng cách.
5. Giải thích bước đo thật cần làm khi đã có LoRa.

**Kiểm tra kết quả:**

- Đơn vị dB dBm không bị cộng sai.
- Mọi số giả định được đánh dấu.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Bảng tính hoặc Python; không cần thiết bị phát sóng

## Học sâu từ tài liệu gốc

- [HUST Electronics Telecom](https://ts.hust.edu.vn/training-cate/nganh-dao-tao-dai-hoc/dien-tu-va-vien-thong)
- [MQTT Overview](https://mqtt.org/)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
