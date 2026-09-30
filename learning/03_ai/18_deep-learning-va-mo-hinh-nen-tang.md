# 18. Deep learning và mô hình nền tảng

**Nhóm:** AI · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Tensor và autograd.
2. Dense CNN attention.
3. Loss optimizer và learning rate.
4. Batch và epoch.
5. Regularization.
6. Transfer learning.
7. Model size và throughput.
8. Evaluation calibration.
9. Phiên bản mô hình dữ liệu.

## Giảng nhanh

Mạng nơ ron gồm các phép biến đổi tham số; quá trình học cập nhật trọng số nhờ gradient của hàm lỗi. Kiến trúc nhiều lớp không tự bảo đảm kết quả tốt; cần baseline, dữ liệu đại diện và ngân sách suy luận. Trong embedded, hãy tách thời gian tiền xử lý và thời gian inference để so sánh công bằng.

## Bài tập ngắn

1. Tính số tham số của MLP 10–32–32–1 đã dùng trong nghiên cứu.
2. Vẽ đồ thị train và validation loss để nhận ra overfitting.

## Project portfolio: MLP nhỏ có phép đo tài nguyên

**Các bước thực hiện:**

1. Tạo bộ dữ liệu số 10 feature và baseline logistic.
2. Huấn luyện MLP với seed và lịch sử loss.
3. Tính tham số kích thước file và thời gian dự đoán CPU.
4. Đánh giá trên tập test chưa dùng lúc chọn hyperparameter.
5. So sánh với baseline rồi nêu được mất.

**Kiểm tra kết quả:**

- Kết quả chạy lại với sai số nhỏ.
- Có thời gian suy luận và kích thước model đo thực tế.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Colab CPU đủ cho bộ dữ liệu nhỏ; không tải model hàng GB

## Học sâu từ tài liệu gốc

- [PyTorch Basics](https://docs.pytorch.org/tutorials/beginner/basics/intro)
- [Google ML Crash Course](https://developers.google.com/machine-learning/crash-course)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
