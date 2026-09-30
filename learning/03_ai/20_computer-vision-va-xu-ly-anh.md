# 20. Computer vision và xử lý ảnh

**Nhóm:** AI · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Pixel color space và histogram.
2. Convolution filter edge.
3. Camera geometry.
4. Dataset và annotation.
5. Classification detection segmentation.
6. IoU precision recall.
7. Robustness ánh sáng.
8. Theo dõi đối tượng.
9. Quyền riêng tư hình ảnh.

## Giảng nhanh

Classification trả một nhãn cho ảnh; detection cho vị trí từng đối tượng; segmentation gán lớp lên từng pixel. Với ADAS, một mô hình phát hiện người đi bộ cần kiểm tra vị trí và trường hợp trời tối/che khuất chứ không chỉ accuracy tổng thể.

## Bài tập ngắn

1. Tính IoU của hai bounding box bằng tay.
2. Biến đổi độ sáng 5 ảnh và ghi thay đổi đầu ra thuật toán ngưỡng.

## Project portfolio: Phát hiện vật cản bằng ảnh mẫu

**Các bước thực hiện:**

1. Dùng 20–50 ảnh hợp pháp hoặc ảnh tự tạo.
2. Chú thích vị trí một loại vật cản nhỏ.
3. Làm baseline màu/cạnh rồi mới thử mô hình dựng sẵn.
4. Đánh giá IoU hoặc precision recall trên ảnh tách riêng.
5. Lưu hình lỗi tiêu biểu kèm giải thích.

**Kiểm tra kết quả:**

- Có ví dụ true positive false positive false negative.
- Ghi rõ ảnh tự thu hay nguồn dataset.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Dữ liệu ảnh nhỏ trên Colab; tránh tải toàn bộ dataset

## Học sâu từ tài liệu gốc

- [OpenCV Tutorials](https://docs.opencv.org/4.x/d9/df8/tutorial_root.html)
- [PyTorch Tutorials](https://docs.pytorch.org/tutorials/)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
