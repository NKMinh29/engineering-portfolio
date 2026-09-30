# 44. Tin sinh học và dữ liệu khoa học

**Nhóm:** Thiết kế & liên ngành · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. DNA RNA protein.
2. FASTA và định dạng.
3. Đếm base và GC.
4. Alignment.
5. Mutation và k-mer.
6. Xác suất sinh học.
7. Dataset provenance.
8. Reproducible notebook.
9. Giới hạn diễn giải sinh học.

## Giảng nhanh

DNA biểu diễn chuỗi ký tự A/C/G/T; GC content là tỷ lệ số ký tự G hoặc C trên chuỗi hợp lệ. Một kết quả phần mềm trùng khớp đoạn gene chỉ đưa ra bằng chứng tính toán; diễn giải sinh học cần dữ liệu ngữ cảnh và kiểm chứng thêm.

## Bài tập ngắn

1. Viết hàm đếm GC với chuỗi rỗng và ký tự N.
2. Tính reverse complement cho chuỗi 10 ký tự.

## Project portfolio: Bộ phân tích FASTA nhỏ

**Các bước thực hiện:**

1. Đọc file FASTA do bạn tự tạo gồm 5 chuỗi.
2. Kiểm tra ID trùng chuỗi rỗng và ký tự ngoài tập cho phép.
3. Tính chiều dài GC và reverse complement.
4. Tạo bảng thống kê và biểu đồ.
5. Viết README về format và giới hạn dữ liệu mẫu.

**Kiểm tra kết quả:**

- Test xử lý được nhiều dòng trong một chuỗi.
- Không suy ra thông tin y khoa từ dữ liệu đồ chơi.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Python thuần với chuỗi tổng hợp; không cần dữ liệu cá nhân

## Học sâu từ tài liệu gốc

- [Rosalind Problems](https://rosalind.info/problems/locations/)
- [Python Tutorial](https://docs.python.org/3/tutorial/index.html)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
