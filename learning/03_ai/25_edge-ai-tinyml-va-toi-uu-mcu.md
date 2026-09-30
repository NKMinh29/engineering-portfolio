# 25. Edge AI TinyML và tối ưu MCU

**Nhóm:** AI · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Edge vs MCU memory hierarchy.
2. Quantization INT8.
3. Model conversion.
4. Runtime hoặc mã inference viết tay.
5. CMSIS-NN và DSP.
6. Feature extraction.
7. Profiling cycle RAM flash.
8. Accuracy latency trade-off.
9. Robustness lỗi cảm biến.

## Giảng nhanh

Suy luận ở edge có thể là máy Linux trên robot; TinyML đặt inference lên vi điều khiển nhiều hạn chế hơn. Mô hình 8-bit có thể giảm kích thước, nhưng cần kiểm lại độ chính xác và chi phí đầu cuối gồm feature và giao tiếp. Paper S32K144 của bạn có đo đường xử lý deployed path: có thể dùng làm mẫu benchmark.

## Bài tập ngắn

1. Tính số byte trọng số của MLP 10–32–32–1 ở float32 và int8.
2. Liệt kê mọi bước trong timing boundary của IDS.

## Project portfolio: Từ mô hình PC tới đo trên S32K144

**Các bước thực hiện:**

1. Huấn luyện model nhỏ và xuất tham số có version.
2. Kiểm chứng 20 vector đầu vào cho đầu ra tương đương trên PC.
3. Tích hợp một đường inference nhẹ vào MCU nếu phù hợp.
4. Đo cycle RAM flash cùng các điều kiện timer on/off.
5. So sánh sai lệch dự đoán và nêu giới hạn clock/interrupt.

**Kiểm tra kết quả:**

- Thống nhất input output giữa PC và MCU.
- Báo rõ đường inference tự viết hay framework cụ thể.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Bắt đầu Colab và board S32K144 đã có; không cần mua MCU mới

## Học sâu từ tài liệu gốc

- [Arm CMSIS-NN Guide](https://www.arm.com/resources/guide/machine-learning-on-cortex-m)
- [Edge Impulse Docs](https://docs.edgeimpulse.com/docs)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
