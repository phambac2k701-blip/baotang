# Âm thanh và ánh sáng trong bảo tàng

> Cập nhật kiến trúc 13/10/2026: các mã R dưới đây là vùng chức năng của gameplay, không quyết định mặt bằng hoặc tọa độ nhà. Nguồn dựng hiện hành là ZIP và [kế hoạch kiến trúc thô Blender](06_cach_build_bao_tang.md). Việc ánh xạ item/event sang map mới thực hiện sau khi chốt kiến trúc; hiện chỉ dựng kiến trúc thô, chưa triển khai gameplay.

Tài liệu âm thanh và ánh sáng · Thiết kế phiên bản 4 · 12 tháng 10 năm 2026

Âm thanh giúp nhận biết vật liệu, khoảng cách và thay đổi ở gian khác. Ánh sáng giữ bảo tàng tối và bất an nhưng cho phép đọc đủ thông tin. Hai hệ thống cùng theo trạng thái event, không tự tạo một chuỗi chớp hoặc tiếng giật độc lập làm mất nhịp suy luận.

## 1 Nền âm và thời tiết

Thời tiết ngoài bảo tàng là mưa giông từ đầu. Mưa nghe mờ qua tường, rõ hơn gần ô kính R01 và ở tuyến thoát cuối. Có tiếng sấm xa thưa ngay trong đoạn đầu yên tĩnh, nên sét ở E06 là một đợt giông mạnh hơn của cùng thời tiết, không là trời đột nhiên đổi chỉ vì người chơi quay đầu.

Mỗi gian có một nền riêng nhưng nhỏ. R00 nghe mưa xa, gỗ co và hơi phòng kín. R01 có gió ở khe kính và tiếng ống. R02 có phòng rộng hơn một chút, vải và khung gỗ. R03 gần tiếng kim loại nhẹ và kệ dụng cụ. R04 là giấy, ngăn kéo và ít tiếng thông gió. R05 có ống gió thấp. Không phủ một bản nhạc kinh dị liên tục lên mọi gian.

Đầu lượt chỉ dùng nền thời tiết và âm tương tác. Một lớp âm trầm rất nhẹ có thể xuất hiện sau khi chứng minh việc tráo hiện vật, rồi lùi xuống khi đọc F04. Đoạn nhận chìa khóa tạo khoảng thở trước đường về. R06 nghe môi trường ngoài trời rộng hơn và bỏ lớp âm trầm trong nhà.

## 2 Danh mục âm chính

| Mã | Âm và nguồn | Dùng ở đâu | Phản hồi hoặc thông tin |
| --- | --- | --- | --- |
| A01 | Mưa và sấm xa ngoài nhà | Toàn công trình, mạnh gần ô kính | Thời tiết được thiết lập từ đầu |
| A02 | Tiếng bước trên gỗ, đá, bụi | Theo bề mặt dưới chân | Cảm giác phòng và nhịp di chuyển |
| A03 | Gió và ống thông khí | R01 R05 | Nguồn cố định, nghe gần mạnh hơn |
| A04 | Chốt đúng và chốt không ăn | Các đĩa, ngăn, hộp | Phân biệt giải đúng với sai |
| A05 | Kim loại nhả chốt nhỏ | G36 R03 | Hoàn tất hồ sơ hiện vật |
| A06 | Kim loại chạm kệ, rơi, lăn ngắn | G14 G69 và sàn R03 | E02 hoặc nhịp hộp rơi của E08 |
| A07 | Gỗ khung tranh rung | W01 R02 | E03; không thay đổi clue |
| A08 | Móng chim và cánh khẽ | Hốc B01 R02 | Dấu báo E04 |
| A09 | Cánh bật và tiếng chim ngắn | B02 R02 | Cao trào E04, ngắn và có nguồn |
| A10 | Sấm gần và rung kính | Ngoài ô kính R01 | E06, kết hợp sét có hướng |
| A11 | Ba nhịp chuông xa | Nhánh W05 R01 | Báo lựa chọn quay đầu E05 E06 |
| A12 | Gậy vụt và va chạm | B04 cạnh người chơi | E06A trước blackout |
| A13 | Hơi thở, ù tai, nhịp hồi phục | Gần góc nhìn | Sau scare hoặc ngất |
| A14 | Giấy, ảnh, dấu và nút máy ảnh | Đồ đang tương tác | Phân biệt vật phẩm và thao tác |
| A15 | Bản lề và chốt giường | G01 R00 | Open và lối xuống được mở |
| A16 | Kính rung gõ hoặc cọ nhẹ | Ô kính R01 và hốc G68 | E07 hoặc báo hiệu E10 |
| A17 | Cửa va khung và chốt cài | G60 G61 R03 | Mở đầu E08, khớp điểm tiếp xúc |
| A18 | Ba tiếng gõ ngoài cửa | Mặt ngoài G60 | E08, chỉ sau thử tay nắm đầu |
| A19 | Bước chân tiến gần rồi dừng | Ngoài cửa R03 | Nhịp căng E08, không phát trong tai |
| A20 | Bản ghi và tiếng máy | G63 R04 | E11, Play Stop có trạng thái |
| A21 | Câu cuối ở ghế trống | Phía sau ghế R04 | E11, cùng giọng với bản ghi |
| A22 | Nhịp gõ truyền qua ống | Các điểm R01 R04 R05 | E09, mỗi lần chỉ một nguồn |
| A23 | Cơ đồng hồ cũ tích rồi dừng | G66 R01 | E16, nguồn trang trí có nhãn hỏng |
| A24 | Bút chì lăn và chạm gỗ | G65 R02 | E14, âm gỗ nhẹ, không tiếng lon |

A11 có âm sắc gần D03 nhưng nghe xa và mờ qua tường. Nếu có nút thử tiếng D03, dùng một biến thể cận của cùng nguồn âm. Không dùng sự giống nhau này làm mật mã bắt buộc. A04 có tiếng ăn chốt thấp chắc và tiếng thử sai ngắn khô; không dùng một tiếng giống hệt cho cả hai.

## 3 Âm có vị trí và đường truyền

Đặt nguồn âm vào đối tượng hoặc điểm phát thực. A06 xuất phát tại R03, truyền nhỏ hơn qua góc hành lang rồi mạnh hơn khi đến gần kệ. Sau tiếng rơi, G14 nằm dưới đúng kệ đó. A07 ở khung W01, không phát ngay trong tai khi người chơi đang đứng R04. A10 chủ yếu từ ô kính và bầu trời, còn tiếng rung kính từ chính ô kính.

Tiếng qua cửa hoặc góc gấp giảm độ rõ và bớt âm cao; bước vào gian nghe đầy đủ hơn. Dùng mức vang theo gian để tránh cảm giác âm mọi nơi đều phẳng. Phòng trực và kho nhỏ có đuôi ngắn; gian tranh có đuôi dài hơn vừa phải; hành lang có phản xạ định hướng. Giá trị cuối được chỉnh theo khối dựng thử, không ấn định khoảng cách suy giảm khi mặt bằng chưa chốt.

Nếu dùng loa stereo, nguồn quan trọng không được chỉ nghe bằng một tai hoặc chỉ ở một dải cao hẹp. Cung cấp phụ đề môi trường có thể bật: “Tiếng kim loại rơi ở gian phục chế”, “Chuông phía sau”, “Kính rung ở hành lang”. Mọi clue bắt buộc vẫn có đường dẫn bằng sổ và hình, kể cả khi tắt âm.

Người chơi dừng lại thì tiếng bước dừng, không tiếp tục loop. Xoay hiện vật nghe một tiếng đế ngắn theo bắt đầu chuyển động, không phát lại cùng âm mỗi frame. Mỗi vật liệu có vài biến thể để lặp thao tác không nghe máy móc. Đồ nhặt có âm vừa đủ phân biệt giấy với đồng; không dùng tiếng chói cho từng lần mở balo.

## 4 Phối âm theo nhịp

Đặt ưu tiên cho thao tác người chơi và thông tin. Khi có âm định hướng như A06, giảm nền giông vừa đủ nghe nguồn và giữ hướng phát. Khi đọc một giấy, âm nền giữ ổn định và các cao trào đang chờ được hoãn. Khi giải chốt, A04 nổi rõ; không phủ sấm lên đúng thời điểm người chơi cần biết đã giải đúng chưa.

Sáu cụm lớn không đồng nghĩa sáu lần bật âm cực lớn. E09 thiên về nghe nguồn, E10 về bằng chứng ảnh và E11 về thay đổi vị trí giọng. Đặt trần ba cao trào mạnh của E08 E04 E06; những cụm khác dùng mức thấp hoặc vừa. Một cao trào dùng ít nguồn cùng lúc: âm báo, âm chính và âm hồi phục. E06 dùng A11 trước, A10 cho sấm, A12 cho cú đánh, âm NG theo phần 11, rồi A13 khi đã tỉnh. Không phát đồng thời chim, lon rơi, khung rung và nhạc lớn. Các event khác được khóa tạm bởi đạo diễn nhịp trong tài liệu event.

Mức scare phải được nghe thử trên tai nghe và loa thường. Cảm giác giật đến từ tương phản, thời điểm và khoảng cách gần, không chỉ tăng âm lượng. Có thanh chỉnh âm nền, âm tương tác và cường độ scare; giảm scare vẫn giữ tiếng chốt, tiếng giấy và nguồn định hướng. Kiểm không clip hoặc làm mất hoàn toàn tiếng bước sau khi giảm âm rồi khôi phục.

## 5 Hệ thống ánh sáng

L01 là đèn pin duy nhất của người chơi. Vòng trung tâm sáng để đọc, vùng rìa mềm cho biết khối phòng. Chùm sáng có độ lan đủ tìm lối đi, không chỉ một chấm rất nhỏ. Bề mặt gần không cháy trắng, mặt đáy có chữ đen vẫn đọc được. Ánh sáng có suy giảm theo khoảng cách và vật cản, không xuyên tủ hoặc tường.

L02 là ánh trời giông lọt qua ô kính cao và khe hở có thật. Cường độ thấp, tông lạnh, chỉ cho thấy silhouette đường đi. L03 là ánh sáng phản xạ môi trường rất yếu để vật không hoàn toàn đen khi đèn quay đi; phải có cơ sở từ L02 và vật liệu, không là một nguồn đèn vô hình sáng cả phòng. R00 không có đèn bàn hoạt động.

L04 là sét ngoài nhà. Sét chiếu từ hướng ô kính, tạo bóng hoặc vùng sáng trên vật ở gần nguồn; gian kín bên trong chỉ nhận phần ánh hắt nhỏ. Không cho cả bảo tàng sáng trắng đồng đều. L05 là hiệu ứng mờ, giảm tầm nhìn hoặc tối ngắn của góc nhìn; đây là lớp trình diễn được kiểm soát, không là một nguồn sáng thật.

| Mã | Nguồn | Quy tắc |
| --- | --- | --- |
| L01 | Đèn pin | Luôn trở lại trạng thái đủ đọc sau event |
| L02 | Ánh trời qua ô kính | Có vị trí, hướng và độ che thực |
| L03 | Ánh hắt trong nhà | Yếu, giữ khối đường đi, không lộ toàn phòng |
| L04 | Sét | Chỉ kích hoạt trong các nhịp thời tiết định nghĩa |
| L05 | Mờ hoặc blackout | Ngắn, tùy chọn giảm, không che clue đang đọc |

## 6 Màu sắc vật liệu và khả năng đọc

Khung xanh ngọc W01, đồ áo đỏ gạch và vàng trong tranh, chén xanh lam, đồng xanh của lá và giấy kem là nhóm màu chủ đạo. Bề mặt tối vẫn giữ màu dưới đèn pin, không đặt lớp lọc xám làm tất cả ảnh giống nhau. Vật liệu cũ có bụi, xước và bong cục bộ, nhưng vùng chữ và hình quyết định được chừa sạch.

Kính khung W04 có phản xạ nhẹ để thấy chất liệu, không dùng một vệt lóa luôn che chữ II. W02 W03 không kính. Đáy D01 đến D03 dùng tương phản nét và một vùng phẳng, không chỉ khác roughness để hiện ký hiệu. F03 phải đọc B và R bằng chữ, không suy từ màu thẻ.

Chế độ xem ảnh giấy có ánh sáng giao diện ổn định. Vẫn thấy vật liệu và mép giấy nhưng việc đèn pin chớp ngoài thế giới không làm trang đọc tối đi. Bản chép chữ hỗ trợ người khó nhìn; không bổ sung lời giải khác với texture. Người chơi có thể tăng độ sáng và kích thước chữ mà không thay điều kiện progress.

## 7 Phối hợp âm và sáng trong các cảnh

### Chim xuất hiện ở tượng

E04 bắt đầu bằng A08 khẽ từ hốc tượng, rồi một đợt L01 yếu ngắn. Chỉ đặt B02 lên B01 khi hốc thực sự khuất hoặc khi màn hình tối hoàn toàn; tắt đèn mà vẫn thấy tượng nhờ L02 chưa đủ điều kiện đổi trạng thái. Khi đèn hồi phục, chim đứng im cho người chơi nhận ra. Không giật A09 ngay ở frame ánh sáng trở lại.

Sau khi nhìn thấy chim một nhịp, chim giật cánh cùng A09. L01 giữ sáng trong cú giật để hình và tiếng khớp. Có thể cho chim rời khỏi hốc bằng một đoạn chuyển động ngắn hoặc chờ đổi trạng thái khi hốc khuất tiếp; không cần bay qua cả phòng. Hồi phục giữ A01 nhỏ và kết thúc mờ màn hình nếu có.

### Quay đầu và sấm

E06 có nhịp nhìn lại nhưng không thấy gì. Góc nhìn nâng nhẹ về ô kính cao, A01 được giảm, L04 chớp từ ngoài rồi A10 phát sau một khoảng rất ngắn phù hợp nguồn sét gần. Ánh sáng trả về mức nền trước khi hình người B03 xuất hiện trong biến thể A, tránh dùng nhiều chớp liên tục để che một model đặt sai.

B03 và gậy B04 xuất hiện tại điểm đã được giấu lúc người chơi nhìn lên. A12 khớp chuyển động gậy; L05 tối ở thời điểm va chạm. Sau blackout vào scene NG; A13 chỉ nghe nhỏ khi đã trở lại bảo tàng qua cổng hoặc bỏ đoạn chạy. Không hiện một dòng “chết” hoặc tiếng game over. Biến thể B thay cú đánh bằng va đập hoặc choáng từ phía khuất, được mô tả rõ là phương án tiết kiệm asset.

### Tiếng rơi ở gian khác

E02 không tắt đèn. A06 phát từ gian R03 lúc người chơi đang ở gian khác và vật ngoài tầm nhìn. Trong lúc chạy tới nguồn, A03 và bước chân vẫn bình thường. G14 trên sàn là kết quả nhìn thấy được; không thêm một tiếng gào khi nhìn lon. Đây là nhịp bí ẩn mức thấp giữa hai đoạn giải đố.

## 8 Tắt đèn và hồi phục

Không có pin giảm theo thời gian. Đèn chỉ yếu, chớp hoặc tắt trong một event có điểm kết thúc xác định. Bản đầu nên dùng thay đổi cường độ chậm và một khoảng tối khoảng dưới hai giây, không dùng strobe lặp nhanh. Thời lượng cuối được chỉnh bằng chơi thử; chế độ giảm hiệu ứng có thể bỏ khoảng tối mà giữ tiếng và thay đổi môi trường ngoài tầm nhìn.

Trước khi tắt đèn, hệ thống kiểm người chơi không ở mép lối xuống, không đang đọc và không trong tương tác chính. Nếu điều kiện không phù hợp thì hoãn hoặc bỏ nhịp, không ép người chơi đứng chờ. Đèn trở về mức chuẩn khi event hoàn tất, bị hủy, tải lại hoặc rời vùng trước trigger.

Trong blackout và scene NG, tiến trình bảo tàng và đồ vẫn giữ. Âm/ánh sáng của NG nằm ở scene riêng, không giữ một lớp mờ blackout trên toàn đoạn chạy. Âm cao trào kết thúc trước khi điều khiển trả về; chỉ giữ một ù tai giảm dần ngắn. Người chơi có thể mở sổ ngay khi tỉnh lại. Không duy trì mờ, rung và yếu đèn trong vài phút để kéo dài thời lượng.

## 9 Khoảng nghỉ và kiểm thử

R00 và bàn đọc R04 là các vị trí ít biến động. Sau mỗi cao trào, dành một đoạn đi hoặc đọc bình thường với nền ổn định. Đạo diễn nhịp tạm khóa scare tiếp theo, nhưng không khóa câu đố hay yêu cầu chờ đủ thời gian để lấy item. Event không được phát khi người chơi chỉ đứng lâu trong menu.

Kiểm từng âm có nguồn và kết quả phù hợp. Đi qua cửa, góc gấp và gian khác để nghe khoảng cách. Chơi với âm lượng thấp, không âm và phụ đề để kiểm đường chính vẫn rõ. Kiểm L04 ở các gian không có cửa sổ; ánh sét không được phát sáng xuyên tường.

Kiểm đèn ở vùng chữ nhỏ nhất, đáy đồ vật, khung có kính, ảnh trong balo và nắp giường mở. Kiểm tải game giữa chớp, blackout và đoạn tỉnh lại để ánh sáng không mắc kẹt. Cuối cùng xem một lượt có Camera: ảnh chụp phải phản ánh ánh sáng thực lúc chụp, không lưu HUD và không vô tình tạo flash mới.

## 10 Phối âm sáng cho ba cụm bổ sung

E08: A17 phát khi cánh G60 chạm khung, tiếng chốt đến ngay sau đó. L01 chỉ giảm nhẹ khoảng 0,25 giây rồi đủ đọc; không làm căn phòng tối liên tục trong câu đố. A18 phát ngoài mặt cửa sau lần thử tay nắm đầu. A19 được xếp lịch sau khi người chơi đối chiếu F07 F08 I09 rồi đóng giao diện; không kiểm giả thuyết đúng sai. Bóng dưới khe là hiệu ứng môi trường, không là một NPC phải dựng đi bộ. Khi đọc F08 I09, nền ổn định và không có sét lớn.

E09: A22 đi qua ba điểm âm biên soạn sẵn. Nguồn kế tiếp chỉ phát khi người chơi đến vùng nguồn trước và đang đi lại. Tường và góc gấp lọc âm theo đường truyền; không cho một tiếng gõ nhảy thẳng vào tai. Kết thúc ở G64 phát một nhịp trầm thấp rồi trở về A03, giúp người nghe nhận ra đường ống hướng xuống. Có phụ đề chỉ gian nguồn, không ghi đáp án. Không tắt đèn, không kéo camera và không khóa lối.

E10: có một tiếng cọ kính nhỏ mời nhìn hốc G68, dùng biến thể A16 tại hốc. Khi chụp, A14 phát tiếng màn trập; ảnh dùng ánh sáng thực L01 L02. Không thêm flash hoặc lớp người vào file ảnh. Giảm nền rất nhẹ lúc xem lại ảnh rồi trả về khi đóng. B05 không biến mất trong tầm nhìn chỉ vì đèn yếu hoặc vì album đang mở.

E11: A20 bắt đầu từ máy G63 với tiếng cơ quay ngắn rồi giọng rõ. Sau khi bản ghi kết thúc hoặc người chơi nhấn Stop ở nhánh hợp lệ, một khoảng yên khoảng hai giây tách nguồn. A21 nói “Mang giấy theo.” từ phía ghế trống bằng cùng giọng, với âm phòng rõ hơn và bớt nhiễu băng. Không đặt giọng này ở mọi nơi hoặc bắt người chơi xoay đúng góc để nghe. L01 giữ sáng; sự bất an đến từ vị trí giọng sau khi máy đã dừng. Kết thúc trả nền bình thường.

Kiểm thêm hủy event và tải giữa A17, A20 A21 hoặc giữa hai nguồn A22. Không lặp tiếng cài cửa nếu cửa đã mở khóa, không để tiếng máy chạy sau Stop và không nối giọng từ máy cũ sang vùng âm khác khi tải. Dữ liệu gốc về giờ, nhãn và mã trên các ảnh giấy luôn giữ nguyên.

## 11 Âm sáng cho thế giới ngất và lúc tỉnh

Đây là yêu cầu cho đợt âm/ánh sáng sau, không yêu cầu tìm asset ngay khi dựng nhà. Bản shape có thể dùng vật liệu màu/self-lit để thấy đường và cổng. Scene riêng không dùng L01 làm nguồn nhìn đường duy nhất.

| Mã | Nguồn | Vai trò |
| --- | --- | --- |
| A25 | Gió/nền ở WORLD-NGAT-01 | Âm liên tục nhỏ, thưa ở khoảng nghỉ, không giọng đọc đáp án |
| A26 | NG-CHASER phía sau | Nhịp truy đuổi theo gap; giảm khi tới đoạn cổng, không tăng âm lượng vô hạn |
| A27 | Vật cản NG đã chạm | Phản hồi ngắn đúng lần va; không lặp mỗi frame |
| A28 | NG-PORTAL | Âm mở rộng ở cổng rồi ngắt khi chuyển về R01 |
| A29 | FX-E06-WISP | Âm rất nhỏ khi đốm tắt; không dùng thêm stinger mạnh lúc tỉnh |
| L06 | Mặt đường/khung của NG | Đường và cả ba làn luôn đọc được; khoảng nghỉ giảm nhịp, không tắt sàn |
| L07 | NG-PORTAL | Tông trắng ngà ấm, một nhịp fade có tùy chọn giảm sáng |
| L08 | FX-E06-WISP trong R01 | Đốm sáng tại vị trí thật, phạm vi nhỏ, tắt/co một lần; không thay L01 |

L07 và L08 có tông chung để gợi liên hệ, không bắt người chơi phân biệt màu để vượt. Chaser có âm phát sau người chơi theo khoảng cách; menu dừng nền điều khiển và mọi timer, resume không phát cú va mới. Khi tỉnh, trả nền A01/A03 và L01 chuẩn, A13 lùi nhanh. Không phát A29 như một cú giật thứ hai và không rải sét/nháy liên tục trong NG. Các mốc hình và state ở [07_the_gioi_ngat_va_quy_tac_thong_tin](07_the_gioi_ngat_va_quy_tac_thong_tin.md).
