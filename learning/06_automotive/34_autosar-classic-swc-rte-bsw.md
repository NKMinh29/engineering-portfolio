# 34. AUTOSAR Classic SWC RTE BSW

**Nhóm:** Automotive · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. ECU và layered architecture.
2. SWC port interface.
3. Runnables events.
4. RTE generation.
5. OS task mapping.
6. MCAL ECU abstraction.
7. CAN stack.
8. DCM DEM.
9. ARXML config build và integration.

## Giảng nhanh

Classic đặt ứng dụng trong SWC; RTE nối SWC với nhau và BSW theo cấu hình; BSW cung cấp các dịch vụ hạ tầng. File `Rte.c` được generate cho project EB tresos là mã glue từ cấu hình chứ không có nghĩa toàn bộ ECU đã chạy đúng; cần build flash và kiểm tra hành vi phần cứng.

## Bài tập ngắn

1. Vẽ SWC nhận CAN và Runnable bật LED với mapping task.
2. Ghi luồng của một DTC từ phát hiện lỗi tới DEM và DCM.

## Project portfolio: ECU demo có tài liệu đường đi tín hiệu

**Các bước thực hiện:**

1. Dùng project simple_demo_rte đã generate thành công.
2. Liệt kê module cấu hình và file sinh ra tương ứng.
3. Vẽ đường tín hiệu input → SWC Runnable → RTE → BSW/driver → output.
4. Làm test board hoặc mô phỏng có log quan sát.
5. Ghi lỗi build nếu có và phân biệt generate thành công với flash thành công.

**Kiểm tra kết quả:**

- Có sơ đồ một runnable với trigger thực.
- README mô tả rõ board toolchain phiên bản và dấu hiệu chạy thành công.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** EB tresos và S32DS có sẵn; làm tiếp project đã tạo

## Học sâu từ tài liệu gốc

- [AUTOSAR Classic Platform](https://www.autosar.org/standards/classic-platform)
- [FreeRTOS Concepts](https://docs.freertos.org/)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
