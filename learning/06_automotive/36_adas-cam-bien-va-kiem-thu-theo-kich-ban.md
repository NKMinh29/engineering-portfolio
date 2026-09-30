# 36. ADAS cảm biến và kiểm thử theo kịch bản

**Nhóm:** Automotive · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Chức năng AEB ACC LKA.
2. Camera radar LiDAR.
3. Hợp nhất cảm biến.
4. Nhận biết làn và vật cản.
5. Time-to-collision.
6. Control actuation.
7. ODD và giới hạn.
8. Scenario-based validation.
9. False alarm và missed detection.

## Giảng nhanh

ADAS thường có ba bước: quan sát môi trường, dự báo rủi ro và quyết định can thiệp. TTC cơ bản là khoảng cách tương đối chia tốc độ đóng; nếu tốc độ đóng không dương thì công thức cảnh báo đơn giản này không áp dụng. Bộ tiêu chí kiểm thử phải nói rõ tốc độ, tầm nhìn, vật cản và mức can thiệp kỳ vọng.

## Bài tập ngắn

1. Tính TTC cho 20 m với tốc độ đóng 5 m/s và trường hợp hai xe tách xa.
2. Vẽ 3 tình huống cùng vật cản nhưng khác ánh sáng/che khuất.

## Project portfolio: Bộ kịch bản cảnh báo vật cản có thể tái lập

**Các bước thực hiện:**

1. Định nghĩa ODD nhỏ gồm đường thẳng tốc độ thấp và cảm biến giả lập.
2. Tạo 10 case với khoảng cách vận tốc chất lượng đo.
3. Viết thuật toán cảnh báo TTC có trạng thái dữ liệu không hợp lệ.
4. Chạy bảng case và đo false alarm missed alert.
5. Viết báo cáo lý do đây chỉ là demo không đủ xác nhận an toàn xe thật.

**Kiểm tra kết quả:**

- Case không có vật cản và mất dữ liệu khác nhau.
- Mọi cảnh báo có điều kiện đầu vào rõ.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** CSV và Python đủ; CARLA để học khi có tài nguyên

## Học sâu từ tài liệu gốc

- [ASAM OpenSCENARIO DSL](https://www.asam.net/standards/detail/openscenario-dsl/)
- [CARLA Simulator](https://carla.org/)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
