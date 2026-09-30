# 21. Xử lý tiếng nói âm thanh và tín hiệu số

**Nhóm:** AI · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Sampling và Nyquist.
2. FFT và phổ.
3. Bộ lọc FIR IIR.
4. Windowing.
5. Feature âm thanh MFCC.
6. Speech recognition.
7. Noise và signal-to-noise.
8. Đánh giá WER.
9. Real-time buffer.

## Giảng nhanh

Sampling 8 kHz chỉ diễn tả tần số dưới khoảng 4 kHz trước khi lọc chống alias. FFT cho biết thành phần tần số trong một đoạn tín hiệu, nhưng độ phân giải thời gian/tần số phụ thuộc độ dài cửa sổ. Nếu làm cảnh báo còi xe, tiếng ồn nền và mức âm thanh khác nhau rất quan trọng.

## Bài tập ngắn

1. Vẽ phổ của sin 200 Hz và 400 Hz.
2. Thử đổi sampling rate và chỉ ra alias ở tần số vượt ngưỡng.

## Project portfolio: Nhận biết tiếng bíp cảnh báo đơn giản

**Các bước thực hiện:**

1. Sinh 20 âm thanh ngắn gồm tiếng bíp và nhiễu.
2. Trích RMS và năng lượng một dải tần.
3. Chọn ngưỡng trên tập phát triển rồi khóa ngưỡng.
4. Đo false positive false negative ở mức nhiễu khác nhau.
5. Vẽ phổ hai ví dụ và giải thích lỗi.

**Kiểm tra kết quả:**

- Có đơn vị sampling rate và dải tần.
- Đánh giá trên file chưa dùng để chọn ngưỡng.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Dữ liệu âm thanh tự sinh không cần micro

## Học sâu từ tài liệu gốc

- [SciPy Signal](https://docs.scipy.org/doc/scipy/reference/signal.html)
- [CS2023 AI](https://csed.acm.org/knowledge-areas/)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
