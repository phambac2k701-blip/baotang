# Bảo tàng và chiếc chìa khóa

Game khám phá theo mạch truyện: tỉnh dậy trong phòng trực, tìm hiểu việc tráo hiện vật, thu thập hồ sơ, lấy chìa khóa rồi quay về mở lối dưới giường.

Thiết kế phiên bản 4, ngày 12 tháng 10 năm 2026. Phiên bản này thay thế toàn bộ ý tưởng NPC đòi đồ và giết người. Bản này có 6 cụm event lớn và 12 event nhỏ. Chỉ E08 đóng khóa một phòng; các cụm còn lại dùng cơ chế khác nhau. Cảnh đánh ngất là tùy chọn, giữ nguyên tiến trình.

| Tài liệu | Nội dung | Đọc trên GitHub |
| --- | --- | --- |
| Flow | Mạch truyện, đáp án, điều kiện bắt buộc, phát hiện sớm | [01_flow](docs/01_flow.md) |
| Clues | Từng ảnh, giấy, khung, chữ, item và Camera | [02_clues](docs/02_clues.md) |
| Kiến trúc | Các gian, đường nối, đối tượng và animation | [03_kien_truc](docs/03_kien_truc.md) |
| Âm thanh và ánh sáng | Nguồn âm, chiếu sáng, phối hợp và hồi phục | [04_am_thanh_anh_sang](docs/04_am_thanh_anh_sang.md) |
| Events | Cửa niêm phong, chim, quay đầu, truy âm, Camera, bản ghi và nhịp nghỉ | [05_events](docs/05_events.md) |
| Bản dựng thử | Nhà chữ L hai tầng, từng phòng/tường/cửa/prop, vị trí shape, nội dung Xem và balo, chia 17 block | [06_draft_kien_truc_va_items](docs/06_draft_kien_truc_va_items.md) |
| Thế giới ngất và ngôn ngữ | E06 chạy ba làn/cổng/tỉnh/đốm sáng; preview khách quan tách khỏi manh mối | [07_the_gioi_ngat_va_quy_tac_thong_tin](docs/07_the_gioi_ngat_va_quy_tac_thong_tin.md) |

Tài liệu dự án dùng định dạng Markdown (.md). Mở từng tài liệu để đọc hoặc tải về. Đọc Flow trước, sau đó Clues. Các tài liệu dùng chung mã phòng R, ảnh F, giấy I, ảnh/bảng tường W, hiện vật D, vật phẩm O, âm A, ánh sáng L và sự kiện E. Không cần tọa độ để đọc bản này.

Thời lượng 120 đến 150 phút là mục tiêu cho lượt chơi đầu, cần kiểm chứng bằng prototype và chơi thử. Tài liệu chưa phải một bản game đã triển khai.

Cửa R03 dùng câu đố nhiều nguồn đã chốt, có đáp án 3581; mọi dữ liệu mở cửa nằm trong R03. I12 là phiếu gốc nối cụm này vào 19 nguồn hồ sơ cuối. Các ảnh và giấy làm bằng chứng không đổi nội dung theo scare.

Để giao AI dựng bản cơ bản, dùng tài liệu 06 theo các lượt A–G. Tài liệu này cụ thể hóa vị trí thử và chép đủ nội dung nguồn; đợt âm thanh, ánh sáng và asset đẹp thực hiện sau. Cơ chế ghép chương trình hiện được đặt thành môđun thử tùy chọn, chưa thay flow chính.

Khi giao AI build: dựng nhà/placeholder/items/balo theo 06 trước, rồi thêm scene NG theo 07. Dùng bảng preview đã tách trong 02/06/07; nội dung in trên ảnh/giấy vẫn là manh mối, không biến đoạn giải thích thiết kế thành lời UI. Repo chứa tài liệu thiết kế, chưa chứa scene game đã triển khai.
