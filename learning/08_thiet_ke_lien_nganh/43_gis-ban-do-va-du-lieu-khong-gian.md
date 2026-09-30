# 43. GIS bản đồ và dữ liệu không gian

**Nhóm:** Thiết kế & liên ngành · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Vĩ kinh độ và hệ quy chiếu.
2. Raster và vector.
3. GeoJSON.
4. GPS error.
5. Spatial join.
6. Routing.
7. Geofencing.
8. Map tile.
9. Quyền riêng tư vị trí.

## Giảng nhanh

Kinh độ vĩ độ là tọa độ góc; không được lấy hiệu độ rồi xem trực tiếp là mét ở mọi nơi. Khi tính khoảng cách ngắn có thể đổi sang hệ phù hợp hoặc dùng công thức địa lý với giả định rõ. Dữ liệu GPS thiếu FIX cần hiển thị trạng thái thay vì im lặng đặt robot ở (0,0).

## Bài tập ngắn

1. Vẽ polygon vùng cấm và ba điểm trong ngoài trên giấy.
2. Giải thích vì sao hai vị trí GPS gần nhau vẫn có sai số nhiều mét.

## Project portfolio: Kiểm tra geofence offline cho hành trình giả

**Các bước thực hiện:**

1. Tạo 20 tọa độ giả cùng accuracy và fix status.
2. Định nghĩa polygon khu vực cho phép.
3. Viết kiểm tra point-in-polygon.
4. Trả trạng thái trong ngoài không xác định khi GPS invalid.
5. Vẽ đường đi và các điểm bị cảnh báo trên bản đồ đơn giản.

**Kiểm tra kết quả:**

- GPS không FIX không bị gán là ngoài vùng.
- Có ví dụ điểm đúng trên biên polygon.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Python hoặc web canvas không cần tải bản đồ nền

## Học sâu từ tài liệu gốc

- [QGIS Gentle GIS](https://docs.qgis.org/3.44/en/docs/gentle_gis_introduction/index.html)
- [GeoJSON RFC](https://www.rfc-editor.org/rfc/rfc7946)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
