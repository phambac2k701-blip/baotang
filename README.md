# Bảo tàng và chiếc chìa khóa

Game khám phá theo mạch truyện: tỉnh dậy trong phòng trực, tìm hiểu việc tráo hiện vật, thu thập hồ sơ, lấy chìa khóa rồi quay về mở lối dưới giường.

## Nguồn build kiến trúc hiện hành

AI bắt đầu từ scene Blender mới và dùng hai nguồn:

1. **[docs/06_cach_build_bao_tang.md](docs/06_cach_build_bao_tang.md)** — hướng dẫn build toàn bộ từ đầu, prompt, trình tự thiết kế bên trong, kiểm tra và bàn giao.
2. **[assets/architecture/khung_bao_tang_v1.zip](assets/architecture/khung_bao_tang_v1.zip)** — hình bao, tọa độ đường cong, mặt bằng và kích thước.

Giải nén ZIP vào museum_architecture/source/. Thực hiện phiên 1 dựng khung rồi phiên 2 thiết kế/dựng toàn bộ kiến trúc bên trong trên cùng mô hình. Checkpoint trung gian được tạo trong chính quy trình này.

Phạm vi: **kiến trúc thô hoàn chỉnh trong Blender**. Chưa làm vật liệu, texture, props, item, gameplay, Meshy, âm thanh/ánh sáng kinh dị hoặc chuyển sang Godot. Các file gameplay bên dưới là nội dung cho giai đoạn sau, không phải bản vẽ để dựng nhà.

## Trạng thái thiết kế

- Hình bao đã được duyệt: bảo tàng ba thùy cong lệch, hai tầng, dải trưng bày mở quanh giếng trời.
- Hình bao ngoài khoảng 16,03 × 12,99 m; tổng diện tích bao sàn hai tầng khoảng 264 m², gồm vùng tường/thang và trừ giếng trời.
- ZIP chứa khung hình học sơ bộ và script minh họa; chưa chứa model Blender đã hoàn thiện.
- Kiến trúc bên trong cần được thiết kế, dựng và kiểm tra theo file 06, gồm các mặt tường/trần, cách nối gian, cột/vòm, thang và tuyến thoát.
- Dữ liệu tọa độ và bản vẽ có số đo ưu tiên hơn ảnh concept. Bàn giao phải có mặt bằng, mặt đứng, mặt cắt và góc ngang mắt.

## Tài liệu gameplay cho giai đoạn sau

| File | Nội dung |
| --- | --- |
| [idea.md](idea.md) | Ý tưởng và mục tiêu game |
| [01_flow](docs/01_flow.md) | Mạch truyện, câu đố, điều kiện và ending |
| [02_clues](docs/02_clues.md) | Nội dung ảnh, giấy, hiện vật, item và Camera |
| [04_am_thanh_anh_sang](docs/04_am_thanh_anh_sang.md) | Thiết kế âm thanh/ánh sáng |
| [05_events](docs/05_events.md) | Event lớn/nhỏ và nhịp nghỉ |
| [07_the_gioi_ngat_va_quy_tac_thong_tin](docs/07_the_gioi_ngat_va_quy_tac_thong_tin.md) | Nhánh thế giới ngất và ngôn ngữ preview |

Các mã R là vùng chức năng của gameplay. Các mã P0/P1/P2/P3 trong ZIP là vùng kiến trúc; không mặc định đồng nhất chúng với mã câu đố. Việc ánh xạ item/event sang vị trí thật thực hiện sau khi kiến trúc bên trong được chốt.

Preview khi nhấn Xem là mô tả khách quan; chữ và hình trong ảnh/giấy là manh mối. Thời lượng 120–150 phút là mục tiêu cần kiểm chứng bằng prototype. Repo hiện chứa tài liệu và nguồn hình học, chưa chứa model .blend hoặc scene game hoàn chỉnh.
