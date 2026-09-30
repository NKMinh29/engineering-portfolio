# 01. Toán cho khoa học máy tính

**Nhóm:** Nền tảng · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Logic mệnh đề và chứng minh.
2. Tập hợp quan hệ hàm.
3. Quy nạp toán học.
4. Tổ hợp và xác suất.
5. Ma trận vector trị riêng.
6. Đạo hàm gradient.
7. Thống kê mô tả và khoảng tin cậy.
8. Tối ưu hóa và đánh giá sai số.
9. Toán rời rạc cho đồ thị.

## Giảng nhanh

Xác suất P(A|B) đo khả năng A khi đã biết B; nó khác P(B|A). Trong phát hiện tấn công CAN hiếm gặp, độ chính xác tổng thể cao vẫn có thể kèm nhiều cảnh báo nhầm: cần xem precision, recall và tỷ lệ nền. Một vector LiDAR đổi hệ trục bằng phép nhân ma trận và phép tịnh tiến; luôn ghi rõ hệ quy chiếu.

## Bài tập ngắn

1. Tạo bảng 1000 khung CAN với 10 tấn công và tự tính precision/recall cho 2 ngưỡng.
2. Vẽ đồ thị đường đi 5 nút và tính đường đi ngắn nhất thủ công.

## Project portfolio: Sổ tay toán với ví dụ CAN và cảm biến

**Các bước thực hiện:**

1. Tạo notebook Python nhỏ với ma trận nhầm lẫn và 2 ngưỡng.
2. Thêm thí nghiệm xác suất với 1% và 20% mẫu tấn công.
3. Viết phép biến đổi 2D cho ba điểm đo.
4. Đối chiếu kết quả bằng tính tay và ghi sai số làm tròn.
5. Viết kết luận ngắn về ảnh hưởng của tỷ lệ nền.

**Kiểm tra kết quả:**

- Có thể đổi tỷ lệ nền mà biểu đồ precision/recall cập nhật.
- Hai trường hợp biến đổi tọa độ có kết quả kiểm tra tay.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Trình duyệt với notebook hoặc Python sẵn có; bộ dữ liệu tự tạo rất nhỏ

## Học sâu từ tài liệu gốc

- [CS2023 Math](https://csed.acm.org/knowledge-areas/)
- [Google ML Foundations](https://developers.google.com/machine-learning/crash-course)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
