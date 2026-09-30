# 14. Blockchain và hợp đồng thông minh

**Nhóm:** Phần mềm & dữ liệu · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Hash và chữ ký số.
2. Giao dịch khối và xác nhận.
3. Tài khoản và quản lý khóa.
4. Smart contract và event.
5. Gas phí mạng.
6. Mạng công khai và permissioned.
7. Kiểm thử lỗi hợp đồng.
8. Privacy và dữ liệu ngoài chuỗi.
9. Khi nào cần nhiều bên tin cậy.

## Giảng nhanh

Blockchain lưu một lịch sử được nhiều nút đồng thuận theo quy tắc; smart contract là mã chạy trong môi trường của mạng. Không đưa dữ liệu cảm biến liên tục lên chuỗi vì chi phí và riêng tư; có thể lưu hash của báo cáo đã được lưu nơi khác để đối chiếu tính toàn vẹn.

## Bài tập ngắn

1. Tính hash của hai bản báo cáo khác một ký tự và đối chiếu.
2. Vẽ các bên tham gia kịch bản bàn giao hàng.

## Project portfolio: Nhật ký xác nhận bàn giao trên chuỗi mô phỏng

**Các bước thực hiện:**

1. Định nghĩa trạng thái created picked_up delivered và quyền của các vai.
2. Viết hợp đồng lưu ID và hash chứng từ không chứa dữ liệu riêng.
3. Viết bài test chuyển trạng thái đúng và sai.
4. Chạy trong môi trường mô phỏng theo hướng dẫn chính thức.
5. Công bố chi phí giả định giới hạn bảo mật và so sánh với database thường.

**Kiểm tra kết quả:**

- Không thể chuyển delivered trước picked_up.
- Hash sai được phát hiện khi đối chiếu chứng từ.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Đọc và viết mô phỏng bằng trình duyệt trước; không cần tiền hay mainnet

## Học sâu từ tài liệu gốc

- [Ethereum Developer Docs](https://ethereum.org/developers/docs/)
- [Hyperledger Fabric Introduction](https://hyperledger-fabric.readthedocs.io/en/latest/whatis.html)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
