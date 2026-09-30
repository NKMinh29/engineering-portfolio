# 23. Reinforcement learning và điều khiển thông minh

**Nhóm:** AI · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. State action reward.
2. Markov decision process.
3. Policy và value.
4. Exploration exploitation.
5. Q-learning.
6. Model based control.
7. Reward hacking.
8. Simulation to reality gap.
9. Safety constraints.

## Giảng nhanh

RL chọn hành động để tối đa tổng phần thưởng dài hạn; phần thưởng thiết kế sai có thể khiến agent hành xử trái mục tiêu. Điều khiển robot thật đòi hỏi giới hạn tốc độ, dừng khẩn và xác nhận độc lập; hãy học RL trước trong lưới mô phỏng có điều kiện dừng rõ.

## Bài tập ngắn

1. Tính một bước update Q(s,a) từ reward và giá trị kế tiếp.
2. Đề xuất reward làm xe đến đích mà không cắt góc qua tường.

## Project portfolio: Agent tìm đường trong gridworld

**Các bước thực hiện:**

1. Thiết kế lưới 6×6 có mục tiêu và tường.
2. Viết simulator với seed và điều kiện kết thúc.
3. Làm baseline BFS để so chất lượng đường.
4. Huấn luyện tabular Q-learning với nhiều seed.
5. Vẽ success rate và độ dài tuyến trên 100 episode test.

**Kiểm tra kết quả:**

- Agent không đi xuyên tường.
- Báo đủ số episode train và kết quả ít nhất ba seed.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Python nhỏ trên Colab; chỉ mô phỏng

## Học sâu từ tài liệu gốc

- [Gymnasium Basic Usage](https://gymnasium.farama.org/introduction/basic_usage/)
- [Sutton Barto Book](http://incompleteideas.net/book/the-book-2nd.html)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
