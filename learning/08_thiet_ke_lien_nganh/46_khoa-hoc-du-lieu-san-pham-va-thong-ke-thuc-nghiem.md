# 46. Khoa học dữ liệu sản phẩm và thống kê thực nghiệm

**Nhóm:** Thiết kế & liên ngành · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. KPI và câu hỏi nghiên cứu.
2. Sampling.
3. Hypothesis và confidence interval.
4. A/B test.
5. Confounding.
6. Time series.
7. Change-point.
8. Dashboard trung thực.
9. Causal claim và giới hạn.
10. Báo cáo dữ liệu.

## Giảng nhanh

So sánh trước sau một bản cập nhật không tự chứng minh bản cập nhật gây thay đổi; còn có tải khác nhau hoặc thời tiết. Trong CAN IDS, so sánh thời gian inference cần kiểm soát clock input tải timer và cấu hình firmware. Một biểu đồ tốt luôn ghi đơn vị cỡ mẫu và đường cơ sở.

## Bài tập ngắn

1. Tạo 10 phép đo và tính trung vị cùng khoảng biến thiên.
2. Nêu ba biến nhiễu khi so hai thuật toán trên MCU.

## Project portfolio: Báo cáo thực nghiệm có thể tái lập

**Các bước thực hiện:**

1. Chọn một biến đo của project đã có như latency.
2. Viết hypothesis protocol số lần lặp và cách thu log.
3. Thu hoặc tạo bộ mẫu ghi rõ nguồn và seed.
4. Vẽ phân bố baseline và biến thể kèm đơn vị n.
5. Viết kết luận giới hạn không suy rộng ngoài thiết lập.

**Kiểm tra kết quả:**

- Có raw data và script sinh mọi biểu đồ.
- Nhận định trong báo cáo không vượt quá thiết kế thí nghiệm.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Python notebook và log nhỏ có sẵn

## Học sâu từ tài liệu gốc

- [Google ML Crash Course](https://developers.google.com/machine-learning/crash-course)
- [SciPy Stats](https://docs.scipy.org/doc/scipy/reference/stats.html)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
