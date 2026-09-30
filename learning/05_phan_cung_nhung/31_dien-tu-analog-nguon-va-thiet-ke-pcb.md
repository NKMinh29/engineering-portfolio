# 31. Điện tử analog nguồn và thiết kế PCB

**Nhóm:** Phần cứng & nhúng · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Định luật Ohm và công suất.
2. Digital voltage level.
3. LDO buck và decoupling.
4. Op-amp comparator.
5. ESD và bảo vệ ngõ vào.
6. Schematic symbol footprint.
7. Net class và return path.
8. DRC ERC.
9. BOM Gerber và kiểm tra sau chế tạo.

## Giảng nhanh

Schematic nói chân nào nối chân nào; PCB còn quyết định đường dòng điện và vị trí linh kiện. DRC tìm lỗi theo bộ quy tắc hình học/điện đã khai báo, không chứng minh mạch sẽ chạy đúng. Với base board S32K144, mức 3,3 V, ground và khả năng chịu áp của từng IC phải được kiểm từ datasheet.

## Bài tập ngắn

1. Tính điện trở hạn dòng cho LED và dòng tiêu thụ giả định.
2. Tìm chân symbol không trùng số pad footprint trong một ví dụ.

## Project portfolio: Hoàn thiện một kênh input và output trên EasyEDA

**Các bước thực hiện:**

1. Chọn một đường input biến trở/công tắc và một LED output từ PCB đang làm.
2. Lập bảng điện áp dòng pin MCU và linh kiện bảo vệ.
3. Kiểm tra schematic ERC mapping symbol footprint.
4. Bố trí routing và chạy DRC với giá trị rule có nguồn.
5. Xuất BOM Gerber 3D và checklist đo nguồn sau khi có bo thật.

**Kiểm tra kết quả:**

- Đường nguồn và ground có tên rõ trên schematic.
- DRC sạch và ghi giới hạn kiểm chứng khi chưa đặt PCB.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Dùng project EasyEDA có sẵn trong trình duyệt; không cần đặt hàng để hoàn thành bài thiết kế

## Học sâu từ tài liệu gốc

- [EasyEDA PCB Layout](https://docs.easyeda.com/en/Introduction/PCB-Layout/)
- [EasyEDA Convert](https://docs.easyeda.com/en/Schematic/Convert-to-PCB/index.html)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
