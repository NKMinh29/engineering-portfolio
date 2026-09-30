# 02. Lập trình cấu trúc dữ liệu và thuật toán

**Nhóm:** Nền tảng · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Kiểu dữ liệu và hàm.
2. Đệ quy và bất biến.
3. Mảng danh sách hàng đợi stack.
4. Hash map và cây.
5. Đồ thị BFS DFS Dijkstra.
6. Sắp xếp và tìm kiếm.
7. Độ phức tạp thời gian bộ nhớ.
8. Unit test và dữ liệu biên.
9. Đọc ghi file và Git.

## Giảng nhanh

Big-O mô tả mức tăng khi kích thước đầu vào tăng; O(n²) trên n=100 và n=100000 tạo trải nghiệm hoàn toàn khác. Một priority queue giúp Dijkstra chọn đỉnh có khoảng cách tạm thời nhỏ nhất; nó phù hợp tính tuyến đường trên bản đồ dạng đồ thị.

## Bài tập ngắn

1. Viết FIFO cho 128 bản ghi cảm biến rồi kiểm tra tràn.
2. So sánh số phép duyệt của BFS và Dijkstra trên đồ thị có trọng số.

## Project portfolio: Bộ tìm đường trên sơ đồ kho hàng

**Các bước thực hiện:**

1. Mã hóa 12 vị trí kho thành đồ thị có trọng số và chướng ngại.
2. Viết BFS cho bản đồ không trọng số và Dijkstra cho trọng số.
3. Thêm đầu vào start goal và tập cạnh bị chặn.
4. Tạo ít nhất bốn trường hợp kiểm thử gồm không có đường.
5. In đường đi chi phí và số nút đã thăm.

**Kiểm tra kết quả:**

- Đường đi tối ưu được đối chiếu trên ba bản đồ nhỏ.
- Đường không tồn tại báo lỗi rõ ràng.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Python trên Windows hoặc notebook cloud

## Học sâu từ tài liệu gốc

- [Python Tutorial](https://docs.python.org/3/tutorial/index.html)
- [CS2023 Areas](https://csed.acm.org/knowledge-areas/)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
