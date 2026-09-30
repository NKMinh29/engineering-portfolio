# 12. Mô phỏng cập nhật firmware có chữ ký

**Tên repo đề xuất:** `secure-update-lab`  
**Ưu tiên:** P2 — security ứng dụng  
**Năng lực:** AppSec, embedded security, cryptography, OTA, testing  
**Ước lượng lập kế hoạch:** 30–55 giờ. Không phải cam kết; chưa tính toàn bộ thời gian học nền tảng.

> Trạng thái: bản thiết kế. Prototype CAN Log Workbench được chuẩn bị riêng; các sản phẩm khác cần triển khai hoặc nhập artifact gốc. Tiêu chí nghiệm thu là mục tiêu, chưa phải kết quả đã đạt.

## 1. Người dùng và bài toán

Thiết bị cần chỉ nhận gói firmware đúng thiết bị, đúng phiên bản và còn nguyên vẹn; phải có hành vi rõ khi cập nhật bị ngắt.

## 2. MVP — phiên bản nhỏ nhất đủ demo

- Host tool tạo manifest và ký bằng thư viện crypto đã được duy trì.
- Verifier kiểm tra chữ ký, hash, device target và monotonic version.
- A/B slot giả lập bằng file, test bị ngắt giữa các bước.

## 3. Kiến trúc và hợp đồng dữ liệu

Package builder → signed manifest + payload → verifier → inactive slot → pending boot → health confirmation → active slot. Trusted public key được cấu hình ngoài gói tải về.

**Hợp đồng:** Manifest {format_version, device_model, firmware_version, payload_sha256, payload_size, signing_key_id}. Quy định canonical bytes được ký; không tự chế thuật toán mật mã.

## 4. Công cụ và môi trường

Python host simulation trước; thư viện cryptography cho primitives. Firmware MCU là extension khi đã xác định flash layout và boot chain.

## 5. Cấu trúc repo đề xuất

- `packager/`: manifest và signing
- `verifier/`: checks
- `device_sim/`: slots và boot state
- `tests/`: tamper, downgrade, interruption
- `docs/`: threat model và trust boundary

## 6. Milestones để chuyển thành GitHub Issues

1. Viết attacker model: sửa payload, replay bản cũ, tráo target, ngắt cập nhật.
2. Chốt signed bytes và key lifecycle demo.
3. Viết verifier fail-closed; tạo fixture hợp lệ/bị sửa.
4. Thiết kế state machine A/B và test power interruption bằng simulation.
5. Lưu test report; mô tả khoảng cách từ host prototype tới MCU.
6. Tích hợp target chỉ khi có cơ chế recovery và board thử.

Mỗi milestone là một issue cha; tách task chỉ khi đủ nhỏ để có output và cách kiểm tra trong một buổi làm. Commit theo thay đổi thật, không tạo lịch sử đóng góp giả.

## 7. Nghiệm thu

- Payload sửa một byte, manifest sai target, chữ ký sai, version thấp đều bị từ chối.
- Package tự mang public key mới không được tự động tin cậy.
- Restart ở từng bước không làm chọn slot chưa xác minh.
- Public repo chỉ chứa key test ghi nhãn rõ; key triển khai phải được tạo riêng.

## 8. Bằng chứng đưa lên portfolio

Cập nhật đúng, sửa payload rồi thử lại, rollback attempt và restart giữa chừng.

README cần: bài toán → demo → cách chạy → kiến trúc → kết quả đo → hạn chế → phần đóng góp của Minh → nguồn và license. Số đo phải gắn thiết bị/cấu hình/dataset; không đặt badge test pass trước khi có workflow chạy thật.

## 9. Giảng nhanh

Hash giúp phát hiện thay đổi khi giá trị hash đáng tin; chữ ký giúp gắn manifest với key được tin. Nếu attacker sửa được cả payload và hash không được ký, kiểm tra hash đơn thuần không xác thực tác giả.

## 10. Phạm vi và bước tiếp theo

Host A/B simulation chưa là secure boot và không chứng minh chống physical attacks. Không công bố “production secure” chỉ từ unit test.

## Tài liệu gốc

- cryptography docs — https://cryptography.io/en/latest/

Tình trạng kiểm tra liên kết ghi trong `../NGUON_VA_PHAM_VI.md`. Tài liệu là điểm bắt đầu học; thiết kế MVP và nghiệm thu ở đây là đề xuất riêng cho portfolio của Minh.
