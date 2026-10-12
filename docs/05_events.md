# Sự kiện và nhịp kinh dị

> Cập nhật kiến trúc 13/10/2026: các mã R dưới đây là vùng chức năng của gameplay, không quyết định mặt bằng hoặc tọa độ nhà. Nguồn dựng hiện hành là ZIP và [kế hoạch kiến trúc thô Blender](06_cach_build_bao_tang.md). Việc ánh xạ item/event sang map mới thực hiện sau khi chốt kiến trúc; hiện chỉ dựng kiến trúc thô, chưa triển khai gameplay.

Tài liệu event · Thiết kế phiên bản 4 · 12 tháng 10 năm 2026

Bộ thiết kế gồm sáu cụm event lớn có tình huống khác nhau và mười hai event nhỏ. Chỉ một cụm nhốt người chơi trong phòng. Các cụm còn lại dùng sinh vật, lựa chọn hướng nhìn, truy nguồn âm, Camera hoặc bản ghi âm. Mọi nhánh trở lại mạch chính tìm chìa khóa, mở giường và thoát xuống dưới; không tạo một kết thúc riêng cho mỗi event.

## 1 Phạm vi và thứ tự

| Cụm lớn | Tình huống | Hoạt động chính | Quan hệ với truyện |
| --- | --- | --- | --- |
| E08 | Cửa gian phục chế tự niêm phong | Đối chiếu nhiều nguồn và mở khóa | Lấy I12 cho hồ sơ chính |
| E04 | Chim xuất hiện trên tượng | Nhận ra thay đổi, phản ứng với sinh vật | Bảo tàng có khe hở và sự sống |
| E05 E06 | Lời nhắc đừng quay đầu | Chọn đi tiếp hoặc quay lại, ngất và truy đuổi ở scene riêng | Trở lại thực tại với đốm sáng tắt |
| E09 | Tiếng gõ chạy qua đường ống | Chủ động nghe và theo nguồn | Gợi tuyến kỹ thuật nằm thấp |
| E10 | Camera giữ một bóng đã biến mất | Chụp và đối chiếu với hiện trường | Giữ dấu vết trải nghiệm cá nhân |
| E11 | Giọng nói tiếp tục sau khi máy dừng | Nghe hoặc ngắt bản ghi, kiểm tra nguồn | Người trực muốn mang hồ sơ ra ngoài |

E08 là gameplay bắt buộc khi lần đầu vào R03. Năm cụm còn lại tùy hành vi và điều kiện; bỏ qua vẫn kết thúc được. Sáu cụm không đồng nghĩa sáu jumpscare cực mạnh. Đặt trần ba cao trào mạnh cho E08 E04 E06; E09 E10 E11 ưu tiên bất an, điều tra và khoảng yên. E05 E06 là hai nhánh của cùng một cụm, không tính thành hai cụm lớn.

Thứ tự theo mốc: E10 có thể sẵn sàng sau P02 nếu đã có O04; E08 xảy ra lần đầu đi hẳn vào R03; E05 E06 sau P03; E04 sau P04; E09 E11 sau P05. Người chơi vẫn có thể thăm các gian từ sớm. Khi đã nhặt O05, hủy các scare còn chờ; đường về R00 ổn định. Chỉ âm môi trường thường và event chuyển môi trường E19 ở cuối vẫn tồn tại.

Mỗi cao trào có khoảng hồi phục, không chạy một cú giật khác ngay khi người chơi vừa được mở cửa hoặc tỉnh lại. Tạm khóa cao trào mạnh tiếp theo khoảng sáu đến tám phút điều khiển thực, không tính menu. Đây là luật phân phối event, không là thời gian buộc chờ để làm câu đố. Event đến quá muộn được bỏ thay vì phát bù.

## 2 Trạng thái và quyền điều khiển chung

Trạng thái chung là CHỜ, SẴN SÀNG, BÁO HIỆU, DIỄN BIẾN, HỒI PHỤC, HOÀN TẤT. Lưu từng trạng thái, nhịp đã chạy, đạo cụ trước sau và biến thể của event. Chỉ một cụm được sở hữu camera, đèn pin hoặc chuỗi trình diễn tại một thời điểm. E08 giữ quyền cho phần trình diễn của phòng, nhưng không chặn thao tác đọc, xoay vật hoặc giải P03.

Nhặt hay đọc giấy chỉ đặt điều kiện sẵn sàng. Cảnh chờ người chơi đóng chế độ xem, rời vùng tương tác và có khoảng an toàn mới phát. Không dùng một scare che chữ, sửa texture bằng chứng, lấy mất item hoặc báo đáp án đúng bằng một tiếng hù. Các nguồn cần suy luận luôn xem lại được. Dữ liệu gốc không thay đổi theo thời gian event.

Thay đối tượng khi ngoài tầm nhìn cần kiểm cả camera đi lại và job Camera đang chụp. Tắt đèn riêng không đủ nếu ánh trời vẫn cho thấy đối tượng. Nếu không có điều kiện che thật, hoãn hoặc bỏ phần thay đổi. Đạo cụ không cắt vào đường đi, không đẩy người chơi, không thay hình học phòng.

R00 là vùng yên tĩnh. Bàn đọc R04 bảo vệ lúc xem hồ sơ; E11 chỉ là tương tác Play riêng tại đó. Nếu người chơi đi nhanh, event không chạy theo họ để giật. Khi giảm scare, giảm chớp hoặc bỏ cảnh, trạng thái tiến trình và kết thúc vẫn như nhau. E08 giữ câu đố ngay cả khi bỏ phần hù của nó.

## 3 E08 Cửa niêm phong của gian phục chế

### Mục tiêu và điều kiện

Người chơi tự vào R03 và bị khóa một lần. Mục tiêu cục bộ là khôi phục hồ sơ kiểm định để mở cửa; I12 là phần thưởng nối vào vụ tráo đồ. Không đặt thêm cửa sập ở gian khác. Cửa G60 mở khóa vĩnh viễn sau lời giải, kể cả quay lại nhiều lần.

Kích hoạt khi E08 chưa hoàn tất, người chơi đi hẳn qua ngưỡng vào phòng, ra khỏi vùng quét cánh và không đang trong một cutscene. Nếu đang đứng ở đường quét, hoãn; nếu quay ra trước khi đủ điều kiện, chưa phát tiếng sập. Không dựng một tường vô hình ngay khi đặt chân vào cửa. F02 ở gian khác không là điều kiện vào hoặc giải E08.

Tất cả chín nhóm nguồn luôn nằm trong R03: F07; D01 D02 D03 D04; I08; F08; I09; I10; W07; I11; W08. Không nguồn nào bị khóa bởi P03, không cần máy ảnh O04 và không cần đoán một nét cực nhỏ. Có thể làm câu đố ngăn bàn P03 trong lúc bị nhốt nếu đã có F02; hai cơ cấu độc lập.

### Các lớp suy luận

F07 ghi năm khai trương 2012, cho thấy cửa đã được lắp và chén gốc có vết sứt chân. I08 nói khóa giữ bảng quy đổi khi lắp đặt; người trực đã đặt tổ hợp theo hồ sơ cuối trước đêm niêm phong năm 2016. Tổ hợp cơ khí đã là 3581 từ đầu, không tự biết người chơi đọc tài liệu gì. F08 có sáu ảnh cùng đêm; I09 cho biết máy A nhanh 7 phút và máy B chậm 5 phút. I11 xác định báo động lúc 21:20 theo giờ chuẩn. W07 yêu cầu lấy lần kiểm định cuối của bản gốc trước báo động rồi xếp theo giờ thật.

| Ảnh | Giờ in | Giờ thật | Xử lý |
| --- | --- | --- | --- |
| Chén có vết sứt, A | 21:19 | 21:12 | Giữ, đúng bản gốc |
| Lá, B | 21:09 | 21:14 | Giữ |
| Mặt nạ, A | 21:23 | 21:16 | Giữ |
| Chuông, B | 21:13 | 21:18 | Giữ |
| Chén không sứt, A | 21:24 | 21:17 | Loại, bản sao dù có thẻ B08 |
| Mặt nạ, B | 21:17 | 21:22 | Loại, sau báo động |

I10 gọi chén lúc 21:17 là bản gốc, tạo một mâu thuẫn có căn cứ thị giác để kiểm chứng. Mặt nạ là vật đối chứng B31, không bổ sung một vụ tráo thứ tư vào bộ ba chính. Dấu mặt dưới của chén, lá, mặt nạ, chuông là trăng, sóng, sao, cây. Chuẩn 2012 trên W08 đổi chúng thành 3, 5, 8, 1. Chuẩn 2016 cho số khác, nên phải có căn cứ chọn năm.

Đáp án 3581 mở khóa và nhả khay G62 chứa I12. Cửa kiểm bốn số và thao tác tay gạt, không kiểm hạn ngạch đã mở đủ chín thẻ. Người biết lời giải có thể mở nhanh. Không áp dụng phép chỉnh giờ, lọc ảnh giả và bảng đổi dấu này sang mọi câu đố khác của game.

### Nhịp trình diễn

1. Khi người chơi vào đủ sâu, G60 đóng trong khoảng 0,7 giây. A17 phát lúc cánh chạm khung, tiếng chốt tiếp theo sau khoảng 0,2 giây. L01 giảm nhẹ khoảng 0,25 giây rồi trở lại đủ sáng. Không ngất hoặc dịch chuyển người chơi.

2. Lần đầu thử tay nắm, tay nắm chuyển nhưng chốt không nhả. Sau khi buông khoảng hai giây, A18 gõ ba nhịp ở mặt ngoài cửa, cách nhau khoảng 0,45 giây. Thử thêm chỉ có tiếng cơ khí; không lặp tiếng gõ. Sổ đổi mục tiêu sang mở cửa từ bên trong, không đòi một chìa khóa mới.

3. Khi đã xem I09, đóng giấy và rời bàn, hộp sắt dẹt G69 trên kệ chỉ đổi sang trạng thái dưới kệ lúc khuất. A06 phát tại hộp. I11 ở ngăn mở gần đó từ đầu; tiếng rơi chỉ gợi chú ý. Nếu không nghe hoặc không đi theo, giấy vẫn tìm được. G14 của E02 là lon khác, không đặt lại G69 lên kệ để làm rơi lần nữa.

4. Khi đã xem F08 và mặt dưới bốn vật, D04 có thể quay nhẹ về hướng đi lại lúc ngoài tầm nhìn. Chỉ pose đổi, tem sao và B31 giữ nguyên. Nếu đang xem hoặc quay D04, bỏ nhịp tự quay. Một tiếng đế cọ nhỏ báo nguồn; không cần animate khuôn mặt hay đổi ảnh kiểm định.

5. Sau lần đối chiếu F07 F08 I09 trong giao diện, đóng giao diện mới xếp lịch nhịp căng. Event không kiểm người chơi đã đánh dấu giả thuyết đúng hay sai, để không trở thành tín hiệu đáp án. A19 có vài bước ngoài cửa trong khoảng hai đến ba giây rồi dừng; một bóng thấp lướt qua khe khoảng một giây. L01 có thể yếu ngắn nhưng không tối hoàn toàn. Không có NPC phải dựng đi bộ trong phòng.

6. Sau nhịp căng, trả nền và ánh sáng chuẩn, không thêm động tác hù trong ít nhất một đoạn điều khiển bình thường khoảng một phút. Người chơi vẫn giải cửa ngay được; luật nghỉ chỉ hạn chế scare. Nếu đã giải trong lúc event còn chờ, hủy những nhịp hù chưa phát.

7. Nhập sai tạo tiếng chốt khô A04 và giữ vòng số, đồ cùng góc vật. Không tự reset cả tổ hợp, không phá giấy hoặc phạt bằng scare. Gợi ý chủ động có ba lớp: xác định ảnh bản gốc, chú ý giờ của từng máy, rồi cách chọn chuẩn mã. Lời giải cuối chỉ hiện khi người chơi yêu cầu mức cao nhất.

8. Nhập đúng, chốt rút và khay G62 trượt ra khoảng 0,3 giây, cùng A04 thành công. Người chơi tự mở cánh và nhặt I12. Nếu rời phòng chưa nhặt, sổ chỉ phiếu còn trong khay; quay lại không bị khóa. Sau khi giải, trả mục tiêu chính và bỏ các nhịp hù của E08 còn treo.

### Lưu tải và trường hợp biên

Lưu E08_STARTED, DOOR_LOCKED, DOOR_SOLVED, bốn số đang chọn, khay mở, I12_OWNED, nhịp đã chạy, pose D04 và trạng thái G69. Tải khi cửa đã khóa đặt người chơi ở điểm an toàn trong phòng và giữ đủ nguồn; không phát lại tiếng sập. Tải khi đang đóng: nếu checkpoint đã ở trong, hoàn tất đóng im lặng; nếu chưa qua ngưỡng, trả cánh mở và chưa kích hoạt. Tải sau DOOR_SOLVED không khóa lại.

Nếu tắt phần kinh dị, vẫn đóng và khóa bằng chuyển động bình thường, hiển thị mục tiêu, giữ mọi manh mối rồi mở bằng 3581. Nếu mở balo trước một tiếng gõ hay bước đang chờ, hoãn đến khi đóng; nếu cửa đã giải trong menu, hủy nhịp. Không thể cần lấy F02 ngoài phòng để ra ngoài lấy chính F02.

## 4 E04 Chim trên tượng

### Mục tiêu và trigger

Cụm này dùng sự xuất hiện của sinh vật và cảm giác một góc quen không còn như trước. Không có câu đố mở cửa, thu đủ giấy hoặc đổi mã. Sẵn sàng sau P04, E08 đã giải, người chơi đi ngang hốc B01 ở R02 và chưa có O05. B02 có nguồn hợp lý từ khe gió hoặc ô kính vỡ gần hốc.

### Diễn biến

1. Gần hốc, A08 là móng và cánh rất nhỏ từ đúng vị trí hốc. L01 chỉ yếu nhẹ; không tắt trong lúc xem W01 W02. Tượng B01 vẫn chưa có chim.

2. Chờ hốc ra khỏi tầm nhìn hoặc một khoảng tối thật đã che hoàn toàn. Khi cả camera và job chụp đều không thấy, bật trạng thái B02 đứng trên tượng. Nếu L02 vẫn cho thấy tượng, chưa được bật. Không đẩy camera quay đi để tạo điều kiện.

3. Khi nhìn lại, chim đứng im một đến hai giây để nhận ra. L01 đã đủ sáng. Không phát A09 ở đúng frame bật đèn. Nếu người chơi không nhìn hốc, chim có thể đứng và cụm kết thúc mức nhẹ.

4. Khi đã nhìn thấy chim trong chế độ đi lại, B02 giật hai cánh và nghiêng ngắn, khớp A09 trong dưới một giây. Không đặt khuôn mặt khác phủ màn hình. Tổng nhịp báo hiệu đến giật khoảng sáu đến mười giây khi người chơi phản ứng bình thường.

5. Chim đứng lại hoặc nhảy một đoạn ngắn khỏi bệ. Chỉ đổi sang trạng thái rời hốc khi khuất tiếp; không cần bay vòng, AI tránh tường hoặc mô phỏng bắt chim. Trả nền A01 và khóa cao trào tiếp theo, không che đường tiếp tục tới R03 R04.

### Phản ứng và lưu tải

Có thể chụp chim vào Camera; ảnh không kích hoạt thêm scare và không là nguồn bắt buộc. Nếu đang đọc hay chụp trong nhịp giật, hoãn chuyển động chứ không xóa ảnh. Nếu không tạo được vùng che để xuất hiện, chạy A08 mức nhẹ rồi kết thúc. Lưu BIRD_REVEALED, BIRD_STARTLED, BIRD_LEFT và E04_DONE. Tải giữa cú giật đưa chim về pose đứng hoặc đã rời theo checkpoint, không giật lại.

## 5 E05 E06 Lời nhắc và việc quay đầu

### Mục tiêu và lựa chọn

Đây là một cụm lựa chọn. W05 ở đầu nhánh R01 viết “Nếu nghe tiếng chuông phía sau, đừng quay đầu lại. Đi tới tấm biển cuối nhánh. Khi chuông ngừng, quay về.” Không cấm quay đầu ở toàn bộ game. Sẵn sàng khi đã xem W05, qua P03, E08 đã giải và có khoảng cho cao trào; người không vào nhánh không bị phạt.

### Nhánh đi tiếp

1. Trong đoạn thẳng cuối nhánh, A11 phát ba nhịp phía sau. Hướng nhìn gốc được ghi tại đoạn thẳng; lia đọc biển, nhìn lên hoặc nhìn xuống không tính là quay đầu.

2. Tới vùng biển “KHU VỰC NIÊM PHONG — QUAY LẠI”, dừng chuông ngay và kết thúc cảnh báo. Nếu chuông tự kết thúc trước đó, cũng được quay lại. Kiểm vùng biển trước kiểm góc quay trong cùng frame để người tới ngõ cụt rồi quay về không bị xử nhầm.

3. Đi lùi ra mà không quay cũng được. Không đóng cửa, bẫy player ở góc hoặc bắt chờ một đoạn dài ở ngõ cụt. Trên đường về chỉ có nền bình thường, không chạy E06 muộn.

### Nhánh chủ động quay lại

1. Trong lúc chuông còn đang cảnh báo, góc nhìn quay quá khoảng 100 độ về phía sau chuyển sang E06. Ngưỡng cần chơi thử để không nhận nhầm. Hành lang trước mắt trống khoảng một nhịp ngắn; không hiện NPC ngay frame quay.

2. Một tiếng kính phía trên mời nhìn ô cao G13. Có thể nâng góc nhìn khoảng nửa giây trong biến thể thường; chế độ giảm chuyển động chỉ giữ âm và sét trong góc đang nhìn. Không dịch vị trí hoặc lật camera 180 độ.

3. L04 từ hướng ô kính rồi A10 sấm gần, với độ trễ nhỏ hợp nguồn sét gần. Thời tiết mưa giông đã có từ đầu. Ánh sáng trở về nền trước nhịp sau; không dùng nhiều chớp liên tục để che model.

4. Biến thể A dùng pose B03 cầm B04 và một chuyển động tay gậy ngắn. Pose được bật khi khuất trong lúc nhìn lên. Gậy vụt cùng A12, L05 tối tại thời điểm va chạm. Biến thể B chỉ có bóng gậy ở mép nhìn, tiếng vụt phía khuất rồi tối. Chọn một biến thể trước lượt chơi; không chạy cả hai.

5. Sau blackout, chuyển vào WORLD-NGAT-01: chạy ba làn trong một scene shape riêng, tránh chướng ngại và một bóng truy đuổi phía sau. Đoạn chạy sạch khoảng 60 giây, có checkpoint và hỗ trợ bỏ thử thách. Không là thế giới tạo từ ảnh, không có item hoặc hồ sơ bắt buộc. Chi tiết điều khiển, đường chạy và lưu tải ở [07_the_gioi_ngat_va_quy_tac_thong_tin](07_the_gioi_ngat_va_quy_tac_thong_tin.md).

6. Qua cổng sáng thì mở mắt tại marker E06_WAKE_SAFE trong vùng liên thông R01 của map mới. Một đốm sáng thật ở marker E06_WISP phía trước, cao khoảng 1,35 m trên sàn, tắt dần. Hai marker được đặt và kiểm tra sau khi chốt kiến trúc; không dùng tọa độ nhà cũ. Nếu đã nhìn thấy nó, xuất hiện suy nghĩ “CÓ VẺ KHÔNG PHẢI MƠ...”. Trả L01 chuẩn, A13 giảm nhanh, giữ toàn bộ đồ và tiến trình; đánh dấu E06_DONE sau khi trở lại an toàn. Nhịp đánh/choáng trước chạy vẫn khoảng tám đến mười hai giây; toàn cụm có thêm đoạn NG, không còn tỉnh ngay sau blackout.

### Kết quả và trường hợp biên

B03 trong nhà chỉ là lần xuất hiện không xác định, không đòi item hoặc canh cửa cuối. NG-CHASER chỉ bám tiến độ trong scene NG, không đi vào bảo tàng. Lưu museum session và phase E06 trước cú đánh; tải giữa chạy về checkpoint NG, tải sau cổng về điểm R01. Bỏ thử thách vẫn trở lại thực tại với tiến trình nguyên vẹn. Quay thêm lần nữa không ngất hoặc chạy lại. Nhánh này vẫn thuộc cụm E05/E06, tổng số cụm lớn giữ sáu.

Nếu ngân sách cao trào không còn, không bắt đầu A11 cảnh báo, để lời nhắn là thông tin tùy chọn. Nếu đã tới biển, chuông dừng, đang đọc, đứng ở vùng nguy hiểm hoặc có O05, không vào nhánh đánh ngất. Cụm này không cung cấp chìa khóa, giấy bắt buộc hay một kết thúc khác.

## 6 E09 Truy nguồn tiếng gõ trong ống

### Mục tiêu và trigger

Cụm điều tra âm thanh gợi sự liên thông theo chiều dọc của công trình. Không nhốt phòng, không tổ hợp số và không đóng tuyến chính. Sẵn sàng sau P05, E08 đã xong và chưa có O05. Người chơi ở đoạn R01 gần R04, không đọc hoặc có cụm khác đang chạy.

### Diễn biến

1. A22 gõ hai nhịp thấp từ điểm âm ở tường R01. Giảm nền vừa đủ nghe, giữ L01 chuẩn. Phụ đề tùy chọn chỉ “Tiếng gõ trong tường hành lang”, không ghi lối thoát. Đi tiếp mục tiêu chính vẫn được.

2. Nếu tới vùng nguồn, âm dừng khoảng hai giây. Một nhịp tương tự vang từ đoạn nối bên R04, bị góc tường lọc bớt âm cao. Điểm trước không tiếp tục gọi cùng lúc. Nếu quay đi, âm còn ở nguồn thật chứ không nhảy về sau gáy.

3. Tới đoạn nối R04, một nhịp thứ ba vang từ R05 và thấp hơn. Không đổi phòng hay mở một cửa bí mật cho sự kiện. Các lối và biển gian giữ nguyên. Âm dẫn người chơi qua những đoạn có thể đi sẵn.

4. Tới G64 ở chân tường R05, A22 là một tiếng kim loại rất thấp qua ống, sau đó chỉ còn A03 thông gió. Cấu trúc khe và hướng ống đi xuống cho thấy âm truyền qua tuyến thấp, không có người đứng sau bảng để hù.

5. Có thể soi, chụp khe hoặc rời đi. Sổ ghi một quan sát bổ sung “Âm truyền qua đường ống hướng xuống”. Nguồn này không thay F04 I04; nhận ra gợi ý sớm vẫn chưa mở giường. Không thêm một câu đố buộc dùng tai nghe.

### Nhánh bỏ qua và trạng thái

Chỉ chuyển nguồn khi player đi đến vùng nguồn trước. Nếu bỏ điều tra và rời tuyến, cho lần gõ hiện tại kết thúc rồi hoàn tất mức nhẹ; không phát mãi để kéo người trở lại. Nếu bước thẳng vào R05, có thể nghe nhịp thấp cuối và bỏ các nhịp chưa chạy. Không có phần thưởng vật phẩm bị mất vì đi sai thứ tự.

Lưu SOUND_ROUTE_STEP, nguồn đang chạy, quan sát G64 và E09_DONE. Tải không đồng thời phát cả ba điểm. Khi O05 được nhặt, dừng phần đang chờ. Tổng nghe chủ động khoảng bốn mươi đến chín mươi giây tùy đường đi; thời gian không là điều kiện mở bảng kỹ thuật.

## 7 E10 Camera và bóng trong hốc kính

### Mục tiêu và trigger

Cụm này để Camera lưu một dấu vết mà hiện trường sau đó không còn. Khác chim, nó tập trung vào xem lại ảnh và nghi ngờ trí nhớ, không có cú cánh giật hay câu đố. Sẵn sàng khi có O04, đã qua P02, chưa có O05 và tới đoạn R01 gần hốc kính G68. Nếu không nhặt Camera, bỏ cụm.

B05 là pose tĩnh trong hốc có kính, nằm trên đế thật. Hốc không mở được và không phải lối ra. Không dựng người đứng lơ lửng ngoài cửa sổ tầng hai, không cần đối thoại hoặc AI. Đây là silhouette không xác định, không buộc diễn giải thành một người sống.

### Diễn biến

1. Khi hốc ngoài tầm nhìn và không có job chụp, đặt B05 vào trạng thái hiện diện. Một tiếng cọ kính nhỏ biến thể A16 từ hốc mời nhìn. Không bật pose ngay tại chỗ người chơi đang ngắm và không ép họ dùng Camera.

2. Người chơi nhìn hốc có thể nhận ra dáng áo hoặc hình người mờ ở nền. Đèn và ánh hắt đủ thấy, không chớp liên tục. Nếu chụp khi pose thuộc khung camera, ảnh lưu đúng hình thế giới tại frame ấy. Chỉ kiểm vùng và trạng thái renderer, không nhận diện nội dung pixel.

3. Âm màn trập A14, một nhịp thở A13 nhỏ rồi trở về nền. Cho người chơi chủ động mở ảnh vừa chụp; không tự mở album để cướp quyền điều khiển. Pose vẫn ở đó nếu player còn nhìn hoặc một job chụp đang xử lý. Không chèn B05 vào file ảnh sau lần chụp.

4. Lần đầu hốc thật sự khuất sau khi đã nhìn hoặc chụp, đổi B05 sang trống. Khi quay lại, hốc chỉ còn nền và đế. Không dùng việc mở album hoặc yếu đèn như bằng chứng đủ để biến mất nếu camera thế giới vẫn nhìn hốc.

5. Nếu xem lại ảnh, B05 vẫn nằm trong ảnh đã lưu. Người chơi có thể so cạnh ảnh F05 hoặc chụp hốc trống lần nữa; game không báo “đúng”, không nhận diện khuôn mặt và không tạo một kết thúc khác. Nếu không chụp trước khi quay đi, cụm vẫn có thể kết thúc bằng quan sát; không tự sinh một ảnh cá nhân.

### Lưu và phản ứng bất thường

Lưu SHADOW_PRESENT, SHADOW_SEEN, SHADOW_GONE, mã ảnh cá nhân nếu có và E10_DONE. Xóa ảnh không làm B05 hiện lại hoặc mất tiến trình. Nếu giữ nhìn rất lâu, pose giữ yên; không dùng timer để xóa trước mắt. Nếu bỏ đi sau âm cọ mà chưa nhìn, chờ vùng che rồi trở về hốc trống và kết thúc mức thấp. Tải phải giữ pose của checkpoint và album, không tạo một ảnh trùng hoặc một bóng mới.

## 8 E11 Giọng ở gian lưu trữ sau khi máy dừng

### Mục tiêu và điều kiện

Cụm này kể động cơ của người trực bằng tương tác âm, không đòi giải mã băng hoặc lấy chìa khóa từ máy. G63 có nút Play Stop và nhãn nguồn tự duy trì. Bản ghi bình thường nghe được từ lúc vào R04; phần giọng đổi nguồn chỉ sẵn sàng sau P05 và trước O05. Không dùng việc đọc giấy để làm một máy đang hoạt động đột nhiên có điện.

Nội dung bản ghi do Linh để lại: “Phiếu nhận lại đã bị sửa. Đừng chỉ tin nhãn trên thùng. Tôi để bản lưu trong khay kiểm định. Nếu ra được khỏi đây, mang giấy theo. Linh.” Cung cấp bản chép lời trong tương tác máy, không tạo một item mới cần nhặt. Toàn bộ thông tin quan trọng vẫn có trong giấy của đường chính.

### Diễn biến và hai cách kết thúc bản ghi

1. Nhấn Play, nút hạ xuống, cuộn quay và A20 tiếng máy trong khoảng nửa giây rồi giọng rõ. L01 giữ sáng. Người chơi được đi, soi và nhấn Stop; không khóa trong một video hoặc buộc đứng đúng một vị trí.

2. Bản ghi dài khoảng hai mươi đến ba mươi giây, điều chỉnh theo bản thu. Nhiễu thấp ở đầu và cuối, không che lời. Âm từ G63 truyền nhỏ hơn khi đi xa hoặc ra hành lang. Mỗi lần Play thường không tạo scare mới.

3. Nếu nghe hết và phần không gian đã đủ điều kiện, máy dừng, cuộn ngừng và có khoảng yên hai giây. A21 nói “Mang giấy theo.” từ phía ghế trống, cùng giọng nhưng rõ âm phòng hơn tiếng băng. Máy không chuyển sang trạng thái Play để phát câu ấy.

4. Nếu chủ động nhấn Stop sau khi đã nghe ít nhất câu đầu trong lượt đủ điều kiện, máy dừng ngay và dùng cùng khoảng yên rồi A21. Nếu Stop ngay trước câu đầu, chỉ dừng bình thường, không biến mọi nhấn nút thành hù. Hai nhánh dùng một cờ E11_SPATIAL_LINE, không phát cả hai trong một lượt.

5. Nhìn về ghế chỉ thấy ghế trống. Không cần một người ngồi rồi đứng dậy, không dịch ghế và không xuất hiện gậy. Nếu người chơi không quay, vẫn nghe nguồn trong phòng. Nếu đã rời xa, chỉ phát tại ghế với suy giảm thật hoặc bỏ nhịp, không gắn lời vào tai ở gian khác.

6. Trả nền trong nhà và để một khoảng đọc bình thường. Sổ bổ sung tên Linh và ý muốn mang hồ sơ đi nếu đã nghe, không mở một ô bắt buộc mới. Có thể nghe lại bản ghi bình thường sau đó; câu ngoài máy chỉ chạy một lần. Cụm không tiết lộ giường hay tầng hai trước F04 I04.

### Lưu tải và giới hạn

Lưu trạng thái Play, vị trí trong đoạn thu, nhánh đã chọn, E11_SPATIAL_LINE và E11_DONE. Tải giữa khoảng yên đưa máy về Stop và chỉ hoàn tất nhịp còn hợp lệ, không ghép hai câu đè nhau. Nếu tải sau câu ngoài máy, không nói lại. Bỏ cảnh hoặc giảm scare có thể giữ bản ghi và bỏ phần đổi nguồn; không mất một lời giải.

## 9 Mười hai event nhỏ

Các event nhỏ có một nguyên nhân, một nguồn âm hoặc chuyển động và một trạng thái sau rõ. Không đếm từng nhịp của sáu cụm lớn thành event riêng. Mỗi event nhỏ chạy tối đa một lần theo mốc, tách nhau ít nhất một đoạn di chuyển hoặc đọc; không lấp mọi khoảng yên. Không nguồn nhỏ nào giữ giấy, dấu hoặc chìa khóa.

| Mã | Trigger và hành vi | Nguồn và kết quả |
| --- | --- | --- |
| E01 | Đọc I00 xong và ra R01 lần đầu; gió cọ khe trong dưới hai giây | A03 tại G13; không thêm clue ở R00 |
| E02 | Có O01, rời R03 và kệ khuất; lon G14 rơi một lần | A06 R03; lon nằm dưới đúng kệ, không nhặt |
| E03 | Sau I03 trở lại R02 khi đi lại; W01 rung vài độ rồi trả | A07 khung; tay trong tranh và vết sứt giữ nguyên |
| E07 | Nhặt F05, đóng xem và rời bàn; kính rung nhẹ một lần | A16 R01; hạ từ scare lớn xuống chi tiết bất an |
| E12 | Lần đầu cất F01; một tiếng giấy tách khỏi mặt ngăn | A14 tại ngăn; item vào balo đúng một bản |
| E13 | Sau khi mở ngăn tùy chọn G43, rời tương tác; ray kéo co nhẹ | A04 nhỏ; ngăn còn mở và không khóa giấy |
| E14 | Sau P02, G65 khuất; bút chì xoay hoặc lăn ngắn ở mép bàn | A24 tại G65; bút vẫn trên bàn, không chứa mã |
| E15 | Đi qua khe R05 lần đầu; gió rít ngắn rồi về nền | A03 đúng khe; không kéo camera hoặc tắt đèn |
| E16 | Đến gần G66 lần đầu; vài tiếng tích rồi dừng | A23; nhãn ĐỒNG HỒ HỎNG ngăn dùng nó làm giờ E08 |
| E17 | Đóng I05 và rời bàn; góc giấy trắng G67 khẽ bật do gió | A14 tại bàn; giấy trắng trang trí, I05 đã ở balo |
| E18 | Ba hồ sơ cuối đã đúng; chốt hộp ăn trước khi nắp mở | A04 tại R05; phản hồi cơ khí, không có scare phụ |
| E19 | Qua ranh giới ra ngoài R06; âm mưa gió mở rộng | A01 bớt lọc; chuyển môi trường và kết thúc, không thêm khóa |

E02 và hộp G69 của E08 là hai đạo cụ khác nhau. E07 không dùng sét gần sau khi vừa có E06. E12 E18 là phản hồi tương tác có thời điểm, không tạo nhịp đột ngột. Với người chơi đi nhanh, có thể bỏ E14 E17 thay vì chờ phát bù khi đã quay lại R00.

## 10 Điều phối và quyền ưu tiên

Ưu tiên: cảnh kết thúc và thao tác nguồn chính; E08 đang khóa; một cụm đang diễn ra; cụm lựa chọn đã bắt đầu; cụm điều tra mới; event nhỏ. Một owner chiếm phần trình diễn, không chiếm việc mở sổ hay nhặt đồ. Khi player mở menu, tạm dừng bộ đếm trình diễn; khi đóng, kiểm lại vị trí và trạng thái trước khi tiếp tục.

Nếu hai trigger cùng hợp lệ, không chạy cả hai. Ví dụ sau P04, E04 có thể sẵn sàng còn E03 chờ; chỉ chạy rung khung nếu chim chưa vào báo hiệu. Sau khi chim giật, hoãn mọi detail động ngắn để có khoảng nghỉ. Nếu E05 đã phát chuông, E10 không được bật một bóng khác tại hốc gần đó.

Không hủy tiến trình đọc hoặc câu đố chỉ vì event hết vùng. Cụm tùy chọn đi khỏi vùng có thể kết thúc nhẹ; cụm E08 chỉ kết thúc phần khóa khi đã giải, với đủ nguồn địa phương. Sau O05, hủy mọi scare chờ và giữ đường về; E19 là chuyển âm của đoạn cuối, không một cao trào mới.

## 11 Kiểm tra logic và chi phí sản xuất

Kiểm sáu cụm riêng rồi ghép một lượt bỏ mọi tùy chọn, một lượt đi đủ nhánh và một lượt đi nhanh. Mỗi lượt phải nhặt I12, hoàn tất 19 nguồn, lấy O05, mở giường và ra ngoài. Khác nhau ở trải nghiệm và ghi chú bổ sung, không ở số kết thúc.

| Trường hợp | Kết quả phải có |
| --- | --- |
| Vào R03 trước F02 | Mở được cửa bằng toàn bộ dữ liệu trong R03 |
| Đứng trong vùng quét cánh | Hoãn đóng, không nghiền hoặc dịch player |
| Nhập 3581 ngay | Nhận đúng, không yêu cầu đọc đủ thẻ |
| Mở cửa rồi quên I12 | Khay giữ giấy và có chỉ dẫn quay lại, không nhốt nữa |
| Đọc lúc có event chờ | Không che chữ, không yếu đèn, hoãn hoặc hủy đúng trạng thái |
| Tới biển rồi quay đầu | Chuông dừng trước kiểm góc, không ngất |
| Tải giữa ngất hoặc NG | Đúng phase/checkpoint theo file 07, giữ museum session, không đánh hoặc chạy lại khi đã qua cổng |
| Giữ nhìn chim hoặc B05 | Không bật tắt đối tượng ngay trước mắt |
| Xóa ảnh Camera | Không xóa clue hoặc chạy lại E10 |
| Stop máy ghi ngay | Dừng bình thường, không phát câu ngoài máy quá sớm |
| Theo âm sai đường hoặc tắt âm | Mạch chính và nguồn giấy vẫn hoàn thành được |
| Hai cụm cùng sẵn sàng | Một owner chạy, cụm còn lại hoãn hoặc bỏ |
| Có O05 khi scare còn chờ | Bỏ scare, đường về ổn định |

Chi phí trọng tâm là G60 G61 G62 cùng giao diện đối chiếu cho E08. E04 cần chim tĩnh và hai cánh; E05 E06 cần vùng lựa chọn, ánh sét, pose gậy/bóng, scene NG ba làn với chaser theo tiến độ và đốm sáng khi tỉnh; E09 chỉ cần nguồn âm và khe; E10 cần pose tĩnh trong hốc cùng ảnh frame thật; E11 cần nút, cuộn và âm thu. Không cần đẩy tủ, AI tìm đường truy đuổi trong nhà, dựng cả chuyến vận chuyển, tạo phòng 3D từ ảnh hoặc animate NPC kéo người. Scene NG dùng đường chạy cố định theo file 07.

## 12 Nguồn tham khảo phương pháp

Ron Gilbert mô tả các nhánh câu đố phụ thuộc nhau rồi hội tụ, giúp nhìn ra ngõ cụt và điểm nghẽn. Áp dụng ở đây cho các nguồn của E08 và các hồ sơ chính, không sao chép nội dung câu đố từ trò chơi khác. Nguồn: https://grumpygamer.com/puzzle_dependency_charts/

Thomas Grip của Frictional Games mô tả việc giãn scare, để người chơi khám phá bí mật và dùng bối cảnh truyện nuôi sự bất an. Áp dụng ở đây cho khoảng hồi phục và khác biệt giữa sáu cụm. Nguồn: https://frictionalgames.com/2019-10-9-years-9-lessons-on-horror/
