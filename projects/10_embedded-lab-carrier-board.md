# 10. Bo mở rộng nhúng có hồ sơ thiết kế và bring-up

**Tên repo đề xuất:** `embedded-lab-carrier-board`  
**Ưu tiên:** P1/P2 — nối tiếp công việc PCB hiện có  
**Năng lực:** Electronics, PCB, power, interfaces, hardware validation  
**Ước lượng lập kế hoạch:** 40–80 giờ; thời gian chế tạo tính riêng. Không phải cam kết; chưa tính toàn bộ thời gian học nền tảng.

> Trạng thái: bản thiết kế. Prototype CAN Log Workbench được chuẩn bị riêng; các sản phẩm khác cần triển khai hoặc nhập artifact gốc. Tiêu chí nghiệm thu là mục tiêu, chưa phải kết quả đã đạt.

## 1. Người dùng và bài toán

Người học cần một carrier board có test point, nguồn rõ ràng và đầu nối thuận tiện để thực hành sensor/CAN mà có thể kiểm tra từng khối.

## 2. MVP — phiên bản nhỏ nhất đủ demo

- Schematic source, PCB source, PDF review, pin map và BOM có phương án thay thế.
- Một cấu hình nguồn/logic được chọn rõ; các connector có pin 1 và nhãn.
- Bring-up checklist và bảng đo thật khi board đã được lắp.

## 3. Kiến trúc và hợp đồng dữ liệu

Nguồn vào → protection/regulator → MCU interface → sensor/communication connectors. Các khối được review riêng theo điện áp, dòng và đường hồi ground.

**Hợp đồng:** Interface table {connector, pin, net, direction, voltage_domain, max_current, pullup, test_point}. Quyết định 3.3 V/5 V phải dựa trên datasheet từng linh kiện và schematic gốc.

## 4. Công cụ và môi trường

Giữ công cụ CAD của thiết kế hiện có, ví dụ EasyEDA; không chuyển sang KiCad chỉ để có thêm công cụ. Xuất source ở định dạng native cùng PDF/BOM.

## 5. Cấu trúc repo đề xuất

- `hardware/source/`: CAD native
- `hardware/review/`: schematic PDF, layout images
- `manufacturing/`: chỉ export bản đã review
- `bom/`: lựa chọn và thay thế
- `bringup/`: đo đạc, ảnh, issue log

## 6. Milestones để chuyển thành GitHub Issues

1. Nhập đúng phiên bản schematic/PCB gốc; ghi revision.
2. Lập interface table và power budget.
3. Sửa ERC/DRC, giữ danh sách waiver có lý do nếu có.
4. Review routing, footprint, pin 1 và test points.
5. Chỉ xuất bản chế tạo khi revision đã khóa.
6. Bring-up từng rail/interface, lưu ảnh và số đo.

Mỗi milestone là một issue cha; tách task chỉ khi đủ nhỏ để có output và cách kiểm tra trong một buổi làm. Commit theo thay đổi thật, không tạo lịch sử đóng góp giả.

## 7. Nghiệm thu

- Mỗi connector truy được tới net và MCU pin.
- BOM ghi manufacturer part number hoặc lý do linh kiện generic.
- Không ghi “tested hardware” nếu mới chạy DRC.
- Gerber/BOM/PDF source cùng revision; lỗi sau chế tạo có issue riêng.

## 8. Bằng chứng đưa lên portfolio

Ảnh render và sơ đồ khối ở giai đoạn thiết kế; thêm ảnh board/đo nguồn khi đã có phần cứng.

README cần: bài toán → demo → cách chạy → kiến trúc → kết quả đo → hạn chế → phần đóng góp của Minh → nguồn và license. Số đo phải gắn thiết bị/cấu hình/dataset; không đặt badge test pass trước khi có workflow chạy thật.

## 9. Giảng nhanh

DRC kiểm tra tập quy tắc hình học đã cấu hình. DRC pass không tự chứng minh đúng nguồn, đúng footprint hay hoạt động điện; schematic review và bring-up giải quyết các lớp bằng chứng khác nhau.

## 10. Phạm vi và bước tiếp theo

Bản thiết kế này chưa sửa PCB gốc. Đây là thiết kế repo để lưu công việc hiện có; cần nhập source và bản revision phù hợp trước khi xuất fabrication files.

## Tài liệu gốc

- KiCad docs tham khảo workflow — https://docs.kicad.org/

Tình trạng kiểm tra liên kết ghi trong `../NGUON_VA_PHAM_VI.md`. Tài liệu là điểm bắt đầu học; thiết kế MVP và nghiệm thu ở đây là đề xuất riêng cho portfolio của Minh.
