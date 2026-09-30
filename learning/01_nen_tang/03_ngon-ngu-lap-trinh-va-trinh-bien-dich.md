# 03. Ngôn ngữ lập trình và trình biên dịch

**Nhóm:** Nền tảng · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Cơ chế kiểu tĩnh và động.
2. Scope và lifetime.
3. Stack heap và sở hữu tài nguyên.
4. Lexer parser AST.
5. Ngữ nghĩa và thông dịch.
6. Compiler pipeline và linker.
7. ABI và gọi hàm.
8. Undefined behavior trong C.
9. FFI và liên kết C Python.

## Giảng nhanh

Compiler biến mã thành mã máy qua nhiều bước; linker nối những symbol giữa các object. Nếu khai báo một hàm nhưng không cung cấp định nghĩa, lỗi thường xuất hiện ở bước liên kết. Lexer tách `x+2` thành token còn parser tạo cây biểu thức có thứ tự thực hiện.

## Bài tập ngắn

1. Tìm ba lỗi compile và ba lỗi link trong ví dụ C nhỏ.
2. Vẽ AST cho `(2+3)*4` và giải thích thứ tự.

## Project portfolio: Bộ thông dịch biểu thức mini

**Các bước thực hiện:**

1. Định nghĩa cú pháp số nguyên cộng trừ nhân ngoặc.
2. Viết tokenizer và parser theo độ ưu tiên toán tử.
3. Xây AST và hàm evaluate.
4. Báo vị trí lỗi ký tự hoặc ngoặc sai.
5. So sánh 20 biểu thức hợp lệ với Python để kiểm tra.

**Kiểm tra kết quả:**

- `2+3*4` cho 14 còn `(2+3)*4` cho 20.
- Input lỗi không làm chương trình sập không báo nguyên nhân.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Python tiêu chuẩn; chưa cần cài LLVM

## Học sâu từ tài liệu gốc

- [Python Language Reference](https://docs.python.org/3/reference/index.html)
- [LLVM Tutorial](https://llvm.org/docs/tutorial/)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
