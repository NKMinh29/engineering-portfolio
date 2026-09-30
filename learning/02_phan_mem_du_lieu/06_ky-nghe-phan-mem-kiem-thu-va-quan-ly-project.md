# 06. Kỹ nghệ phần mềm kiểm thử và quản lý project

**Nhóm:** Phần mềm & dữ liệu · **Mục tiêu:** nắm nền tảng, tự làm một demo nhỏ và giải thích giới hạn của nó.

## Học những gì?

1. Yêu cầu chức năng phi chức năng.
2. User story và tiêu chí chấp nhận.
3. Thiết kế module giao diện.
4. Version control và review.
5. Unit integration system test.
6. Mock dữ liệu và khả năng tái lập.
7. CI và quality gate.
8. Logging và xử lý lỗi.
9. Giấy phép đạo đức kỹ thuật.

## Giảng nhanh

Một yêu cầu tốt chỉ rõ điều kiện kiểm chứng. “Hệ thống nhanh” không kiểm tra được; “95% bản ghi xử lý dưới 50 ms trên cấu hình X” có thể đo. Unit test kiểm tra logic nhỏ, integration test kiểm tra các khối phối hợp, end-to-end theo đường đi của người dùng.

## Bài tập ngắn

1. Viết 5 yêu cầu đo được cho demo đèn Manual/Auto.
2. Lập ma trận requirement → test cho một lỗi cảm biến.

## Project portfolio: Chuẩn hóa một repo project S32K144 đã làm

**Các bước thực hiện:**

1. Chọn project hiện có và tách source config docs logs.
2. Viết README về sơ đồ khối pin điện áp cách build flash.
3. Thêm bảng yêu cầu và kết quả kiểm tra với ảnh hoặc log.
4. Tạo issue cho một lỗi và commit bản sửa liên kết issue.
5. Viết đoạn limitations phân biệt đã thử với ý tưởng tương lai.

**Kiểm tra kết quả:**

- Người khác theo README tái lập được build hoặc mô phỏng.
- Mỗi yêu cầu chính có minh chứng kiểm thử cụ thể.

**Đưa lên GitHub:** tạo repo riêng gồm `README.md` (bài toán, kiến trúc, cách chạy, kết quả đo, giới hạn), mã nguồn hoặc file thiết kế, dữ liệu mẫu nhỏ/nguồn dữ liệu, ảnh chụp hoặc GIF demo, và giấy phép cho những tài sản được phép chia sẻ. Ghi rõ điều kiện chạy và commit theo các mốc thiết kế → demo → kiểm chứng. Tránh tải lên khóa API, dữ liệu riêng tư hoặc bộ dữ liệu lớn.

**Điều kiện thực hành:** Repo local hoặc GitHub trình duyệt; không cần cài CI máy riêng

## Học sâu từ tài liệu gốc

- [GitHub Get Started](https://docs.github.com/en/get-started)
- [GitHub Actions Quickstart](https://docs.github.com/en/actions/get-started/quickstart)

## Khi nào hoàn thành?

Bạn giải thích được đầu vào/đầu ra của demo, tự chạy lại từ README, cho thấy ít nhất một trường hợp thành công và một trường hợp lỗi hoặc giới hạn. Phần học sâu cần thêm thời gian: dùng nguồn trên để mở rộng sau khi bản cơ bản đã chạy.
