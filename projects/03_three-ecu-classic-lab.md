# 03. Mô hình ba ECU theo kiến trúc Classic

**Tên repo đề xuất:** `three-ecu-classic-lab`  
**Ưu tiên:** P1 — chiều sâu chuyên ngành  
**Năng lực:** AUTOSAR Classic, C, CAN, state machine, RTOS, testing  
**Ước lượng lập kế hoạch:** 45–80 giờ cho host model và một luồng trên board. Không phải cam kết; chưa tính toàn bộ thời gian học nền tảng.

> Trạng thái: bản thiết kế. Prototype CAN Log Workbench được chuẩn bị riêng; các sản phẩm khác cần triển khai hoặc nhập artifact gốc. Tiêu chí nghiệm thu là mục tiêu, chưa phải kết quả đã đạt.

## 1. Người dùng và bài toán

Cần quản lý logic phân tán giữa ba ECU mà vẫn kiểm thử được application logic khi chưa có toàn bộ phần cứng.

## 2. MVP — phiên bản nhỏ nhất đủ demo

- Đề xuất phân vai: ECU Input phát input đã debounce; ECU Body quyết định đèn; ECU Display hiển thị trạng thái/lỗi.
- Bảng signal, chu kỳ, timeout, port và runnable cho đúng một use case Manual/Auto lighting.
- Host simulation kiểm thử logic; adapter S32K144 cho một đường truyền CAN.

## 3. Kiến trúc và hợp đồng dữ liệu

Application SWC → RTE interface → communication/IO services → hardware adapter. Ba ECU có hợp đồng CAN chung. Bản tự viết được ghi là mô hình giáo dục lấy cảm hứng Classic; tích hợp vendor stack là một cấu hình riêng.

**Hợp đồng:** Bảng message do dự án tự định nghĩa: 0x101 InputStatus mỗi 20 ms, 0x201 LightStatus mỗi 20 ms, 0x301 NodeHealth mỗi 100 ms. Đây là ID lab đề xuất. Timeout demo 100 ms và trạng thái fallback cần thống nhất trong requirements.

## 4. Công cụ và môi trường

C và host compiler có sẵn; S32DS trên Windows cho hardware adapter. ARXML/EB tresos chỉ thêm sau khi chốt stack, bản phát hành và quyền phân phối.

## 5. Cấu trúc repo đề xuất

- `swc/`: pure application logic
- `rte_api/`: interface và stub host
- `bsw_adapter/`: CAN, Dio, timer abstraction
- `ecu_config/`: cấu hình riêng từng ECU
- `tests/scenarios/`: normal, timeout, recovery
- `docs/`: signal matrix và mapping

## 6. Milestones để chuyển thành GitHub Issues

1. Viết 10 yêu cầu có ID, gồm mất input và recovery.
2. Thiết kế state machine và signal matrix rồi review trước coding.
3. Viết SWC thuần C với clock/input được truyền vào.
4. Tạo host runner cho ba ECU theo thời gian giả lập.
5. Thay adapter host bằng board trên một use case; ghi log và kiểm tra timeout.
6. Lập bảng mapping sang module Classic đã thực sự sử dụng.

Mỗi milestone là một issue cha; tách task chỉ khi đủ nhỏ để có output và cách kiểm tra trong một buổi làm. Commit theo thay đổi thật, không tạo lịch sử đóng góp giả.

## 7. Nghiệm thu

- Cùng test vector cho host và board cho ra cùng trạng thái ứng dụng.
- Mất 0x101 quá timeout đưa hệ thống về trạng thái fallback đã ghi; recovery không nhấp nháy vô hạn.
- Mỗi requirement có ít nhất một evidence test tương ứng.
- README ghi rõ thành phần tự viết, thành phần vendor, mức tích hợp thực tế.

## 8. Bằng chứng đưa lên portfolio

Màn hình timeline ba ECU, rút kết nối node input trên bàn thử, quan sát timeout và phục hồi.

README cần: bài toán → demo → cách chạy → kiến trúc → kết quả đo → hạn chế → phần đóng góp của Minh → nguồn và license. Số đo phải gắn thiết bị/cấu hình/dataset; không đặt badge test pass trước khi có workflow chạy thật.

## 9. Giảng nhanh

RTE giúp application dùng interface thay vì gọi driver trực tiếp. Chỉ chia thư mục theo Application/RTE/BSW chưa đủ chứng minh tuân thủ AUTOSAR; cần cả cấu hình, API, hành vi và workflow đúng stack.

## 10. Phạm vi và bước tiếp theo

Đây là đề xuất phân vai ban đầu, cần đối chiếu yêu cầu thầy trước khi áp dụng lên xe lab. Giai đoạn đầu dùng LED/host simulator; chưa điều khiển chức năng chuyển động của xe.

## Tài liệu gốc

- AUTOSAR Classic — https://www.autosar.org/standards/classic-platform/

Tình trạng kiểm tra liên kết ghi trong `../NGUON_VA_PHAM_VI.md`. Tài liệu là điểm bắt đầu học; thiết kế MVP và nghiệm thu ở đây là đề xuất riêng cho portfolio của Minh.
