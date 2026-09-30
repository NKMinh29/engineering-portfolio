# 11. Kỹ thuật dữ liệu và phân tích

**Nhóm:** Phần mềm & dữ liệu · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Thu thập và xác thực dữ liệu.
2. CSV Parquet và schema.
3. Missing duplicate outlier.
4. ETL và ELT.
5. Batch và streaming.
6. Data lineage.
7. Chia tập train test tránh rò rỉ.
8. Dashboard KPI.
9. Chất lượng dữ liệu và provenance.

## Giảng nhanh

Dữ liệu hợp lệ về cú pháp chưa chắc đáng tin: timestamp trùng hoặc mất mẫu gây sai số đo. Nếu các dòng gần nhau từ cùng một run nằm cả tập train và test, mô hình dễ nhìn thấy mẫu gần giống trong lúc đánh giá. Với paper CAN, chia theo run có thể phản ánh khả năng tổng quát hóa hơn chia từng hàng ngẫu nhiên.

## Bài tập ngắn

1. Tạo CSV có số thứ tự mất đoạn và đếm gap.
2. Tính tỷ lệ missing theo mỗi run thay vì toàn bộ dữ liệu.

## Project portfolio: Pipeline kiểm toán dữ liệu CAN

**Các bước thực hiện:**

1. Đọc CSV run và xác thực cột kiểu dữ liệu đơn vị.
2. Phát hiện bản ghi lặp thiếu sequence và timestamp ngoài thứ tự.
3. Lập bảng thống kê theo run model và điều kiện timer.
4. Xuất file sạch cùng báo cáo lỗi mà không sửa dữ liệu gốc.
5. Ghi rõ quy tắc chia tập và nguồn từng đầu vào.

**Kiểm tra kết quả:**

- Chạy lặp lại tạo cùng báo cáo.
- Có ít nhất ba loại lỗi dữ liệu chủ ý được phát hiện.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Python và file CSV nhỏ của chính mình hoặc dữ liệu giả lập

## Học sâu từ tài liệu gốc

- [Python CSV](https://docs.python.org/3/library/csv.html)
- [Google ML Datasets](https://developers.google.com/machine-learning/crash-course/overfitting)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
