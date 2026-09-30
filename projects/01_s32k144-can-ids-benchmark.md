# 01. Repo nghiên cứu CAN IDS / IMCOM 2027

**Tên repo đề xuất:** `s32k144-can-ids-benchmark`  
**Ưu tiên:** P0 — đóng gói công việc đã có  
**Năng lực:** Embedded C, automotive security, ML deployment, đo thời gian, nghiên cứu tái lập  
**Ước lượng lập kế hoạch:** 16–30 giờ sau khi có đủ artifact gốc. Không phải cam kết; chưa tính toàn bộ thời gian học nền tảng.

> Trạng thái: bản thiết kế. Prototype CAN Log Workbench được chuẩn bị riêng; các sản phẩm khác cần triển khai hoặc nhập artifact gốc. Tiêu chí nghiệm thu là mục tiêu, chưa phải kết quả đã đạt.

## 1. Người dùng và bài toán

Người đọc nghiên cứu cần truy ngược từ một con số trong bài về bản build, cấu hình, dữ liệu đo và script tạo bảng. Repo này là hồ sơ thực nghiệm cho nghiên cứu của Minh.

## 2. MVP — phiên bản nhỏ nhất đủ demo

- README mô tả đúng ranh giới processing time, testbed, hai detector và trạng thái nghiên cứu.
- Manifest của 18 run, metadata cấu hình, checksum ELF và script tái tạo bảng theo từng run.
- Mã nguồn do nhóm sở hữu, hướng dẫn cài SDK riêng, bốn functional probe và kết quả đối chiếu có nguồn.

## 3. Kiến trúc và hợp đồng dữ liệu

Firmware S32K144 ghi log → decoder theo layout đã xác nhận → CSV đã kiểm tra → tổng hợp theo run → bảng/hình trong bài. Notebook huấn luyện và kiểm tra Python/C là nhánh riêng, liên kết bằng checksum model.

**Hợp đồng:** Mỗi run cần run_id, model_id, input_kind, lpit_mode, core_hz, can_bitrate, compiler, optimization, elf_sha256, raw_log_sha256, record_count. CSV giải mã cần sequence, timestamps, cycles, timer_entries, score và decision; phải đối chiếu layout C trước khi viết decoder.

## 4. Công cụ và môi trường

Giữ nguyên toolchain thực nghiệm đã xác nhận. Phần analysis chạy Python trên Windows. S32DS/SDK cần cho build và đo lại trên MCU; phân tích log không cần board.

## 5. Cấu trúc repo đề xuất

- `firmware/app/`: mã do nhóm sở hữu
- `analysis/`: decoder, kiểm tra và tạo bảng
- `data/manifests/`: nguồn gốc từng run
- `data/samples/`: sample được phép chia sẻ
- `docs/`: setup, measurement boundary, limitations
- `results/`: bảng sinh từ dữ liệu và cấu hình

## 6. Milestones để chuyển thành GitHub Issues

1. Thu gom phiên bản source/ELF/MAP/log đã dùng; tính checksum, lập bảng thiếu/có.
2. Chốt clock 48 MHz theo bản thảo mới; đối chiếu các artifact cũ khác clock trước khi nhập.
3. Xác nhận layout 48-byte record/160-byte metadata bằng định nghĩa C và kích thước thực tế.
4. Decoder phải phát hiện file thiếu, sai kích thước, sequence lỗi, clock không khớp và timestamp wrap.
5. Tổng hợp đủ 6 cấu hình × 3 run × 128 record; tạo bảng và đối chiếu từng ô với bản thảo.
6. Gắn release khi có thể chạy lại; cập nhật DOI/trạng thái hội nghị khi có bằng chứng chính thức.

Mỗi milestone là một issue cha; tách task chỉ khi đủ nhỏ để có output và cách kiểm tra trong một buổi làm. Commit theo thay đổi thật, không tạo lịch sử đóng góp giả.

## 7. Nghiệm thu

- Tái tạo đủ 2.304 record, 18 run; không tạo cấu hình Attack + LPIT ON vốn chưa được đo.
- Từ CSV thật tái tạo D3 OFF 275 cycles, D4 OFF 23.322 cycles; chênh lệch phải được giải thích trước khi phát hành.
- README phân biệt số trong bản thảo và số đã tái chạy; manifest truy về đúng một ELF.
- Một người khác có thể chạy analysis mà không cần bộ SDK thương mại.

## 8. Bằng chứng đưa lên portfolio

Video 90 giây: mô tả board → chọn manifest → chạy analysis → giải thích một hình và một giới hạn; lưu log chạy thực tế.

README cần: bài toán → demo → cách chạy → kiến trúc → kết quả đo → hạn chế → phần đóng góp của Minh → nguồn và license. Số đo phải gắn thiết bị/cấu hình/dataset; không đặt badge test pass trước khi có workflow chạy thật.

## 9. Giảng nhanh

Cycle và microsecond liên hệ qua T_us = cycles × 10^6 / core_hz. Mẫu đo lặp trong cùng run có thể phụ thuộc nhau; thống kê theo run giúp giữ đơn vị lặp thí nghiệm. Processing time ở bài này gồm tạo feature, dispatch, inference, publication/LED; không gồm mọi khâu nhận frame.

## 10. Phạm vi và bước tiếp theo

Chưa chép source, raw log hay paper vào bộ thiết kế này. Chưa xác nhận bài được chấp nhận. Không gọi D4 là TFLite Micro: bản thảo mô tả integer MLP biên dịch C. Không gọi kết quả là WCET hay chứng minh không mất frame.

## Tài liệu gốc

- IMCOM guidelines — https://www.imcom.org/gnu/guideline.htm
- Nguồn nội bộ đã đọc: IMCOM2027_NKM_tuned.tex, sửa 16/09/2026.

Tình trạng kiểm tra liên kết ghi trong `../NGUON_VA_PHAM_VI.md`. Tài liệu là điểm bắt đầu học; thiết kế MVP và nghiệm thu ở đây là đề xuất riêng cho portfolio của Minh.
