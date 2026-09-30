# 37. Mạng trong xe chẩn đoán và an toàn chức năng

**Nhóm:** Automotive · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. CAN arbitration frame bit timing.
2. LIN và Ethernet ô tô.
3. UDS service.
4. DTC và DEM.
5. DCM interaction.
6. DoIP.
7. Fault detection.
8. Fail-safe state.
9. Safety case ở mức khái niệm.
10. Truy vết requirement test.

## Giảng nhanh

CAN ưu tiên ID thấp trong phân xử, còn ID không tự xác thực người gửi. DTC mã hóa thông tin lỗi được ECU quản lý; UDS quy định kiểu tương tác chẩn đoán. Safety khác security: hỏng ngẫu nhiên và hành vi tấn công có thể cần phương pháp kiểm soát khác nhau nhưng cùng ảnh hưởng chức năng.

## Bài tập ngắn

1. Tính bus load xấp xỉ cho một tập frame có kỳ và giải thích giả định.
2. Lập bảng một lỗi cảm biến đi qua phát hiện → DTC → hiển thị.

## Project portfolio: Bộ giải mã trace CAN và fault injection trong lab

**Các bước thực hiện:**

1. Định nghĩa hai ID một báo trạng thái một báo lỗi.
2. Thu hoặc tự tạo log frame có timestamp.
3. Viết decoder theo định nghĩa byte có endian và scaling rõ.
4. Chèn lỗi giả vào log offline và xác nhận trạng thái fault.
5. Trình bày đường fault → DTC mô phỏng và phần đã kiểm bằng board nếu có.

**Kiểm tra kết quả:**

- Decoder có golden vectors bình thường biên lỗi.
- Không mô tả UDS đã chạy nếu chỉ làm mô phỏng DTC.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Dùng hai board S32K144 hoặc log offline; không nối xe thật

## Học sâu từ tài liệu gốc

- [AUTOSAR Classic](https://www.autosar.org/standards/classic-platform)
- [NXP S32K Data Sheet](https://www.nxp.com/docs/en/data-sheet/S32K1xx.pdf)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
