# 15. Đồ họa lập trình và kỹ thuật đa phương tiện

**Nhóm:** Phần mềm & dữ liệu · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Raster vector và alpha.
2. Hệ tọa độ 2D 3D.
3. Phép biến đổi.
4. Màu sắc gamma.
5. Sampling aliasing.
6. Rasterization và shader.
7. Ánh sáng vật liệu.
8. Âm thanh và video codec.
9. Tối ưu asset.

## Giảng nhanh

Ảnh raster gồm pixel, phóng lớn có thể lộ ô vuông; vector mô tả hình học nên phóng to phù hợp logo và sơ đồ. Trong 3D, ma trận biến đổi vị trí một vật từ local space sang world space và camera space. Với dashboard, xuất ảnh có kích thước và tương phản rõ thường quan trọng hơn hiệu ứng phức tạp.

## Bài tập ngắn

1. Vẽ một icon ở SVG và PNG rồi so khi phóng 4 lần.
2. Giải thích tại sao đường chéo bị răng cưa khi giảm độ phân giải.

## Project portfolio: Bộ hình minh họa kiến trúc robot

**Các bước thực hiện:**

1. Phác họa 3 trạng thái bình thường cảnh báo mất tín hiệu.
2. Thiết kế SVG vector có palette và typography nhất quán.
3. Xuất PNG ở 2 kích thước và đối chiếu độ đọc.
4. Đưa bản đồ hệ tọa độ cảm biến vào một hình giải thích.
5. Kiểm tra nền sáng tối và ghi giấy phép asset.

**Kiểm tra kết quả:**

- Icon rõ ở kích thước nhỏ và không chỉ dựa màu.
- Có file nguồn vector chỉnh sửa được.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Inkscape hoặc trình duyệt với SVG; chưa cần phần mềm 3D nặng

## Học sâu từ tài liệu gốc

- [Stanford Graphics Courses](https://graphics.stanford.edu/courses/)
- [SVG MDN](https://developer.mozilla.org/en-US/docs/Web/SVG)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
