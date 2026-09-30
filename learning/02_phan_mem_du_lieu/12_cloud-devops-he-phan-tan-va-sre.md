# 12. Cloud DevOps hệ phân tán và SRE

**Nhóm:** Phần mềm & dữ liệu · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Process service container.
2. CI/CD.
3. Triển khai và rollback.
4. Queue và retry.
5. Horizontal scale.
6. Idempotency.
7. Logging metrics tracing.
8. Availability và SLO.
9. Consistency và failure modes.

## Giảng nhanh

Trong hệ phân tán, cùng một request có thể đến hai lần do timeout và retry. Thiết kế idempotent giúp xử lý lặp không tạo hai đơn hàng. SLO là mục tiêu đo được như “99% request đáp ứng dưới 200 ms”; cần định nghĩa phép đo cùng khoảng thời gian.

## Bài tập ngắn

1. Lập bảng retry khi API telemetry timeout và cách ngăn ghi trùng.
2. Viết một SLO cho dịch vụ cảnh báo.

## Project portfolio: Dịch vụ telemetry có CI và cơ chế retry

**Các bước thực hiện:**

1. Dùng project API chuyên đề 07 và thêm request_id duy nhất.
2. Viết test gửi cùng request_id hai lần.
3. Tạo workflow CI chạy test trên mỗi push.
4. Mô phỏng service thất bại và kiểm tra retry không nhân đôi bản ghi.
5. Thêm log cấu trúc và bảng tỷ lệ request thành công.

**Kiểm tra kết quả:**

- Workflow tự chạy và báo trạng thái test.
- Hai request cùng ID chỉ ghi một bản ghi.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** CI cloud cho project nhỏ; học Kubernetes khái niệm trước khi cài cluster

## Học sâu từ tài liệu gốc

- [GitHub Actions Quickstart](https://docs.github.com/en/actions/get-started/quickstart)
- [Kubernetes Basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
