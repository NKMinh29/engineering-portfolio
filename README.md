# Engineering Portfolio & Learning Atlas

A practical learning and project-design hub by **NKMinh29**.

The focus is embedded automotive engineering, with structured exploration of
software, AI, robotics, electronics, security and design. Learning notes are in Vietnamese.

**Status:** 48 learning modules and 15 project blueprints. A blueprint records an
intended product, its architecture and acceptance criteria; it does not claim that
the product has already been implemented or validated.

## Start here

1. [Learning map and topic index](learning/00_MUC_LUC_VA_LO_TRINH.md)
2. [Delivery roadmap](ROADMAP.md)
3. [Project blueprints](#project-blueprints)
4. [Reusable issue and README templates](templates/)

## Engineering focus

- Embedded C, automotive networks and testable ECU software.
- Reproducible measurements and AI deployment on constrained hardware.
- Useful software tools with small datasets, explicit interfaces and documented results.
- Windows-first exercises; heavy simulation is a later integration step.

## Project blueprints

| Project | Status |
|---|---|
| [01. Repo nghiên cứu CAN IDS / IMCOM 2027](projects/01_s32k144-can-ids-benchmark.md) | Thiết kế / kế hoạch nghiệm thu |
| [02. Công cụ phân tích log CAN dùng trên PC](projects/02_can-log-workbench.md) | Thiết kế / kế hoạch nghiệm thu |
| [03. Mô hình ba ECU theo kiến trúc Classic](projects/03_three-ecu-classic-lab.md) | Thiết kế / kế hoạch nghiệm thu |
| [04. Gateway dịch vụ để học kiến trúc Adaptive](projects/04_adaptive-service-gateway.md) | Thiết kế / kế hoạch nghiệm thu |
| [05. AI giám sát tình trạng thiết bị ở edge](projects/05_edge-condition-monitor.md) | Thiết kế / kế hoạch nghiệm thu |
| [06. Nền tảng IoT theo dõi đội robot/thiết bị](projects/06_fleet-telemetry-console.md) | Thiết kế / kế hoạch nghiệm thu |
| [07. Tìm kiếm tài liệu kỹ thuật có bằng chứng](projects/07_engineering-docs-search.md) | Thiết kế / kế hoạch nghiệm thu |
| [08. Nhận biết vật cản và tìm đường từ LiDAR](projects/08_lidar-navigation-lab.md) | Thiết kế / kế hoạch nghiệm thu |
| [09. Phân tích và phát lại nhiệm vụ drone](projects/09_drone-mission-replay.md) | Thiết kế / kế hoạch nghiệm thu |
| [10. Bo mở rộng nhúng có hồ sơ thiết kế và bring-up](projects/10_embedded-lab-carrier-board.md) | Thiết kế / kế hoạch nghiệm thu |
| [11. IP số UART, FIFO và PWM có testbench](projects/11_rtl-peripheral-lab.md) | Thiết kế / kế hoạch nghiệm thu |
| [12. Mô phỏng cập nhật firmware có chữ ký](projects/12_secure-update-lab.md) | Thiết kế / kế hoạch nghiệm thu |
| [13. Ứng dụng quản lý hoạt động câu lạc bộ](projects/13_clubops.md) | Thiết kế / kế hoạch nghiệm thu |
| [14. Thử nghiệm truy xuất bàn giao hàng hóa](projects/14_shipment-proof-ledger.md) | Thiết kế / kế hoạch nghiệm thu |
| [15. Giao diện vận hành robot và bộ thiết kế đồ họa](projects/15_robot-ops-design-system.md) | Thiết kế / kế hoạch nghiệm thu |

## How to use this repository

Pick one project. Work through its milestones, keep raw evidence, and distinguish
goals from measured results. Small exercises can remain under the learning atlas;
an independent product should get its own repository when it has a clear demo and setup.

The 48-module map is a broad starting point, not an exhaustive taxonomy of every
technology specialty. It can be extended as interests and projects develop.

## Existing work

- [S32K144 Mini BCM](https://github.com/NKMinh29/S32K144-Mini-BCM): register-level embedded learning.
- [AI4SE project](https://github.com/NKMinh29/N0body_ai4se): AI/web project repository.
- [Virtual Global Citizen](https://github.com/NKMinh29/MMT_InnoCodeCamp_2025): educational web project.
- [OpenCV demo](https://github.com/NKMinh29/opencv_demo): small C++ image-display exercise.

Repository links describe the projects; they do not assert that their current builds
or deployment environments were validated during preparation of this atlas.

## Attribution and sources

The learning materials and blueprints were prepared with AI assistance and should
be reviewed through practical implementation. Each module includes source links.
See [source notes](NGUON_VA_PHAM_VI.md). Linked third-party materials retain their own terms.
