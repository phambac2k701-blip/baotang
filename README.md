# Bảo tàng và chiếc chìa khóa

Game khám phá theo mạch truyện: tỉnh dậy trong phòng trực, tìm hiểu việc tráo hiện vật, thu thập hồ sơ, lấy chìa khóa rồi quay về mở lối dưới giường.

## News — 13/10/2026

Đổi hướng kiến trúc sang **bảo tàng ba thùy cong lệch**, hai tầng, khoảng **264 m² tổng diện tích bao sàn**, có dải trưng bày mở quanh giếng trời. Hình bao đã được duyệt; kiến trúc chi tiết bên trong vẫn cần thiết kế và kiểm tra trong Blender.

- Thêm [khung_bao_tang_v1.zip](assets/architecture/khung_bao_tang_v1.zip): mặt bằng, các góc khung, cao độ, tọa độ đường cong và script minh họa.
- Thêm [kế hoạch kiến trúc thô Blender](docs/08_ke_hoach_kien_truc_tho_blender.md): hai phiên nối tiếp trên cùng mô hình, gồm thiết kế và dựng phần bên trong.
- Xóa tài liệu kiến trúc cũ, bản dựng nhà chữ L và hai SVG mặt bằng cũ khỏi bản hiện tại. Bản cũ vẫn tra được trong lịch sử Git.
- Phạm vi đang làm: **hoàn thiện kiến trúc thô trong Blender**. Chưa làm vật liệu, props, Meshy, âm thanh/ánh sáng kinh dị hoặc chuyển sang Godot.

Chi tiết cập nhật ở [NEWS.md](NEWS.md).

## Bắt đầu dựng kiến trúc

1. Tải và giải nén [ZIP kiến trúc](assets/architecture/khung_bao_tang_v1.zip).
2. Đọc README.md, geometry.json và ba bản vẽ PNG trong ZIP.
3. Đọc [kế hoạch Blender](docs/08_ke_hoach_kien_truc_tho_blender.md), dùng prompt phiên 1 rồi tiếp tục phiên 2 trên cùng mô hình.
4. Đối chiếu bằng mặt bằng, mặt đứng, mặt cắt và camera ngang mắt trước khi gọi kiến trúc thô là hoàn chỉnh.

ZIP là khung hình học sơ bộ, **không phải model Blender đã dựng hoặc thiết kế nội thất hoàn chỉnh**. draw_shell.py tạo hình minh họa; AI thực hiện phải dựng mesh có bề dày, ô mở thật, giao vách và thang. Dữ liệu tọa độ và bản vẽ có số đo ưu tiên hơn ảnh concept.

## Tài liệu truyện và gameplay

| Tài liệu | Nội dung | Đọc trên GitHub |
| --- | --- | --- |
| Ý tưởng | Mục tiêu, phong cách và cơ chế chính | [idea](idea.md) |
| Flow | Mạch truyện, đáp án, điều kiện bắt buộc, phát hiện sớm | [01_flow](docs/01_flow.md) |
| Clues | Từng ảnh, giấy, khung, chữ, item và Camera | [02_clues](docs/02_clues.md) |
| Âm thanh và ánh sáng | Thiết kế cho giai đoạn sau | [04_am_thanh_anh_sang](docs/04_am_thanh_anh_sang.md) |
| Events | Câu đố cửa, các cụm scare và nhịp nghỉ | [05_events](docs/05_events.md) |
| Thế giới ngất và ngôn ngữ | E06 chạy ba làn/cổng/tỉnh/đốm sáng; preview khách quan tách khỏi manh mối | [07_the_gioi_ngat_va_quy_tac_thong_tin](docs/07_the_gioi_ngat_va_quy_tac_thong_tin.md) |
| Kiến trúc mới | Workflow hoàn thiện khung ngoài và kiến trúc bên trong bằng Blender | [08_ke_hoach_kien_truc_tho_blender](docs/08_ke_hoach_kien_truc_tho_blender.md) |

Các mã R trong tài liệu gameplay hiện chỉ là **mã vùng chức năng**, không phải yêu cầu tái dựng mặt bằng cũ. Các mã P0/P1/P2/P3 trong ZIP là mã vùng của phương án kiến trúc mới; chưa đồng nhất chúng với mọi mã P/R trong câu đố. Việc ánh xạ nguồn, item và event sang vị trí thật sẽ làm sau khi kiến trúc bên trong được chốt. Không lấy vị trí hoặc tọa độ nhà cũ để dựng map mới.

Flow và Clues giữ phiên bản nội dung 4, ngày 12/10/2026: sáu cụm event lớn, 12 event nhỏ, chỉ E08 khóa một phòng; cảnh đánh ngất là tùy chọn. Cửa câu đố dùng đáp án 3581, mọi dữ liệu mở cửa nằm trong vùng đó. I12 nối cụm này vào 19 nguồn hồ sơ cuối. Nội dung ảnh/giấy không đổi theo scare.

Preview khi nhấn Xem là mô tả khách quan; chữ và hình thật trong ảnh/giấy là manh mối. Dùng danh mục nguồn và preview trong 02/07 khi triển khai gameplay về sau. Repo hiện là tài liệu thiết kế, chưa chứa scene game hoặc model .blend đã hoàn thiện. Thời lượng 120–150 phút là mục tiêu cần kiểm chứng bằng prototype.
