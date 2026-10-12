# News

## 13/10/2026 — Hướng dẫn build từ đầu tại docs/06

Nguồn giao AI chính: [06 — Cách build bảo tàng từ đầu](docs/06_cach_build_bao_tang.md) và [ZIP kiến trúc](assets/architecture/khung_bao_tang_v1.zip). File 06 có đầy đủ trình tự, tiêu chí bàn giao và prompt để AI bắt đầu với scene Blender mới rồi làm cả khung ngoài lẫn kiến trúc bên trong. Không cần model/checkpoint cũ hoặc lịch sử trò chuyện. Hai phiên là hai chặng nối tiếp; checkpoint được tạo trong phiên 1.

Kế hoạch được chuyển vào mục 06; không giữ file 08 trùng nội dung. NEWS.md chỉ là nhật ký cập nhật, không phải hướng dẫn build.

## 13/10/2026 — Thay kiến trúc cũ, hoàn thiện kiến trúc thô trong Blender

### Nguồn kiến trúc mới

- [ZIP khung bảo tàng V1](assets/architecture/khung_bao_tang_v1.zip): mặt bằng hai tầng, bốn góc từ cùng tọa độ, cao độ/kích thước phòng, geometry.json, draw_shell.py và README nguồn.
- [Kế hoạch Blender](docs/06_cach_build_bao_tang.md): phiên 1 dựng khung ngoài và các cao độ/vùng; phiên 2 thiết kế và dựng kiến trúc bên trong trên cùng mô hình.
- Phương án: ba thùy cong lệch quanh giếng trời, hình bao 16,03 × 12,99 m; tổng diện tích bao sàn hai tầng khoảng 264 m², gồm vùng tường/thang và trừ giếng trời.

### Phạm vi hiện tại

Hoàn thiện hình học kiến trúc trong Blender: tường/sàn/mái có bề dày, ô cửa, cách nối các gian, trần, cột/vòm, thang công cộng và đường xuống bí mật. Bàn giao .blend, script, mặt bằng, mặt đứng, mặt cắt, ảnh ngang mắt và báo cáo kiểm tra. Chưa làm vật liệu, đồ nội thất, hiện vật, Meshy, âm thanh/ánh sáng kinh dị hoặc nhập Godot.

Hình bao đã được duyệt; thiết kế chi tiết bên trong chưa được chốt. ZIP không chứa model .blend đã hoàn thiện. Hai phòng kho/phục chế trong khung sơ bộ nhỏ, cần kiểm tra sử dụng và khoảng đi ở phiên 2.

### Loại bỏ nguồn kiến trúc cũ

Xóa docs/03_kien_truc.md, docs/06_draft_kien_truc_va_items.md và hai SVG mặt bằng trong assets/draft/. Bỏ các chỉ dẫn build theo nhà chữ L/17 block. Lịch sử Git giữ các phiên bản trước để tra cứu, nhưng chúng không còn là nguồn dựng hiện hành.

Cập nhật README và tài liệu thế giới ngất để không tham chiếu nguồn đã xóa; bỏ tọa độ hồi phục gắn với mặt bằng cũ, dùng marker đặt trên map mới sau khi kiến trúc được chốt. Các mã vùng R trong gameplay là mã chức năng; việc ánh xạ sang kiến trúc mới chưa hoàn tất.

Flow, nội dung clues, preview, các cơ chế event và ending chính được giữ làm nguồn thiết kế gameplay cho giai đoạn sau. Các tài liệu này không quyết định hình bao hay tọa độ kiến trúc mới.
