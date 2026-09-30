# 05. AI giám sát tình trạng thiết bị ở edge

**Tên repo đề xuất:** `edge-condition-monitor`  
**Ưu tiên:** P2 — sau khi đóng gói IMCOM  
**Năng lực:** TinyML, DSP, embedded AI, MLOps, embedded C  
**Ước lượng lập kế hoạch:** 35–65 giờ, cộng thời gian thu dữ liệu. Không phải cam kết; chưa tính toàn bộ thời gian học nền tảng.

> Trạng thái: bản thiết kế. Prototype CAN Log Workbench được chuẩn bị riêng; các sản phẩm khác cần triển khai hoặc nhập artifact gốc. Tiêu chí nghiệm thu là mục tiêu, chưa phải kết quả đã đạt.

## 1. Người dùng và bài toán

Người vận hành muốn nhận biết trạng thái bất thường của một motor/quạt từ tín hiệu cảm biến và biết model tốn bao nhiêu RAM/thời gian trên MCU.

## 2. MVP — phiên bản nhỏ nhất đủ demo

- Pipeline cửa sổ tín hiệu → feature RMS/variance → baseline threshold và model nhỏ.
- Chia dữ liệu theo phiên thu độc lập; báo cáo confusion matrix và lỗi tiêu biểu.
- C inference và host parity; đo trên MCU khi có cảm biến/board tương thích.

## 3. Kiến trúc và hợp đồng dữ liệu

Sensor/CSV → windowing → feature extractor → model → state smoothing → alert log. Huấn luyện offline, export cố định cùng scaler; inference không tự fit lại dữ liệu.

**Hợp đồng:** sample {session_id, timestamp_us, channel, value, unit, label}; model manifest {window_size, sample_rate_hz, feature_order, scale, model_hash}. Nhãn tổng hợp dùng thử pipeline phải được tách khỏi đánh giá cảm biến thật.

## 4. Công cụ và môi trường

Python/NumPy/scikit-learn cho baseline; C cho inference; Windows. Không cần GPU hoặc tải model ngôn ngữ. Cảm biến chỉ mua khi đã chốt giao tiếp và nguồn.

## 5. Cấu trúc repo đề xuất

- `data/manifests/`: sessions và quyền sử dụng
- `training/`: split, features, baseline
- `export/`: model/scaler
- `firmware/`: inference adapter
- `evaluation/`: parity, metrics, timing

## 6. Milestones để chuyển thành GitHub Issues

1. Mô tả 2–3 trạng thái có thể thu dữ liệu an toàn.
2. Thu nhiều phiên và khóa test sessions trước khi thử model.
3. Dựng threshold baseline rồi mới thêm classifier.
4. Export scaler/model, tạo test vectors và kiểm tra score trên host C.
5. Chạy board và đo p50/p95/max, RAM/flash cùng cấu hình compiler.
6. Viết model card giải thích lỗi và domain shift.

Mỗi milestone là một issue cha; tách task chỉ khi đủ nhỏ để có output và cách kiểm tra trong một buổi làm. Commit theo thay đổi thật, không tạo lịch sử đóng góp giả.

## 7. Nghiệm thu

- Không để cửa sổ chồng lấn từ cùng phiên lọt qua train/test.
- Báo cáo theo class và session; kết quả không đạt mục tiêu vẫn được giữ.
- Host parity nằm trong tolerance đã công bố; MCU measurements có log gốc.
- Phân biệt inference-only và toàn pipeline khi đo.

## 8. Bằng chứng đưa lên portfolio

Replay ba phiên tín hiệu và biểu đồ alert; sau đó video sensor thực khi đã có bằng chứng.

README cần: bài toán → demo → cách chạy → kiến trúc → kết quả đo → hạn chế → phần đóng góp của Minh → nguồn và license. Số đo phải gắn thiết bị/cấu hình/dataset; không đặt badge test pass trước khi có workflow chạy thật.

## 9. Giảng nhanh

Data leakage có thể làm model tốt giả tạo: scaler fit trên toàn tập hoặc các cửa sổ gần giống nằm ở hai phía split. Chia theo session trước preprocessing giúp đánh giá gần bài toán triển khai hơn.

## 10. Phạm vi và bước tiếp theo

Chưa đặt mục tiêu accuracy giả định như 99%. Đây là monitor thử nghiệm, chưa chẩn đoán lỗi công nghiệp đã được chứng nhận.

## Tài liệu gốc

- scikit-learn pitfalls — https://scikit-learn.org/stable/common_pitfalls.html

Tình trạng kiểm tra liên kết ghi trong `../NGUON_VA_PHAM_VI.md`. Tài liệu là điểm bắt đầu học; thiết kế MVP và nghiệm thu ở đây là đề xuất riêng cho portfolio của Minh.
