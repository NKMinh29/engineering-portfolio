# 04. Kiến trúc máy tính và hệ điều hành

**Nhóm:** Nền tảng · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Nhị phân và biểu diễn số.
2. CPU cache RAM flash.
3. Interrupt DMA và memory map.
4. Process thread và scheduler.
5. Virtual memory.
6. Đồng bộ và race condition.
7. File system và I/O.
8. Kernel và system call.
9. Boot sequence và đo hiệu năng.

## Giảng nhanh

Ngắt cho CPU phản ứng với sự kiện ngoại vi; scheduler quyết định task nào chạy. Cache giúp tăng tốc nhưng cũng gây sai lệch nếu đo thời gian thiếu kiểm soát. Một biến dùng chung giữa ngắt và luồng chính cần được quản lý theo đúng ngữ nghĩa bộ nhớ, không chỉ mong rằng lệnh đọc ghi luôn có thứ tự.

## Bài tập ngắn

1. Vẽ vùng stack heap cho chương trình C nhỏ.
2. Lập lịch 3 task ưu tiên khác nhau và xác định nơi có thể race.

## Project portfolio: Thí nghiệm độ trễ tác vụ với timer

**Các bước thực hiện:**

1. Tận dụng demo FreeRTOS hoặc timer hiện có trên S32K144.
2. Ghi timestamp trước và sau xử lý ở ít nhất 100 lần.
3. Bật và tắt một task nền có kiểm soát.
4. Tính trung vị cực đại và histogram.
5. Phân biệt phần đo trên MCU và phần chỉ phân tích log trên PC.

**Kiểm tra kết quả:**

- Có log thô và cách đổi chu kỳ sang thời gian ghi rõ clock.
- Nêu ít nhất một nguồn jitter và số liệu chứng minh.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Dùng board và công cụ S32K144 đang có; phân tích bằng Python

## Học sâu từ tài liệu gốc

- [FreeRTOS Docs](https://docs.freertos.org/)
- [CS2023 Areas](https://csed.acm.org/knowledge-areas/)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
