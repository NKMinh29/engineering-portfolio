# Bản đồ tự học công nghệ: từ CNTT tới automotive, điện tử và thiết kế

**Phiên bản:** 2026-09-28 · **Ngôn ngữ:** Tiếng Việt · **Định dạng:** một file Markdown cho một chuyên đề.

## Phạm vi và cách dùng

Bộ này là **bản đồ nhập môn có thực hành**, không tương đương một chương trình cử nhân hoàn chỉnh hay chứng chỉ nghề. “Tất cả chuyên ngành” không có danh sách đóng; danh mục dưới đây đối chiếu **17 vùng kiến thức CS2023** với hướng đào tạo công khai của HUST/FPT, rồi bổ sung các nhánh automotive, robot, bán dẫn và sáng tạo số theo yêu cầu. Một file bao gồm phạm vi cần học, một ý được giảng nhanh, bài tập, project có bước làm/kiểm chứng và tài liệu gốc cho phần dài. **Không cần học theo số thứ tự tuyệt đối.**

### Mốc dành riêng cho Minh

- Đã có: S32K144, CAN IDS, FreeRTOS, EB tresos/Classic và PCB EasyEDA. Hãy dùng các project cũ làm đầu vào cho bài mới, ghi rõ điều gì thực sự đã chạy trên phần cứng.
- Máy Windows còn khoảng 20 GB: ưu tiên tài liệu web, GitHub, HDLBits, Colab, EasyEDA, bộ dữ liệu mẫu nhỏ. ROS/Gazebo/CARLA hay thiết kế chip đầy đủ có thể học lý thuyết trước, thực hành trên máy lab/từ xa khi có tài nguyên.
- Mỗi tháng: 1 project chính 12–20 giờ, 2 bài tập nhỏ, đọc 2 chuyên đề khác ở mức nhập môn. Tăng giảm theo lịch học trên trường.

### Nền tảng chung trước project lớn

Python hoặc C/C++, Git, thuật toán, toán rời rạc + xác suất, mạng và hệ điều hành là các tiền đề lặp lại. Đừng đợi xong tất cả mới bắt đầu project: chọn bài đơn giản, quay lại học đúng phần thiếu.

### Sản phẩm GitHub tối thiểu

`README.md` có mục tiêu, sơ đồ hoặc ảnh, hướng dẫn chạy, dữ liệu nhỏ, kết quả thực tế, cách tái lập, hạn chế; commit của bạn; thư mục `src/`, `tests/` khi phù hợp; `docs/` cho sơ đồ; `.gitignore`; không chứa bí mật. Thông tin hỗ trợ học thuật cần trích dẫn, phân biệt tác phẩm tham khảo với phần tự làm.

## Mục lục từng chuyên đề

### Nền tảng (5)

- [01. Toán cho khoa học máy tính](01_nen_tang/01_toan-cho-khoa-hoc-may-tinh.md)
- [02. Lập trình cấu trúc dữ liệu và thuật toán](01_nen_tang/02_lap-trinh-cau-truc-du-lieu-va-thuat-toan.md)
- [03. Ngôn ngữ lập trình và trình biên dịch](01_nen_tang/03_ngon-ngu-lap-trinh-va-trinh-bien-dich.md)
- [04. Kiến trúc máy tính và hệ điều hành](01_nen_tang/04_kien-truc-may-tinh-va-he-dieu-hanh.md)
- [05. Mạng máy tính và truyền thông](01_nen_tang/05_mang-may-tinh-va-truyen-thong.md)

### Phần mềm & dữ liệu (11)

- [06. Kỹ nghệ phần mềm kiểm thử và quản lý project](02_phan_mem_du_lieu/06_ky-nghe-phan-mem-kiem-thu-va-quan-ly-project.md)
- [07. Backend API và kiến trúc dịch vụ](02_phan_mem_du_lieu/07_backend-api-va-kien-truc-dich-vu.md)
- [08. Frontend web và truy cập được](02_phan_mem_du_lieu/08_frontend-web-va-truy-cap-duoc.md)
- [09. Ứng dụng di động đa nền tảng](02_phan_mem_du_lieu/09_ung-dung-di-dong-da-nen-tang.md)
- [10. Cơ sở dữ liệu SQL và NoSQL](02_phan_mem_du_lieu/10_co-so-du-lieu-sql-va-nosql.md)
- [11. Kỹ thuật dữ liệu và phân tích](02_phan_mem_du_lieu/11_ky-thuat-du-lieu-va-phan-tich.md)
- [12. Cloud DevOps hệ phân tán và SRE](02_phan_mem_du_lieu/12_cloud-devops-he-phan-tan-va-sre.md)
- [13. UX HCI và thiết kế giao diện](02_phan_mem_du_lieu/13_ux-hci-va-thiet-ke-giao-dien.md)
- [14. Blockchain và hợp đồng thông minh](02_phan_mem_du_lieu/14_blockchain-va-hop-dong-thong-minh.md)
- [15. Đồ họa lập trình và kỹ thuật đa phương tiện](02_phan_mem_du_lieu/15_do-hoa-lap-trinh-va-ky-thuat-da-phuong-tien.md)
- [16. Game engine mô phỏng và XR](02_phan_mem_du_lieu/16_game-engine-mo-phong-va-xr.md)

### AI (9)

- [17. Machine learning và khoa học dữ liệu](03_ai/17_machine-learning-va-khoa-hoc-du-lieu.md)
- [18. Deep learning và mô hình nền tảng](03_ai/18_deep-learning-va-mo-hinh-nen-tang.md)
- [19. NLP mô hình ngôn ngữ và RAG](03_ai/19_nlp-mo-hinh-ngon-ngu-va-rag.md)
- [20. Computer vision và xử lý ảnh](03_ai/20_computer-vision-va-xu-ly-anh.md)
- [21. Xử lý tiếng nói âm thanh và tín hiệu số](03_ai/21_xu-ly-tieng-noi-am-thanh-va-tin-hieu-so.md)
- [22. Tìm kiếm gợi ý và hệ thống thông tin](03_ai/22_tim-kiem-goi-y-va-he-thong-thong-tin.md)
- [23. Reinforcement learning và điều khiển thông minh](03_ai/23_reinforcement-learning-va-dieu-khien-thong-minh.md)
- [24. MLOps đánh giá mô hình và quản trị dữ liệu](03_ai/24_mlops-danh-gia-mo-hinh-va-quan-tri-du-lieu.md)
- [25. Edge AI TinyML và tối ưu MCU](03_ai/25_edge-ai-tinyml-va-toi-uu-mcu.md)

### Bảo mật (3)

- [26. An ninh mạng và phòng thủ hệ thống](04_bao_mat/26_an-ninh-mang-va-phong-thu-he-thong.md)
- [27. Bảo mật ứng dụng mật mã và quyền riêng tư](04_bao_mat/27_bao-mat-ung-dung-mat-ma-va-quyen-rieng-tu.md)
- [28. Bảo mật xe robot và IoT](04_bao_mat/28_bao-mat-xe-robot-va-iot.md)

### Phần cứng & nhúng (5)

- [29. Logic số HDL và FPGA](05_phan_cung_nhung/29_logic-so-hdl-va-fpga.md)
- [30. Vi mạch bán dẫn và thiết kế IC](05_phan_cung_nhung/30_vi-mach-ban-dan-va-thiet-ke-ic.md)
- [31. Điện tử analog nguồn và thiết kế PCB](05_phan_cung_nhung/31_dien-tu-analog-nguon-va-thiet-ke-pcb.md)
- [32. Lập trình nhúng và RTOS](05_phan_cung_nhung/32_lap-trinh-nhung-va-rtos.md)
- [33. IoT cảm biến và mạng không dây](05_phan_cung_nhung/33_iot-cam-bien-va-mang-khong-day.md)

### Automotive (4)

- [34. AUTOSAR Classic SWC RTE BSW](06_automotive/34_autosar-classic-swc-rte-bsw.md)
- [35. AUTOSAR Adaptive và kiến trúc ECU hiệu năng cao](06_automotive/35_autosar-adaptive-va-kien-truc-ecu-hieu-nang-cao.md)
- [36. ADAS cảm biến và kiểm thử theo kịch bản](06_automotive/36_adas-cam-bien-va-kiem-thu-theo-kich-ban.md)
- [37. Mạng trong xe chẩn đoán và an toàn chức năng](06_automotive/37_mang-trong-xe-chan-doan-va-an-toan-chuc-nang.md)

### Robot & drone (3)

- [38. ROS 2 node topic service và robot software](07_robot_drone/38_ros-2-node-topic-service-va-robot-software.md)
- [39. LiDAR point cloud SLAM và dẫn đường](07_robot_drone/39_lidar-point-cloud-slam-va-dan-duong.md)
- [40. Drone autopilot PX4 ArduPilot và MAVLink](07_robot_drone/40_drone-autopilot-px4-ardupilot-va-mavlink.md)

### Thiết kế & liên ngành (8)

- [41. Thiết kế đồ họa 2D và nhận diện](08_thiet_ke_lien_nganh/41_thiet-ke-do-hoa-2d-va-nhan-dien.md)
- [42. Thiết kế 3D hoạt hình và truyền thông số](08_thiet_ke_lien_nganh/42_thiet-ke-3d-hoat-hinh-va-truyen-thong-so.md)
- [43. GIS bản đồ và dữ liệu không gian](08_thiet_ke_lien_nganh/43_gis-ban-do-va-du-lieu-khong-gian.md)
- [44. Tin sinh học và dữ liệu khoa học](08_thiet_ke_lien_nganh/44_tin-sinh-hoc-va-du-lieu-khoa-hoc.md)
- [45. Điện toán lượng tử nhập môn](08_thiet_ke_lien_nganh/45_dien-toan-luong-tu-nhap-mon.md)
- [46. Khoa học dữ liệu sản phẩm và thống kê thực nghiệm](08_thiet_ke_lien_nganh/46_khoa-hoc-du-lieu-san-pham-va-thong-ke-thuc-nghiem.md)
- [47. Kỹ thuật viễn thông RF và thông tin số](08_thiet_ke_lien_nganh/47_ky-thuat-vien-thong-rf-va-thong-tin-so.md)
- [48. Đạo đức công nghệ nghiên cứu và portfolio](08_thiet_ke_lien_nganh/48_dao-duc-cong-nghe-nghien-cuu-va-portfolio.md)

## Ma trận kiểm kê theo CS2023

| Vùng kiến thức CS2023 | File đại diện |
|---|---|
| Algorithmic Foundations | 02 |
| Architecture and Organization | 04, 29, 30 |
| Artificial Intelligence | 17–25, 36 |
| Data Management | 10, 11 |
| Foundations of Programming Languages | 03 |
| Graphics and Interactive Techniques | 15, 16, 20, 41, 42 |
| Human-Computer Interaction | 08, 13, 41 |
| Mathematical and Statistical Foundations | 01 |
| Networking and Communication | 05, 33, 37 |
| Operating Systems | 04, 32 |
| Parallel and Distributed Computing | 12 |
| Security | 26–28, 37 |
| Society, Ethics, and the Profession | 06, 24, 48 |
| Software Development Fundamentals | 02, 06 |
| Software Engineering | 06–09 |
| Specialized Platform Development | 09, 16, 32, 38, 42 |
| Systems Fundamentals | 04–05, 12, 32 |

Ma trận là **đối chiếu phạm vi**, không khẳng định các file là giáo trình chính thức của trường hoặc CS2023. Danh mục bổ sung ngoài CS gồm PCB, AUTOSAR, ADAS, robotics, bán dẫn, thiết kế đồ họa, bioinformatics và điện toán lượng tử.

## Thứ tự gợi ý (12 tháng, có thể kéo dài)

1. **Tháng 1–3:** 01–06, 10; làm công cụ phân tích log CAN và README đo đạc.
2. **Tháng 4–6:** 07–16, 26–28, 31–34; làm dashboard dữ liệu cảm biến, demo RTOS và PCB.
3. **Tháng 7–9:** 17–25, 35–38, 43–45; làm notebook AI/LiDAR, kịch bản ADAS và demo hệ thống.
4. **Tháng 10–12:** 29–30, 39–42, 46–48; thử HDL, thiết kế số, đồ họa và 1 nhánh liên ngành; chọn 2 project mạnh nhất để hoàn thiện.

## Chuẩn đối chiếu

- [HUST SoICT – Khoa học máy tính](https://soict.hust.edu.vn/chuong-trinh-khoa-hoc-may-tinh-ma-tuyen-sinh-it1.html), [Kỹ thuật máy tính](https://soict.hust.edu.vn/chuong-trinh-dao-tao-cong-nghe-thong-tin-ky-thuat-may-tinh-it2.html), [Điện tử viễn thông](https://ts.hust.edu.vn/training-cate/nganh-dao-tao-dai-hoc/dien-tu-va-vien-thong).
- [FPTU – danh mục ngành/chuyên ngành](https://daihoc.fpt.edu.vn/chuong-trinh-dao-tao/) và [Thiết kế đồ họa/mỹ thuật số](https://daihoc.fpt.edu.vn/chuyen-nganh/thiet-ke-do-hoa-va-my-thuat-so/).
- [ACM/IEEE-CS/AAAI CS2023 – 17 vùng kiến thức](https://csed.acm.org/knowledge-areas/).
