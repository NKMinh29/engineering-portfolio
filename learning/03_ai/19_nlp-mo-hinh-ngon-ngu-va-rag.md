# 19. NLP mô hình ngôn ngữ và RAG

**Nhóm:** AI · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Tokenization và vocabulary.
2. Embedding và similarity.
3. Language model transformer.
4. Retrieval BM25 và vector.
5. Prompt và context.
6. RAG và trích dẫn.
7. Đánh giá factuality.
8. An toàn dữ liệu và injection.
9. Độ trễ chi phí và giới hạn context.

## Giảng nhanh

RAG tìm đoạn tài liệu liên quan rồi đưa vào bước trả lời. Kết quả có trích dẫn chỉ đáng tin khi đoạn gốc thật sự hỗ trợ phát biểu; vì vậy bài kiểm tra cần câu hỏi có đáp án đối chiếu và trường hợp tài liệu không chứa đáp án. RAG không biến dữ liệu sai thành tri thức đúng.

## Bài tập ngắn

1. Tự viết 5 câu hỏi từ một datasheet kèm trang đáp án.
2. Tạo câu hỏi không có đáp án và xem hệ thống có nói không biết.

## Project portfolio: Bộ tra cứu tài liệu S32K144 mini

**Các bước thực hiện:**

1. Chọn một tài liệu được quyền dùng và tách 10 đoạn ngắn có số trang.
2. Làm tìm kiếm từ khóa trước và xuất 3 đoạn phù hợp.
3. Thêm retrieval bằng embedding khi hiểu baseline.
4. Xây giao diện trả đoạn trích và link trang thay vì bịa câu trả lời.
5. Đánh giá 10 câu hỏi và ghi đúng sai thiếu nguồn.

**Kiểm tra kết quả:**

- Mỗi câu trả lời kèm vị trí đoạn chứng cứ.
- Khi thiếu dữ liệu hiển thị không tìm thấy.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Bắt đầu bằng tìm kiếm từ khóa Python không model; Colab khi thử embedding

## Học sâu từ tài liệu gốc

- [Hugging Face LLM Course](https://huggingface.co/learn/llm-course/chapter0/1)
- [PyTorch Tutorials](https://docs.pytorch.org/tutorials/)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
