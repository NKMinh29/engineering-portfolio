# 24. MLOps đánh giá mô hình và quản trị dữ liệu

**Nhóm:** AI · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Version dữ liệu model code.
2. Reproducible training.
3. Feature pipeline.
4. Registry và provenance.
5. Experiment tracking.
6. Deployment và rollback.
7. Monitoring drift.
8. Privacy và fairness.
9. Model card và tài liệu giới hạn.

## Giảng nhanh

Nếu model A tốt hơn B trong notebook nhưng không biết dữ liệu, seed và mã của lần chạy, kết luận khó kiểm chứng. MLOps biến phép đo thành quy trình tái lập: khóa phiên bản dữ liệu, ghi cấu hình huấn luyện và lưu metric trước khi thay model đang phục vụ.

## Bài tập ngắn

1. Viết model card một trang cho detector CAN.
2. Định nghĩa điều kiện rollback khi false positive tăng.

## Project portfolio: Quy trình benchmark có thể tái lập

**Các bước thực hiện:**

1. Lấy project 17 hoặc 18 làm baseline.
2. Tạo file config cho seed chia tập và hyperparameter.
3. Lưu metric theo run vào CSV và model artifact có hash.
4. Tạo script so sánh bản mới với baseline.
5. Viết báo cáo drift giả lập khi phân bố input thay đổi.

**Kiểm tra kết quả:**

- Người khác chạy lại ra bảng cùng cấu trúc.
- Không chọn model dựa trên tập test đã xem nhiều lần.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Colab hoặc Python Windows và dữ liệu nhỏ

## Học sâu từ tài liệu gốc

- [Google ML Production](https://developers.google.com/machine-learning/crash-course/production-ml-systems)
- [PyTorch Tutorials](https://docs.pytorch.org/tutorials/)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
