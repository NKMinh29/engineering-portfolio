# 45. Điện toán lượng tử nhập môn

**Nhóm:** Thiết kế & liên ngành · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Bit và qubit.
2. Vector trạng thái.
3. Superposition và đo.
4. Cổng X H Z.
5. Tensor product.
6. Entanglement.
7. Quantum circuit.
8. Noise.
9. Giới hạn máy lượng tử hiện nay.

## Giảng nhanh

Qubit được mô tả bằng biên độ xác suất trước phép đo; phép đo cho kết quả cổ điển với xác suất phụ thuộc trạng thái. Cổng H đưa |0⟩ vào tổ hợp đều; đo nhiều lần cho tỷ lệ gần 50/50. Điều này không có nghĩa một qubit tự lưu hai bit đọc được cùng lúc.

## Bài tập ngắn

1. Tính xác suất đo từ biên độ 1/√2 và 1/√2.
2. Vẽ mạch H rồi đo và dự đoán phân bố.

## Project portfolio: Notebook mô phỏng mạch một và hai qubit

**Các bước thực hiện:**

1. Viết biểu diễn vector cho |0⟩ và ma trận H X.
2. Tính kết quả H|0⟩ và X|0⟩ bằng tay và code.
3. Mô phỏng 1000 lần đo với seed.
4. Thêm mạch 2 qubit đơn giản theo bài học IBM.
5. So sánh tần suất đo và xác suất lý thuyết cùng giới hạn mô phỏng.

**Kiểm tra kết quả:**

- Xác suất đầu ra cộng thành 1.
- Kết quả thống kê có dao động được diễn giải đúng.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Notebook Python nhỏ; không cần tài khoản máy lượng tử

## Học sâu từ tài liệu gốc

- [IBM Quantum Basics](https://quantum.cloud.ibm.com/learning/en/courses/basics-of-quantum-information)
- [IBM Quantum Learning](https://quantum.cloud.ibm.com/learning/en)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
