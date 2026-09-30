# 07. Tìm kiếm tài liệu kỹ thuật có bằng chứng

**Tên repo đề xuất:** `engineering-docs-search`  
**Ưu tiên:** P1/P2 — nhánh NLP nhẹ  
**Năng lực:** NLP, information retrieval, RAG, evaluation, backend  
**Ước lượng lập kế hoạch:** 25–45 giờ. Không phải cam kết; chưa tính toàn bộ thời gian học nền tảng.

> Trạng thái: bản thiết kế. Prototype CAN Log Workbench được chuẩn bị riêng; các sản phẩm khác cần triển khai hoặc nhập artifact gốc. Tiêu chí nghiệm thu là mục tiêu, chưa phải kết quả đã đạt.

## 1. Người dùng và bài toán

Người học cần tìm đúng đoạn giải thích trong ghi chú và tài liệu của mình, đồng thời biết câu trả lời dựa vào nguồn nào.

## 2. MVP — phiên bản nhỏ nhất đủ demo

- Index 20–50 ghi chú Markdown do bạn sở hữu, giữ filename và heading.
- Tìm kiếm BM25 hoặc TF-IDF baseline; trả top-k đoạn kèm link nguồn.
- Bộ 30 câu hỏi có đoạn liên quan được đánh dấu; đo recall@5 và ví dụ thất bại.

## 3. Kiến trúc và hợp đồng dữ liệu

Markdown parser → sections/chunks → sparse index → query → ranked passages. LLM generation là module tùy chọn sau khi retrieval baseline được đánh giá.

**Hợp đồng:** Chunk {doc_id, heading, text, source_path, content_hash}; QueryEval {query_id, query, relevant_chunk_ids, split}. Không đưa đáp án test vào tuning cùng lúc rồi báo test độc lập.

## 4. Công cụ và môi trường

Python, SQLite hoặc index file, web UI nhỏ trên Windows. Không bắt buộc tải LLM local; nếu dùng API phải thêm cost log và cơ chế giữ dữ liệu riêng.

## 5. Cấu trúc repo đề xuất

- `ingest/`: parser
- `retrieval/`: tokenizer/ranker
- `eval/`: queries và metrics
- `ui/`: query/results
- `docs/`: failure analysis

## 6. Milestones để chuyển thành GitHub Issues

1. Chọn corpus có quyền chia sẻ, chuẩn hóa heading và nguồn.
2. Tạo câu hỏi tìm thông tin, so sánh và câu hỏi ngoài corpus.
3. Làm lexical baseline và error analysis trước embeddings.
4. Đánh giá chunk size/ranking trên dev set; giữ test riêng.
5. Thêm answer generation với nguồn nếu thật sự giúp người dùng.
6. Viết report so baseline, latency và các trường hợp không tìm được.

Mỗi milestone là một issue cha; tách task chỉ khi đủ nhỏ để có output và cách kiểm tra trong một buổi làm. Commit theo thay đổi thật, không tạo lịch sử đóng góp giả.

## 7. Nghiệm thu

- Mọi kết quả hiển thị đúng nguồn và đoạn trích.
- Bảng recall@5 có script tính lại và query set kèm theo.
- Câu hỏi ngoài corpus được báo thiếu bằng chứng nếu có bước sinh trả lời.
- Không ghi “RAG hoàn chỉnh” khi repo mới có retrieval.

## 8. Bằng chứng đưa lên portfolio

Hỏi một câu về CAN/RTOS, mở đúng heading, rồi thử câu không có trong corpus.

README cần: bài toán → demo → cách chạy → kiến trúc → kết quả đo → hạn chế → phần đóng góp của Minh → nguồn và license. Số đo phải gắn thiết bị/cấu hình/dataset; không đặt badge test pass trước khi có workflow chạy thật.

## 9. Giảng nhanh

Retrieval chọn bằng chứng; generation diễn đạt câu trả lời. Đánh giá riêng hai khâu giúp biết lỗi đến từ tìm sai tài liệu hay diễn giải sai tài liệu.

## 10. Phạm vi và bước tiếp theo

MVP chạy bằng tìm kiếm truyền thống và tài liệu nhỏ. Phần LLM/embedding triển khai sau, không cần tăng dung lượng máy từ đầu.

## Tài liệu gốc

- scikit-learn documentation — https://scikit-learn.org/stable/

Tình trạng kiểm tra liên kết ghi trong `../NGUON_VA_PHAM_VI.md`. Tài liệu là điểm bắt đầu học; thiết kế MVP và nghiệm thu ở đây là đề xuất riêng cho portfolio của Minh.
