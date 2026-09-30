# 16. Game engine mô phỏng và XR

**Nhóm:** Phần mềm & dữ liệu · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Game loop và delta time.
2. Scene graph.
3. Input event.
4. Collision và physics.
5. Camera.
6. Script và tài nguyên.
7. State machine.
8. UI và âm thanh.
9. Mô phỏng VR AR và giới hạn độ chân thật.

## Giảng nhanh

Một game engine cập nhật logic theo từng frame; dùng `delta` để vật di chuyển theo thời gian thực thay vì mỗi frame một khoảng cố định. Mô phỏng robot chỉ đáng tin khi mô hình cảm biến và vật lý phản ánh giả định đã viết rõ; hình ảnh đẹp không đủ làm minh chứng độ chính xác.

## Bài tập ngắn

1. Viết pseudo-code di chuyển 1 m/s với 30 và 60 fps.
2. Nêu ba sai khác giữa mô phỏng và robot thật.

## Project portfolio: Kho hàng 2D tương tác

**Các bước thực hiện:**

1. Tạo bản đồ lưới và vị trí xe chở hàng.
2. Thêm điều khiển bằng bàn phím và chướng ngại.
3. Đưa bộ tìm đường chuyên đề 02 vào để hiển thị tuyến.
4. Hiện quãng đường và số lần va chạm.
5. Chụp GIF và ghi giới hạn vật lý mô phỏng.

**Kiểm tra kết quả:**

- Cùng một bản đồ seed cho kết quả lặp lại.
- Xe không đi xuyên vật cản theo luật đã viết.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Có thể làm HTML canvas nhẹ trước nếu máy thiếu chỗ

## Học sâu từ tài liệu gốc

- [Godot Stable Intro 2D](https://docs.godotengine.org/en/stable/tutorials/2d/introduction_to_2d.html)
- [Unity XR](https://docs.unity3d.com/6000.1/Documentation/Manual/XR.html)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
