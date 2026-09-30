# 17. Machine learning và khoa học dữ liệu

**Nhóm:** AI · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Thu thập gán nhãn.
2. Features và target.
3. Train validation test.
4. Regression classification.
5. Decision tree và linear model.
6. Imbalance precision recall.
7. Cross validation.
8. Leakage và drift.
9. Baseline và reproducibility.

## Giảng nhanh

ML học quy luật từ dữ liệu ví dụ để dự đoán mẫu mới. Đặt một baseline đơn giản trước khi dùng mạng sâu: trên CAN IDS, luật ngưỡng rất nhanh nhưng có thể không biểu diễn tương tác phức tạp; số liệu kiểm tra phải phản ánh mức độ hữu ích và chi phí chạy của từng model.

## Bài tập ngắn

1. Tính confusion matrix với 20 tấn công trong 1000 mẫu.
2. Tìm 3 cách dữ liệu test rò rỉ vào train.

## Project portfolio: So sánh hai detector trên dữ liệu có nguồn rõ

**Các bước thực hiện:**

1. Chọn bộ dữ liệu mở hoặc tạo dữ liệu tổng hợp với seed.
2. Chia tập theo phiên thu thập để giảm leakage.
3. Huấn luyện threshold baseline và cây quyết định.
4. Báo precision recall F1 và confusion matrix cho từng tập.
5. Lưu kết quả và mô tả giới hạn do dữ liệu tổng hợp nếu có.

**Kiểm tra kết quả:**

- Tập test không được dùng để chọn threshold.
- README ghi rõ dữ liệu thực hay mô phỏng.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Google Colab hoặc Python nhỏ trên Windows

## Học sâu từ tài liệu gốc

- [Google ML Crash Course](https://developers.google.com/machine-learning/crash-course)
- [PyTorch Basics](https://docs.pytorch.org/tutorials/beginner/basics/intro)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
