# Bảo tàng và chiếc chìa khóa

Game khám phá theo mạch truyện: tỉnh dậy trong phòng trực, tìm hiểu việc tráo hiện vật, thu thập hồ sơ, lấy chìa khóa rồi quay về mở lối dưới giường.

Thiết kế phiên bản 3, ngày 12 tháng 10 năm 2026. Phiên bản này thay thế toàn bộ ý tưởng NPC đòi đồ và giết người. Bản này có 6 cụm event lớn và 12 event nhỏ. Chỉ E08 đóng khóa một phòng; các cụm còn lại dùng cơ chế khác nhau. Cảnh đánh ngất là tùy chọn, giữ nguyên tiến trình.

| Tài liệu | Nội dung | Đọc trên GitHub | Tải Word |
| --- | --- | --- | --- |
| Flow | Mạch truyện, đáp án, điều kiện bắt buộc, phát hiện sớm | [01_flow](docs/01_flow.md) | [DOCX](docx/01_flow.docx) |
| Clues | Từng ảnh, giấy, khung, chữ, item và Camera | [02_clues](docs/02_clues.md) | [DOCX](docx/02_clues.docx) |
| Kiến trúc | Các gian, đường nối, đối tượng và animation | [03_kien_truc](docs/03_kien_truc.md) | [DOCX](docx/03_kien_truc.docx) |
| Âm thanh và ánh sáng | Nguồn âm, chiếu sáng, phối hợp và hồi phục | [04_am_thanh_anh_sang](docs/04_am_thanh_anh_sang.md) | [DOCX](docx/04_am_thanh_anh_sang.docx) |
| Events | Cửa niêm phong, chim, quay đầu, truy âm, Camera, bản ghi và nhịp nghỉ | [05_events](docs/05_events.md) | [DOCX](docx/05_events.docx) |

Đọc Flow trước, sau đó Clues. Các tài liệu dùng chung mã phòng R, ảnh F, giấy I, ảnh/bảng tường W, hiện vật D, vật phẩm O, âm A, ánh sáng L và sự kiện E. Không cần tọa độ để đọc bản này.

Thời lượng 120 đến 150 phút là mục tiêu cho lượt chơi đầu, cần kiểm chứng bằng prototype và chơi thử. Tài liệu chưa phải một bản game đã triển khai.

Cửa R03 dùng câu đố nhiều nguồn đã chốt, có đáp án 3581; mọi dữ liệu mở cửa nằm trong R03. I12 là phiếu gốc nối cụm này vào 19 nguồn hồ sơ cuối. Các ảnh và giấy làm bằng chứng không đổi nội dung theo scare.
