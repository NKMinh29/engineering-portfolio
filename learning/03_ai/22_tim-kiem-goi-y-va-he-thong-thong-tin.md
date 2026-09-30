# 22. Tìm kiếm gợi ý và hệ thống thông tin

**Nhóm:** AI · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Inverted index.
2. Tokenization cho tìm kiếm.
3. Ranking BM25.
4. Vector similarity.
5. Relevance judgment.
6. Metrics P@k MRR NDCG.
7. Recommender content collaborative.
8. Cold start.
9. Phản hồi người dùng và bias.

## Giảng nhanh

Search tìm tài liệu cho một truy vấn; recommender gợi ý tài liệu ngay cả khi chưa có truy vấn rõ. Một danh sách kết quả có liên quan nhưng sắp sai vị trí vẫn gây tốn thời gian, vì vậy đánh giá thứ hạng cần xét k kết quả đầu thay vì chỉ đếm tổng số kết quả.

## Bài tập ngắn

1. Tạo inverted index cho 5 trang tài liệu.
2. Xếp top 3 bằng số lần từ khóa và chỉ ra trường hợp thất bại.

## Project portfolio: Công cụ tìm học liệu cho các chuyên đề

**Các bước thực hiện:**

1. Lập 30 mẩu tài liệu và metadata chủ đề nguồn.
2. Viết token hóa và tìm theo từ khóa.
3. Thêm ranking đơn giản và filter theo chủ đề.
4. Tạo 10 truy vấn với nhãn liên quan thủ công.
5. Tính precision@3 và phân tích ba truy vấn lỗi.

**Kiểm tra kết quả:**

- Truy vấn sai chính tả hoặc không kết quả có thông báo.
- Lưu nhãn đánh giá và công thức metric.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Có thể dùng Python thuần và JSON nhỏ

## Học sâu từ tài liệu gốc

- [Elasticsearch Relevance Guide](https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html)
- [Hugging Face LLM Course](https://huggingface.co/learn/llm-course/chapter0/1)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
