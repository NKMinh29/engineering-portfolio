# 09. Ứng dụng di động đa nền tảng

**Nhóm:** Phần mềm & dữ liệu · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Vòng đời ứng dụng.
2. UI state và navigation.
3. Lưu trữ cục bộ.
4. API client và cache.
5. Quyền truy cập cảm biến.
6. Xử lý ngoại tuyến.
7. Accessibility.
8. Kiểm thử ứng dụng.
9. Bảo vệ dữ liệu người dùng.

## Giảng nhanh

Ứng dụng di động có thể bị tắt hoặc mất mạng bất cứ lúc nào; dữ liệu cần có trạng thái loading thành công và lỗi. Nếu nhận cảnh báo robot, màn hình phải phân biệt “mất kết nối” với “robot ổn định” vì hai trạng thái có ý nghĩa an toàn khác nhau.

## Bài tập ngắn

1. Vẽ 3 màn hình trạng thái thiết bị và luồng mất mạng.
2. Viết bảng dữ liệu nào lưu trên máy và thời gian lưu.

## Project portfolio: App xem telemetry ở chế độ prototype

**Các bước thực hiện:**

1. Làm prototype tương tác trên giấy hoặc web responsive trước.
2. Định nghĩa JSON trạng thái pin GPS cảnh báo.
3. Nếu có đủ tài nguyên tạo app Compose từ tài liệu chính thức.
4. Dùng dữ liệu mẫu và mô phỏng ngắt mạng.
5. Quay video luồng bình thường cảnh báo và không có dữ liệu.

**Kiểm tra kết quả:**

- Giao diện phân biệt lỗi cảm biến với thiết bị bình thường.
- Không yêu cầu quyền hệ thống khi demo không sử dụng.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Prototype web nhẹ trước; Android Studio có thể cần thêm dung lượng hoặc máy lab

## Học sâu từ tài liệu gốc

- [Android Basics Compose](https://developer.android.com/courses/android-basics-compose/course)
- [Android Developer Guide](https://developer.android.com/guide)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
