# Thế giới khi ngất và quy tắc thông tin cho người chơi

> Tài liệu gameplay cho giai đoạn sau. Các mã R dưới đây là vùng chức năng, không quyết định mặt bằng hoặc tọa độ nhà. Khi build kiến trúc, dùng [file 06](06_cach_build_bao_tang.md) và ZIP hình học. Việc ánh xạ item/event sang vị trí thật thực hiện sau khi chốt kiến trúc; hiện chỉ dựng kiến trúc thô.

Cập nhật thiết kế ngày 12 tháng 10 năm 2026. File này bổ sung nhánh E06 của bản hiện tại và phân biệt mô tả preview với nội dung manh mối. Kiến trúc nhà dùng ZIP và kế hoạch Blender mới; nguồn thông tin vẫn theo file 02. Scene truy đuổi là công việc gameplay về sau, không thuộc giai đoạn kiến trúc thô hiện tại.

## Block 01 Chốt vị trí trong mạch truyện

Lồng thế giới mới vào đúng nhánh E06: người chơi chủ động quay lại khi chuông còn cảnh báo, gặp chuỗi sét/choáng hoặc gậy, ngã và tối màn hình. Thay phần tỉnh ngay sau blackout bằng một đoạn chạy trong không gian khác. Làm theo lời nhắc và quay về an toàn ở cuối nhánh vẫn bỏ qua toàn bộ đoạn này. Không dùng nó cho mọi lần ngất, không đặt sau O05 hoặc ở lối thoát cuối.

Chuỗi đầy đủ: E06 quay đầu → bị đánh/choáng → blackout → WORLD-NGAT-01 → tránh chướng ngại và thoát truy đuổi → cổng sáng → mở mắt tại R01 → đốm sáng trước mặt tắt → suy nghĩ “CÓ VẺ KHÔNG PHẢI MƠ...” → tiếp tục điều tra. Dòng suy nghĩ thể hiện cảm giác của nhân vật, không khẳng định nguyên nhân siêu nhiên là sự thật.

Không gian mới là một scene 3D được dựng riêng bằng shape. Nó không được tạo từ ảnh 2D và không thuộc tầng ba của ngôi nhà. Không có nguồn bắt buộc, item nhặt, tiền xu, nâng cấp hoặc kết thúc riêng ở đó. Balo và trạng thái bảo tàng giữ nguyên. Chỉ một lần xuất hiện trong một lượt chơi.

Vẫn có sáu cụm sự kiện lớn và 12 sự kiện nhỏ: đoạn chạy là phần của cụm E05/E06, không đếm thành cụm thứ bảy. Quyền điều phối E06 giữ từ lúc cảnh báo tới khi tỉnh hoàn toàn; không chạy chim/vật rơi/giọng ghế trong lúc người chơi đang ở thế giới mới.

## Block 02 Hình dáng thế giới và placeholder

Scene `DreamRunDraft`, ID thế giới `WORLD-NGAT-01`. Một đường thẳng dài 300 m, ba làn, trong nền tối với những khung trưng bày phóng đại và các mảng màu quen của bảo tàng. Khung tranh trở thành vòm, đế tượng thành khối cản; lá/chén/chuông chỉ xuất hiện dưới dạng họa tiết không chứa mã. Sự quen thuộc gợi rằng trải nghiệm có liên hệ với bảo tàng. Không sao chép map hoặc mỹ thuật của game chạy tàu.

Tọa độ riêng `(x,s,y)`: x trái/phải, s tiến về trước, y độ cao. Có thể ánh xạ X=x, Z=-s, Y=y. Ba tâm làn x=-1,6 / 0 / +1,6. Mặt đường rộng 6 m, từ -3 tới +3; có viền nhìn thấy hai bên, không hố sàn. Sàn liên tục từ s=0 tới 304; chỉ trigger cổng tại s=300 kết thúc đoạn chạy. Camera góc thứ nhất, không cần model nhân vật chạy.

| ID nhóm | Shape và bố trí | Nội dung/tương tác |
| --- | --- | --- |
| NG-FLOOR-T0/C1/R1/C2/R2/C3/GATE | Bảy box sàn theo các khoảng trong Block 04, dày 0,2 m; nối khít | Không item, không Xem giữa lúc chạy |
| NG-RAIL-L/R | Hai strip ở x=-2,9/+2,9, cao 0,4 m, dọc toàn đường | Giới hạn làn; không cho chạy khỏi sàn |
| NG-ARCH-01 đến 06 | Sáu khung box ở s=36,84,132,180,228,276; rộng trong 5,6 m, cao 3,8 m | Khung trang trí, không bịt đường hoặc tạo mã |
| NG-DECOR-01 đến 06 | Sáu plane màu, đặt ngoài viền ở s=48,96,144,192,240,288; luân phiên hai phía | Mảng màu/ảnh trừu tượng, không chữ hoặc manh mối mới |
| NG-CHASER | Một capsule tối cao 2,2 m, bán kính 0,35; ở sau người chơi | Bám tiến độ chạy, không điều hướng trong bảo tàng |
| NG-PORTAL | Khung hai trụ và thanh trên tại s=300, rộng trong 5,6 m, cao 3,2 m; plane sáng bên trong | Đi qua từ bất kỳ làn nào để trở lại thực tại |
| FX-E06-WISP | Sphere đường kính 0,08 m trong vùng liên thông R01, đặt theo marker E06_WISP trên map mới | Chỉ hiện lúc tỉnh sau đoạn chạy; không nhặt, không nguồn |

NG-CHASER dùng capsule/khối bóng trong bản đầu, không cần khuôn mặt, rig đánh hay AI tìm đường. Vật cản là box/cylinder theo ba loại ở Block 03. Không thêm đồ tương tác hoặc mở balo để đọc trong lúc chạy. Khung, portal và nền dùng vật liệu màu/self-lit cơ bản ở draft; âm thanh và chiếu sáng trình diễn triển khai sau theo file 04.

## Block 03 Điều khiển và va chạm

Người chơi tự tiến với tốc độ thử 5 m/s. A/D hoặc trái/phải đổi từng làn, một lần chuyển 0,22 giây; Space nhảy; Ctrl hoặc phím xuống trượt; Esc mở menu và dừng toàn bộ tiến độ/đuổi. Trước khi bắt đầu hiện hướng dẫn ngắn bằng biểu tượng và chữ tiếng Việt. Không yêu cầu kinh nghiệm chạy ba làn để biết phím.

Nhảy khoảng 0,75 giây, chân đạt cao 1,0 m ở đỉnh; trượt khoảng 0,70 giây, thân cao 0,8 m. Tốc độ/độ cao là thông số thử cần kiểm trong engine. Va chạm luôn dùng thân ở tư thế hiện tại, không dùng capsule đứng trong khi hình đã trượt. Không cho xếp chồng nhảy và trượt; nhấn thao tác không hợp lệ có phản hồi nhẹ, không tạo chuỗi input treo.

| Mã loại | Shape vật cản | Cách vượt |
| --- | --- | --- |
| H | Box rộng 1,20, sâu theo s 0,70, cao 1,80, từ mặt sàn | Đổi làn; không nhảy qua hoặc trượt xuyên |
| J | Box rộng 1,20, sâu 0,70, cao 0,50, từ mặt sàn | Nhảy hoặc đổi làn |
| S | Thanh ngang rộng 1,20, sâu 0,70; đáy ở y=1,05, đỉnh y=2,00 | Trượt hoặc đổi làn; không nhảy xuyên |

Mỗi lần va chạm giảm khoảng cách truy đuổi 6 m và làm chậm xuống 2 m/s trong 2 giây. Một vật chỉ gây phạt một lần; có khoảng miễn nhận va chạm 1 giây để không phạt lại mỗi frame. Sau lần va, cho đi qua vật đã xử lý bằng trạng thái riêng, không để auto-run đứng kẹt vĩnh viễn trước box. Menu/tải không tính thêm va chạm.

Khoảng cách ban đầu 14 m, tối đa 18 m, tăng lại 0,4 m/s khi chạy sạch. NG-CHASER ở s_player-gap, cùng tuyến; vị trí x chuyển chậm theo làn player. Đây là một mô hình tiến độ truy đuổi, không AI vượt mọi vật cản. Nếu gap≤2 m thì bị bắt: fade ngắn, tải checkpoint của đoạn chạy. Không chết trong bảo tàng, không mất đồ, không bắt đầu lại game.

Các hàng vật cản cách nhau ít nhất 12 m, có ít nhất một làn trống ở mỗi hàng. Đổi hai làn mất 0,44 giây; ở 5 m/s chỉ đi 2,2 m, nhỏ hơn khoảng hàng 12 m. Không đặt chướng ngại ngay sau một checkpoint hoặc sát plane cổng. Không dùng random chưa kiểm khả năng vượt.

## Block 04 Trình tự đường chạy xác định

| Đoạn | Khoảng s | Cách thể hiện | Checkpoint |
| --- | --- | --- | --- |
| T0 Làm quen | 0–36 | 12 m đầu yên, hướng dẫn; một vật J tại 18 giữa và một S tại 30 giữa, các làn bên trống | 0 |
| C1 Bắt đầu bị đuổi | 36–96 | Bóng/nhịp đuổi xuất hiện phía sau; các vòm đầu | 0, T0 không reset hướng dẫn đã đọc |
| R1 Khoảng thở | 96–120 | Không vật cản, nền bớt dồn | Qua 120 lưu checkpoint 120 |
| C2 Dồn nhịp | 120–198 | Thay làn và tư thế, các mảng màu quen nổi hơn | 120 |
| R2 Khoảng thở | 198–228 | Không vật cản; cổng bắt đầu thấy ở xa | Qua 228 lưu checkpoint 228 |
| C3 Cao điểm cuối | 228–270 | Ba hàng cuối, không thêm vật cản bất ngờ ngoài bảng | 228 |
| GATE Thoát | 270–304 | Không vật cản; cổng ở 300, mọi làn đều qua được | Không checkpoint sau cổng |

| s của hàng | Trái | Giữa | Phải |
| --- | --- | --- | --- |
| 18 | Trống | J | Trống |
| 30 | Trống | S | Trống |
| 48 | H | Trống | H |
| 60 | Trống | J | Trống |
| 72 | H | S | Trống |
| 84 | H | H | Trống |
| 132 | Trống | H | H |
| 144 | S | Trống | J |
| 156 | H | H | Trống |
| 168 | Trống | Trống | J |
| 180 | H | Trống | H |
| 192 | Trống | H | Trống |
| 240 | H | H | Trống |
| 252 | J | Trống | S |
| 264 | H | Trống | H |

Tổng 25 vật cản riêng, ID `NG-OBS-{s}-{L/C/R}` cho các ô không Trống. Bản dựng dùng đúng bảng này, không tạo cả ba loại trong cùng một ô. Khu T0 va lần đầu chỉ nhắc thao tác và giảm tốc ngắn, không giảm gap; lượt sau vẫn cho chạy tiếp. Hai hành động nhảy/trượt có thể luyện, nhưng chọn làn trống vẫn là đường hoàn thành hợp lệ.

Một lượt sạch mất khoảng 60 giây chạy, cộng chuyển cảnh và tỉnh khoảng 10–15 giây. Đây là dự kiến, không thời lượng đã đo. Lần bị bắt đưa về checkpoint gần nhất; sau hai lần bị bắt, menu đưa lựa chọn Tiếp tục thử hoặc Đi tới cổng. Đi tới cổng đưa tới s=270 với gap=18 rồi vẫn đi qua portal để xem đoạn tỉnh. Nút Bỏ đoạn truy đuổi luôn có trong menu hỗ trợ; không giữ kết thúc chính sau một thử thách vận động.

## Block 05 Trở lại thực tại và đốm sáng

Qua s=300 khi ở trong khung NG-PORTAL: vô hiệu input chạy/va chạm, dừng chaser, fade theo plane sáng trong khoảng 0,6–1,0 giây. Không tăng sáng toàn màn hình nhiều lần. Ghi DREAM_PORTAL_CROSSED rồi chuyển scene về bảo tàng tại marker E06_WAKE_SAFE trong vùng liên thông R01 của tầng hai. Vị trí và hướng nhìn được đặt sau khi chốt kiến trúc mới; dùng cao độ tầng hai 3,65 m và kiểm tra đường đi. Không spawn về giường hay về vị trí cú đánh nguy hiểm.

Mở mắt bằng một lớp che mí/giảm mờ khoảng 0,8 giây; ưu tiên góc nhìn phía trước trong nhịp này. FX-E06-WISP hiện tại marker E06_WISP phía trước hướng nhìn từ E06_WAKE_SAFE, cao khoảng 1,35 m trên sàn và cùng tông trắng ngà/ấm của cổng. Hai marker phải được kiểm tra góc nhìn và va chạm trên map mới; tọa độ cụ thể chưa chốt. Nó là vật hiển thị thật trong scene bảo tàng, không chỉ hình trong giấc mơ. Giữ hiện khoảng 0,8–1,0 giây sau khi mắt mở, rồi co/fade về 0 trong khoảng 0,4–0,6 giây. Collider tắt; không vật phẩm bên dưới, không cửa hay texture bằng chứng bị đổi.

Nếu player đã thấy đốm sáng trong nhịp tỉnh, khi nó tắt hiện dòng suy nghĩ đúng “CÓ VẺ KHÔNG PHẢI MƠ...” trong khoảng 2 giây. Mỗi lần chỉ một câu. Nếu bỏ toàn bộ cảnh tỉnh hoặc không thấy đốm, không khẳng định bằng dòng này; vẫn tiếp tục bình thường. Không ép quay camera tìm đốm sau khi đã trả điều khiển. Không yêu cầu chụp đúng đốm để ghi nhận.

Trả L01 chuẩn, giảm ù tai nhanh, bảo tàng trở lại nhịp yên. Balo mở được ngay. Đặt E06_DONE sau khi đã trở lại vị trí an toàn; cấm lặp nhánh đánh ngất và truy đuổi. Khoảng nghỉ trước cao trào tiếp theo tính từ lúc phục hồi, không tính 60 giây chạy là một khoảng nghỉ. Đốm là dấu vết trải nghiệm bổ sung, không nguồn thứ 20 và không mở key/giường.

## Block 06 Lưu tải và trường hợp biên

| Giai đoạn | Lưu tối thiểu | Khi tải |
| --- | --- | --- |
| Trước cú đánh | Trạng thái bảo tàng, vị trí hồi phục an toàn, biến thể A/B, E06 phase | Hoàn tất blackout rồi vào NG nếu đã commit, không đánh lại |
| Đang chạy | Museum session được giữ; checkpoint NG, phase, số lần bị bắt, trạng thái hỗ trợ | Vào checkpoint NG, làn giữa, gap=18, đứng đất; không spawn đang trượt trong vật cản |
| Đã qua portal | DREAM_PORTAL_CROSSED, WAKE_PENDING | Tới R01 an toàn, không chạy lại NG |
| Đang tỉnh | WISP_SEEN, WISP_DONE, E06 phase | Hoàn tất tỉnh ổn định, không lặp dòng/cú tắt nếu đã chạy |
| Đã phục hồi | E06_DONE, WISP_DONE | Bảo tàng bình thường, không ngất lại |

Trong NG, không tiến event khác, không mở balo, không chụp Camera, không thay inventory/nguồn/ngăn/kết luận của bảo tàng. Thời gian album vẫn là thời gian lượt chơi; không dùng nó làm puzzle. Pause dừng auto-forward, chaser và timer tư thế. Resume kiểm lại input, không tự nhảy vì phím còn giữ từ lúc mở menu.

Bỏ đoạn NG đi qua nhánh an toàn s=270 hoặc chuyển tỉnh nếu chọn Bỏ toàn bộ cảnh; cả hai giữ đồ và kết thúc. Nếu setting tắt cảnh truy đuổi từ đầu, E06 vẫn có nhánh choáng/tỉnh nhưng không tạo thử thách bắt buộc. Không gọi NG từ E08 cửa niêm phong. O05 đã có thì E06 không được khởi động; nguồn trong nhà không phụ thuộc NG_DONE.

## Block 07 Preview khác với manh mối

Có năm lớp dữ liệu riêng. Không lấy cả đoạn mô tả thiết kế để hiển thị cho người chơi.

| Trường | Dùng ở đâu | Quy tắc |
| --- | --- | --- |
| display_name | Tên khi ngắm/click, tên balo | Tên khách quan, không lộ kết luận; I10 là Biên bản bàn giao, không Biên bản đã sửa |
| preview_text | Mô tả ngắn khi click Xem | Một hoặc hai câu về thứ đang thấy: chất liệu, kiểu vật, tình trạng; không tự giải nguồn |
| asset_text / asset_visual_spec / pages | Chữ, hình và các mặt/trang của item thật | Nội dung súc tích của file 02; có thể bí ẩn/kinh dị theo tác giả in-world, nhưng dữ kiện phải đủ suy luận |
| hint_text / notebook_observation | Nút gợi ý chủ động, ghi nhận quan sát/đối chiếu | Nêu dữ kiện đã thấy; chỉ giải thích quan hệ sau hành động kiểm chứng; không tự kết luận qua preview |
| narration_text | Suy nghĩ/thoại trong event | Có thể chủ quan, bất an; dòng Không phải mơ chỉ thuộc sự kiện tỉnh, không phải preview một sphere |

Ví dụ I09: preview “Phiếu bảo dưỡng có ghi chú về hai máy ảnh.”; mặt giấy ghi máy A nhanh 7 phút, B chậm 5 phút; người chơi tự hiệu chỉnh. Ví dụ D01: preview “Một chiếc chén men xanh đặt trên đế cố định.”; khi xoay mới thấy tam giác, R08 và tem trăng; sổ ghi điều đã thấy. Không cho preview nói “Chén là bản sao, dùng số 3.”

Ngôn ngữ chung dùng tiếng Việt rõ, trung lập, hơi bí ẩn ở chi tiết quan sát. Có thể nói “Khung cũ có vài vết xước.”; không nói “Bức tranh đang che giấu đáp án.” Không thay chữ trên giấy bằng một câu kể dài về lịch sử bảo tàng. Không dùng câu chắc chắn mà nhân vật chưa có căn cứ biết.

Dùng bảng dưới và danh mục file 02 làm lời preview; dùng nội dung nguồn tại file 02 để dựng chữ và hình thực tế. Ghi chú kỹ thuật, mã và điều kiện không phải lời preview để copy thẳng. Lời giải ở file 01/05 chỉ là dữ liệu thiết kế, không in trên item nếu không được quy định.

### Preview cho toàn bộ nguồn đã đặt

| ID | display_name | preview_text |
| --- | --- | --- |
| F01 | Ảnh lưu trữ gia đình | Một ảnh màu chụp bức tranh gia đình cùng khung gỗ. |
| F02 | Ảnh bàn kiểm tra | Một bức ảnh chụp bàn làm việc và ba hiện vật. |
| F03 | Ảnh bàn giao | Bức ảnh chụp một thùng gỗ đang mở trong kho. |
| F04 | Bản chụp sơ đồ kỹ thuật | Một bản chụp nét vẽ kỹ thuật, có chú thích và đường nối. |
| F05 | Ảnh ngày mở cửa | Nhóm nhân viên đứng trước sảnh bảo tàng. |
| F06 | Ảnh phòng trực | Bức ảnh chụp một căn phòng khi còn được sử dụng. |
| F07 | Ảnh gian kiểm định | Bức ảnh có viền giấy cũ, chụp khu kiểm định trong bảo tàng. |
| F08 | Bộ ảnh kiểm định | Sáu bức ảnh nhỏ được gắn trên cùng một tấm giấy. |
| I00 | Tờ hướng dẫn | Một tờ giấy đặt riêng trên bàn. |
| I01 | Phiếu kiểm tra tranh | Phiếu in nhỏ với một đường gấp ngang. |
| I02 | Phiếu trả từ xưởng | Một phiếu giấy có lỗ dập ở góc. |
| I03 | Sổ kiểm kê | Một tập giấy gập có hai trang nội dung. |
| I04 | Phiếu bảo trì | Một phiếu in chia thành hai phần. |
| I05 | Lời nhắn viết tay | Một mẩu giấy có chữ viết tay và tên ở cuối. |
| I06 | Phiếu bảo dưỡng đèn | Phiếu giấy xanh nhạt đã cũ ở mép. |
| I07 | Phiếu vệ sinh trưng bày | Một tờ hướng dẫn công việc trong gian trưng bày. |
| I08 | Phiếu sửa khóa | Phiếu giấy xám kem có chữ ở cả hai mặt. |
| I09 | Phiếu bảo dưỡng máy ảnh | Phiếu bảo dưỡng có ghi chú về hai máy ảnh. |
| I10 | Biên bản bàn giao | Một biên bản có chữ ký ở cuối trang. |
| I11 | Nhật ký báo động | Một tờ nhật ký ghi thời điểm của một sự việc. |
| I12 | Phiếu vận chuyển | Một phiếu giấy còn dấu xác nhận rõ. |
| W01 | Gia đình bên cửa sổ | Bức tranh gia đình trong khung gỗ sơn xanh ngọc. |
| W02 | Bảng hướng dẫn đối chiếu | Một bảng giấy được kẹp bằng hai thanh gỗ mảnh. |
| W03 | Bảng lưu hồ sơ | Bảng có các hàng, cột và nhãn chữ số. |
| W04 | Ảnh cầu thang cũ | Bức ảnh đen trắng trong khung gỗ nâu. |
| W05 | Tờ nhắn trên tường | Một tờ giấy ghim lên tường, mép dưới bị xé. |
| W06 | Nắng trong sân | Bức tranh tạo bởi các mảng màu trong khung gỗ mỏng. |
| W07 | Quy trình trên cửa | Một bảng men chữ đen gắn vào mặt trong cánh cửa. |
| W08 | Bảng dấu kiểm định | Bảng giấy trong khung gỗ xám, có hình và hai cột năm. |
| D01 | Chén men xanh | Một chiếc chén men xanh đặt trên đế cố định. |
| D02 | Lá đồng | Một vật hình lá, có cuống dài và bề mặt màu đồng xanh. |
| D03 | Chuông nhỏ | Một chiếc chuông đồng có tay cầm dạng vòng. |
| D04 | Mặt nạ gỗ | Mặt nạ sơn kem đỏ đặt trên một bệ riêng. |
| O01 | Dấu Hiện vật | Một con dấu đồng nhỏ, có chữ trên mặt. |
| O02 | Dấu Đường đi | Một con dấu đồng với biểu tượng đường rẽ. |
| O03 | Dấu Tầng | Một con dấu đồng có hình bậc. |
| O04 | Máy ảnh | Máy ảnh nhỏ với dây đeo xám và màn hình ở mặt sau. |
| O05 | Chìa khóa | Chìa khóa đồng đầu vòng, có rãnh ở cổ và ba răng. |
| N01 | Nét bút chì | Vài nét bút chì ngắn nằm cạnh khu treo tranh. |
| N02 | Vết nước | Vết ố cũ chạy thành nhánh trên tường. |
| N03 | Nhãn trên ống | Một nhãn nhỏ gắn trên đường ống kim loại. |

Preview không bỏ khả năng người chơi tự thấy chữ trên asset: nhãn R08 nằm đúng trên đáy khi xoay; năm trên ảnh vẫn hiện trên viền. Tách preview chỉ ngăn hệ thống tự diễn giải hoặc đưa lời giải trước khi người chơi quan sát. Khi Xem nguồn phải mở cả mặt hình/giấy, không chỉ hiện một câu preview rồi giấu nguồn.

Các prop chưa thuộc danh mục nguồn phải có preview khách quan khi được thiết kế lại trên map mới. Các ví dụ ngôn ngữ có thể giữ: “Một hộp kim loại có ba hàng nhãn.”; “Bốn vòng số và một tay gạt.”; “Khay nhỏ bên khung cửa.”; “Một hốc trưng bày có kính.”; “Máy đọc thẻ kiểm kê có màn hình và nút điều khiển.” Vị trí prop được chốt ở giai đoạn ánh xạ gameplay. Không hiện “môđun dự trữ”, “nguồn thứ 19”, “đáp án 3581”, “prototype” hoặc tên engine trong UI người chơi. Các câu này chỉ thuộc ghi chú developer.

## Block 08 Giao AI xây và kiểm tra

Kiến trúc nhà dùng ZIP và kế hoạch Blender mới. Items lấy nội dung từ file 02; vị trí cụ thể chưa ánh xạ sang map mới. Toàn bộ lời preview dùng Block 07 file này. Scene NG làm sau khi đường chính và balo chạy được, ở giai đoạn gameplay về sau. Các shape của NG đặt cố định theo bảng; chưa cần asset nhân vật, âm hoặc shader cầu kỳ. Không dùng bộ luật auto-run cho người chơi trong bảo tàng; controller của hai scene là hai chế độ tách nhau và khi tỉnh phải trả chế độ đi lại.

| Kiểm | Kết quả bắt buộc |
| --- | --- |
| Làm theo W05 | Quay về bình thường, không vào NG |
| E06 biến thể A hoặc B | Cùng vào NG, chỉ khác cách bị choáng trước đó |
| Trước và sau NG | Inventory, 19 nguồn, ngăn, đĩa, hồ sơ và key của bảo tàng không đổi |
| Hàng vật cản | Có làn trống, đúng ID/loại, không random bất khả thi |
| Va một vật nhiều frame | Chỉ phạt một lần, không đứng kẹt |
| Trượt/nhảy/đổi làn | Collider đúng tư thế; không xuyên vật khác chưa xử lý |
| Pause giữa chạy | s/gap/timer giữ nguyên |
| Bị bắt/tải giữa chạy | Checkpoint NG an toàn, không replay cú đánh, không mất đồ |
| Bỏ thử thách | Vẫn trở về thực tại, không khóa kết thúc |
| Qua portal ở làn trái/giữa/phải | Cùng trở về R01 đúng điểm |
| Đốm sáng và câu suy nghĩ | Đốm hiện thật ở R01 rồi tắt, câu chỉ khi đã nhìn thấy |
| Có O05 | Không khởi động E06/NG mới |
| Click I10/D01/F07 | Preview khách quan, không tự nói đã sửa/bản sao/chọn năm nào |
| Mở mặt giấy, ảnh hoặc xoay đáy | Chữ/hình/tem đúng nguồn; đủ dữ kiện để suy luận |
| Đóng preview/mở balo | Nội dung không đổi, không cộng nguồn bằng việc đọc lời preview |

Đây là đặc tả xây bản cơ bản, chưa phải kết quả test trong engine. Khi bắt đầu làm âm thanh và ánh sáng, dùng bổ sung A25–A29/L06–L08 ở file 04; không tăng nháy đèn để kéo dài đoạn chạy hoặc che lỗi hình học.
