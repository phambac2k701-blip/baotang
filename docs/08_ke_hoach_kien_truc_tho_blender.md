# Hoàn thiện kiến trúc thô bảo tàng trong Blender — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task if that skill is installed. If unavailable, follow the tasks natively with Blender MCP/Python; no extra agent or plugin is required. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Hoàn thiện một mô hình kiến trúc thô duy nhất, có đầy đủ vỏ ngoài và không gian bên trong, để người dùng duyệt trước khi làm vật liệu.

**Architecture:** Dựng bằng Blender Python từ dữ liệu hình học; dùng Blender MCP để thực thi, xem scene và kiểm tra các góc nhìn. Phiên 2 tiếp tục cùng hệ tọa độ và cùng mô hình của phiên 1. Dữ liệu phần nội thất phải được lưu riêng, không thay hình bao đã duyệt bằng cách đoán từ ảnh.

**Tech Stack:** Blender, Python `bpy`, Blender MCP. Chưa dùng Meshy, imagegen để dựng hình, texture hoặc Godot trong phạm vi bàn giao này.

**Spec:** `geometry.json`, `README.md`, `01_mat_bang_kich_thuoc.png`, `02_khung_nhieu_goc.png`, `03_cao_do_va_phong.png` trong `khung_bao_tang_v1.zip`. Đây là spec hình bao sơ bộ; Task 3 bổ sung thiết kế kiến trúc bên trong còn thiếu.

## Global Constraints

- Hình bao ba thùy lệch đã được duyệt. Giữ tọa độ vỏ và giếng trời trong `geometry.json`.
- Hai tầng: cao độ sàn 0 và 3,65 m; thông thủy 3,40 m; sàn/mái dày 0,25 m; đỉnh mái 7,30 m.
- Diện tích 263,924 m² là tổng diện tích bao sàn hai tầng, gồm vùng tường/thang, trừ giếng trời; không phải diện tích dùng được sau khi đặt đồ.
- Vỏ dày 0,20 m; vách phụ dày 0,12 m. Bề dày phải tồn tại trong hình học.
- Không gian trưng bày là dải rộng liên tục quanh giếng trời; không tự chia thành một chuỗi phòng nhà ở.
- Giếng trời có tường bao kín với không gian trưng bày; không tạo ban công nhìn xuống tầng dưới, giữ logic khám phá tầng 2.
- Sàn tầng 2 có ô xuống bí mật H trong P0; thang công cộng vẫn tồn tại về kiến trúc nhưng cần hình học chặn trong trạng thái gameplay.
- Chỉ dùng vật liệu trắng mặc định và ánh sáng làm việc trung tính để xem hình khối. Không tạo texture, PBR, props, tranh, đồ nội thất, hiện vật hoặc môi trường kinh dị.
- Chưa thay đổi gameplay, chưa nhập model vào Godot, chưa xóa scene cũ. Giữ bản cũ và dựng thành phiên bản kiến trúc riêng.
- Các ảnh gen là tham chiếu hình khối. Bản vẽ và tọa độ ưu tiên cao hơn ảnh gen khi có khác biệt.

## Review Focus

1. Cảnh nhìn đẹp từ trên cao nhưng các gian bên trong chưa được thiết kế: Task 3–4 phải có mặt đứng nội thất và các camera ngang mắt.
2. Hai phiên dựng hai mô hình lệch nhau: Task 1–2 phải ghi nguồn dữ liệu, đơn vị và mô hình gốc; Task 4 chỉ tiếp tục phiên 1.
3. Tường/sàn chồng, lỗ giả, mặt đảo hoặc đường cong gãy: Task 2 và 5 kiểm tra hình học với chế độ solid và mặt cắt.
4. Thang, cửa, khu phụ không đủ khoảng đứng/di chuyển: Task 3 và 5 kiểm tra bằng khối người tham chiếu, không chỉ ảnh render.
5. Thang/giếng trời làm lộ tầng dưới hoặc thành lối thoát sớm: Task 4 phải có hình học chặn thang và đường xuống bí mật tách riêng.

## Cấu trúc bàn giao

Tạo một thư mục mới `museum_architecture/` trong workspace của người thực hiện. Không yêu cầu cấu trúc repo game cụ thể.

| File | Vai trò |
|---|---|
| `source/geometry.json` | Bản nguồn hình bao giữ nguyên |
| `source/README.md` | Bản nguồn mô tả |
| `design/interior_spec.json` | Các vùng, mặt đứng, cột/vòm, thang, đường nối đã thiết kế |
| `design/interior_review.md` | Giải thích bố cục và các điều chỉnh so với khung sơ bộ |
| `scripts/build_shell.py` | Tái dựng vỏ từ nguồn; chạy lại không nhân đôi object |
| `scripts/build_interior.py` | Tái dựng kiến trúc bên trong theo `interior_spec.json` |
| `museum_shell_v1.blend` | Mốc kết thúc phiên 1 |
| `museum_architecture_v2.blend` | Mô hình cuối có kiến trúc bên trong |
| `views/` | Ảnh kiểm tra, mặt bằng, mặt đứng và mặt cắt |
| `handoff.md` | Kết quả thực hiện và vấn đề còn lại |

Collection Blender: `ARCH_SHELL`, `ARCH_FLOORS`, `ARCH_INTERIOR`, `ARCH_STAIRS`, `ARCH_SECRET_ROUTE`, `REVIEW_CAMERAS`, `REVIEW_SCALE`. Camera và khối người kiểm tra không thuộc model kiến trúc xuất cuối.

## Phiên 1 — Khung toàn bộ nhà

### Task 1: Nạp nguồn và lập scene

**Consumes:** ZIP kiến trúc V1 và dự án Blender của người dùng nếu có.

**Produces:** thư mục bàn giao, bản sao nguồn, scene dùng đơn vị mét và báo cáo nguồn.

- [ ] Giải nén ZIP, đọc các file spec, kiểm tra Blender MCP có thể đọc scene và chạy Python.
- [ ] Lưu bản mô hình cũ nếu có. Không sửa/xóa các collection ngoài phạm vi kiến trúc mới.
- [ ] Thiết lập hệ tọa độ: x/y theo JSON, z là cao độ; bắc là +y. Một Blender unit bằng một mét.
- [ ] Ghi kết quả trong `handoff.md`: nguồn nào đã đọc, Blender version, các file tạo ra.

### Task 2: Dựng toàn bộ khung từ dữ liệu

**Consumes:** `source/geometry.json`.

**Produces:** `scripts/build_shell.py`, `museum_shell_v1.blend`, ảnh kiểm tra phiên 1.

- [ ] Dựng đường cong từ công thức hoặc các điểm có sẵn. Không đo kích thước bằng mắt từ concept.
- [ ] Dựng tường vỏ có bề dày, sàn hai tầng, mái và giếng trời; các tấm không xuyên qua giếng trời.
- [ ] Dựng ô cửa, cửa sổ đúng vị trí và kích thước. Không dùng texture hoặc mặt đen thay một lỗ thật.
- [ ] Đánh dấu bốn vùng P0/P1/P2/P3, thang S1, ô H và đường đi trong scene. Đây là khung nội thất sơ bộ để phiên 2 nối tiếp.
- [ ] Đặt tên object ổn định. Script chỉ tạo/xóa object do chính nó quản lý khi chạy lại.
- [ ] Đo hình bao, cao độ, số ô mở; so với JSON. Báo cáo chênh lệch đo thay vì tuyên bố "giống 95%".
- [ ] Xuất mặt bằng hai tầng và bốn camera ngoài cố định. Lưu file `.blend` và script.

**Điều kiện xong phiên 1:** khung hai tầng dựng được và có nguồn tái tạo, chưa được gọi là nội thất hoàn chỉnh.

## Phiên 2 — Thiết kế và dựng toàn bộ kiến trúc bên trong

### Task 3: Bổ sung spec nội thất trước khi dựng chi tiết

**Consumes:** file `.blend` phiên 1, khung P0/P1/P2/P3 và dữ liệu nguồn.

**Produces:** `design/interior_spec.json`, `design/interior_review.md`, mặt bằng nội thất chi tiết.

- [ ] Định nghĩa ba vùng công cộng: vùng trưng bày chính tại thùy phía nam, vùng tranh tại thùy phía tây, vùng nối/quan sát phía trong khu phụ. Phòng câu đố P3 thuộc thùy phía đông và không cắt đứt tuyến đi công cộng.
- [ ] Làm rõ sự chuyển tiếp giữa các vùng bằng hình khối kiến trúc: khung vòm rộng, cột áp tường hoặc một đoạn vách cong ngắn. Không dùng hàng vách kín để chia nhỏ sảnh.
- [ ] Đề xuất tối đa hai khung vòm đánh dấu gian công cộng. Chọn vị trí sau khi kiểm tra thang, tuyến đi và ô mở; lưu tọa độ, hướng, bề rộng và mặt cắt chính xác trong spec. Không coi vị trí vòm là đã có trong bản V1.
- [ ] Xác định từng mặt tường, trần, chân tường, ô cửa: hình học, kích thước, cách nối góc. Chỉ tạo hình thô; chưa chọn màu/vật liệu. Có thể thêm bệ kiến trúc hoặc hốc tường nếu không cản đường đi.
- [ ] Với tường cong dành cho tranh, bố trí những đoạn/hốc có mặt trưng bày đủ phẳng; không mặc định tất cả tranh phải uốn theo tường.
- [ ] Kiểm tra từng phòng phụ: P0 khoảng 8,44 m², P1 khoảng 4,75 m², P2 khoảng 5,66 m², P3 khoảng 20,54 m², trước khi trừ vách. P1/P2 là các không gian rất nhỏ; không mô tả chúng như kho hoặc xưởng lớn.
- [ ] Dùng các hộp kiểm tra tạm cho một người, một bàn và một tủ để chứng minh phòng có thể dùng. Hộp chỉ nằm trong `REVIEW_SCALE`, không trở thành đồ nội thất bàn giao.
- [ ] Nếu không thể sử dụng P1/P2 với kích thước hiện tại, lập phương án điều chỉnh vách nội bộ kèm diện tích và ảnh. Giữ hình bao, giếng trời, cao độ; ghi rõ mọi thay đổi. Chưa gọi thiết kế là hoàn chỉnh nếu còn vấn đề này.
- [ ] Định nghĩa thang công cộng và thang đứng bí mật bằng kích thước thực; kiểm tra lỗ sàn, khoảng đứng và điểm lên/xuống. Vỏ thang bí mật xuống khu cửa hậu là phần cần bổ sung, không có sẵn trong hình vẽ V1.

Mỗi vùng trong `interior_spec.json` có tối thiểu: `id`, `floor`, `function`, `boundary`, `wall_faces`, `ceiling`, `openings`, `connections`, `architectural_elements`, `clearances`, `review_camera_ids`.

Mỗi phần tử kiến trúc có: `id`, `type`, `position_xyz`, `rotation`, `dimensions`, `profile`, `parent_zone`. Biên cong ghi bằng điểm hoặc công thức, không chỉ dùng mô tả "uốn đẹp".

### Task 4: Dựng chi tiết hình khối bên trong

**Consumes:** `interior_spec.json`, `museum_shell_v1.blend`.

**Produces:** `scripts/build_interior.py`, `museum_architecture_v2.blend`.

- [ ] Dựng vách, cột/vòm, hốc, khung ô mở, phần trần và chuyển tiếp sàn theo spec; không tự tạo một model mới độc lập với vỏ.
- [ ] Dựng vùng giao giữa vỏ cong và vách; không để góc thừa, mặt trùng hoặc khe nhìn xuyên.
- [ ] Hoàn thiện P0, P1, P2 và P3 với mặt đứng và trần thực, không chỉ có vách nhìn từ trên xuống.
- [ ] Dựng vị trí gắn cửa sập tại P3 như kiến trúc: khe/hộp phía trên cửa và ô mở. Chưa lập trình sự kiện.
- [ ] Dựng thang S1 cùng hình học chặn nó trong trạng thái gameplay; chặn phải thấy được, không dùng một collider vô hình ở giai đoạn thiết kế.
- [ ] Dựng ô H, thang đứng riêng, vỏ đường thoát tầng dưới và đường tới D1. Giữ cửa sàn đóng mặc định bằng tấm kiến trúc, chưa thêm giường.
- [ ] Các phần cơ khí về sau cần chuyển động như nắp H hoặc cửa sập phải là object tách, có vị trí trục hợp lý.
- [ ] Lưu mô hình và script; giữ checkpoint phiên 1.

### Task 5: Kiểm tra toàn bộ từ bên trong

**Consumes:** model kiến trúc V2.

**Produces:** bộ ảnh kiểm tra và `handoff.md` cập nhật.

- [ ] Kiểm tra normals, bề dày, giao sàn/tường và lỗ mở trong solid view, wireframe và mặt cắt.
- [ ] Dùng khối người/camera cao khoảng 1,65 m để kiểm tra đường đi. Kiểm tra bằng phép đo, không lấy chiều cao camera làm chứng minh duy nhất.
- [ ] Tuyến công cộng chính nên có khoảng trống khoảng 1,50 m trở lên sau khi dự trù kiến trúc; cửa phụ theo kích thước nguồn. Đây là mục tiêu bố cục game, không phải tuyên bố đạt quy chuẩn xây dựng.
- [ ] Kiểm tra không phải đi xuyên P3 để tới phần còn lại; giếng trời không cho góc nhìn xuống tầng dưới; ô H dẫn tới D1 mà không xuyên sàn/vách.
- [ ] Xuất ảnh mỗi vùng: một góc rộng ngang mắt, một góc ngược và các mặt đứng tường có ô mở hoặc hình khối đặc biệt. Có cả P0/P1/P2/P3 và khu lối thoát.
- [ ] Xuất mặt bằng hai tầng, mặt bằng trần, ít nhất hai mặt cắt qua các hướng khác nhau, một ảnh tháo mái và một ảnh tách tầng.
- [ ] Camera ngoài: trước, sau, hai bên và trên cao. Camera trong: ít nhất hai vị trí mỗi vùng chính. Lưu tên và transform camera trong scene để chụp lại cùng góc sau khi sửa.
- [ ] `handoff.md` phân biệt rõ phần đã dựng, đã đo, đã nhìn kiểm tra và phần còn vướng. Nếu không thực sự kiểm tra được một mục, ghi chưa kiểm tra.

**Điều kiện xong phiên 2:** người xem hiểu toàn bộ không gian từ ngoài vào trong và thấy các đường nối/thang/cửa; không còn phần nội thất chỉ được suy ra từ ảnh trên cao. Hoàn chỉnh ở phạm vi kiến trúc thô game, chưa phải thiết kế kỹ thuật thi công hoặc game đã chạy.

## Prompt mở phiên 1

```text
Đọc kế hoạch kiến trúc thô và khung_bao_tang_v1.zip. Thực hiện phiên 1
trong Blender bằng Python qua Blender MCP. Dựng từ geometry.json,
giữ hình bao đã duyệt, tạo file .blend và script tái dựng. Xuất các góc
kiểm tra và báo cáo kích thước. Không làm vật liệu, không gọi Meshy,
không sửa gameplay và chưa chuyển sang Godot. Bàn giao checkpoint
để phiên 2 tiếp tục chính mô hình này.
```

## Prompt mở phiên 2

```text
Mở checkpoint phiên 1 và đọc kế hoạch. Thực hiện Task 3–5: thiết kế
và dựng kiến trúc bên trong, không chỉ dựng lại vỏ nhà. Lưu spec
nội thất có tọa độ, kích thước và mặt cắt; hoàn thiện từng vùng,
cửa/vòm/trần/thang và đường thoát. Giữ khung gốc và ghi mọi thay đổi
vách nội bộ. Kiểm tra bằng mặt bằng, mặt đứng, mặt cắt và camera
ngang mắt; cung cấp file .blend, script, ảnh và báo cáo. Không vật
liệu, không props, không Meshy, chưa triển khai trong Godot.
```

## Sau phạm vi này

Chỉ khi người dùng duyệt kiến trúc thô mới lập công việc vật liệu. Godot và Meshy không cần tham gia để hoàn thiện hình học nội thất ở giai đoạn hiện tại.
