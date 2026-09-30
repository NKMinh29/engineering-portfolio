# 14. Thử nghiệm truy xuất bàn giao hàng hóa

**Tên repo đề xuất:** `shipment-proof-ledger`  
**Ưu tiên:** P3 — chỉ sau một app SQL hoàn chỉnh  
**Năng lực:** Blockchain, smart contracts, backend, provenance, testing  
**Ước lượng lập kế hoạch:** 25–45 giờ. Không phải cam kết; chưa tính toàn bộ thời gian học nền tảng.

> Trạng thái: bản thiết kế. Prototype CAN Log Workbench được chuẩn bị riêng; các sản phẩm khác cần triển khai hoặc nhập artifact gốc. Tiêu chí nghiệm thu là mục tiêu, chưa phải kết quả đã đạt.

## 1. Người dùng và bài toán

So sánh hai cách lưu sự kiện bàn giao kiện hàng giữa các bên: database tập trung và ledger smart contract trong môi trường thử nghiệm.

## 2. MVP — phiên bản nhỏ nhất đủ demo

- Một workflow create shipment → handoff → accept; quyền của các bên rõ.
- Cùng bộ tình huống chạy trên SQLite và local blockchain để so.
- Chỉ lưu ID/hash/event trên chain; hồ sơ đầy đủ nằm ngoài chain.

## 3. Kiến trúc và hợp đồng dữ liệu

UI/script → application service → storage interface → SQL adapter hoặc smart-contract adapter. Hai adapter dùng cùng domain rules và cùng test cases.

**Hợp đồng:** Event {shipment_id, sequence, from_party, to_party, document_hash, event_type}; điều kiện accept dựa vào trạng thái và caller. Không đưa thông tin cá nhân vào fixture on-chain.

## 4. Công cụ và môi trường

SQL baseline trước; Solidity + browser/local dev chain sau. Không cần token kinh doanh, ví có tài sản thật hoặc mainnet.

## 5. Cấu trúc repo đề xuất

- `domain/`: state machine
- `sql_backend/`: baseline
- `contracts/`: thử nghiệm contract
- `tests/`: cùng scenario cho hai backend
- `comparison/`: trust, cost, complexity

## 6. Milestones để chuyển thành GitHub Issues

1. Viết ai tin ai và ai có quyền sửa dữ liệu.
2. Hoàn thành SQL implementation.
3. Thêm contract với quyền và events.
4. Test caller sai, replay và handoff sai thứ tự.
5. Đo thao tác, chi phí execution trong dev environment, độ phức tạp recovery.
6. Viết kết luận khi nào SQL đủ và khi nào nhiều bên cần ledger.

Mỗi milestone là một issue cha; tách task chỉ khi đủ nhỏ để có output và cách kiểm tra trong một buổi làm. Commit theo thay đổi thật, không tạo lịch sử đóng góp giả.

## 7. Nghiệm thu

- Không thể accept shipment chưa handoff cho chính bên đó.
- Replay không tạo hai lần chuyển quyền.
- Hash document không bị trình bày như bằng chứng hàng hóa ngoài đời đúng.
- Báo cáo giữ cả bất lợi của blockchain.

## 8. Bằng chứng đưa lên portfolio

Cùng một flow trên SQL và local chain; so event trail và một request bị từ chối.

README cần: bài toán → demo → cách chạy → kiến trúc → kết quả đo → hạn chế → phần đóng góp của Minh → nguồn và license. Số đo phải gắn thiết bị/cấu hình/dataset; không đặt badge test pass trước khi có workflow chạy thật.

## 9. Giảng nhanh

Ledger có thể ghi lại cam kết dữ liệu; nó không tự xác minh kiện hàng ngoài đời. Đây là bài toán kết nối dữ liệu thực với hệ thống, thường gọi là oracle problem.

## 10. Phạm vi và bước tiếp theo

Ưu tiên thấp vì portfolio hiện có thể mạnh hơn với embedded + web. Không đặt mục tiêu gọi vốn hay deploy tài sản thật.

## Tài liệu gốc

- Ethereum developer docs — https://ethereum.org/en/developers/docs/

Tình trạng kiểm tra liên kết ghi trong `../NGUON_VA_PHAM_VI.md`. Tài liệu là điểm bắt đầu học; thiết kế MVP và nghiệm thu ở đây là đề xuất riêng cho portfolio của Minh.
