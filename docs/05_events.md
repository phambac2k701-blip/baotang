# Sự kiện và nhịp kinh dị

Tài liệu event · Thiết kế phiên bản 2 · 12 tháng 10 năm 2026

Sự kiện tạo cảm giác bảo tàng đang phản ứng khi người chơi tìm ra thông tin. Chúng được tổ chức theo trạng thái, vị trí và nhịp âm sáng, không chạy ngẫu nhiên giữa lúc đọc clue. Các cảnh chim xuất hiện, quay đầu không thấy gì, sét và đánh ngất là những lựa chọn trình diễn; chúng không thay thế đường giải đố hoặc tạo một NPC đòi đồ chặn lối thoát.

## 1 Đạo diễn nhịp

Một lượt có ba dạng nhịp: yên để đọc và suy luận, dấu hiệu nhỏ làm người chơi chú ý tới không gian, rồi cao trào ngắn. Sau cao trào có đoạn hồi phục rõ, ánh sáng ổn định và đủ điều khiển để tiếp tục mục tiêu. “Dồn dập” nằm trong một chuỗi vài giây có tăng tiến, không phải nhiều event không liên quan phát cùng lúc.

Ở bản đầu, đặt trần ba cao trào mạnh trong một lượt. E04, E06 và E07 là ứng viên, nhưng chỉ chạy nếu điều kiện phù hợp. Các event mức thấp có thể xen giữa. Tạm khóa cao trào mạnh kế tiếp khoảng sáu đến tám phút điều khiển thực sau một cao trào; không tính lúc ở balo. Nếu đã tới đoạn kết, bỏ event đang chờ. Thời gian này chỉ giới hạn scare, không giới hạn câu đố, item hay chìa khóa.

Thứ tự đề xuất: R00 yên tĩnh; P01 có dấu hiệu âm xa; sau P03 có E02; sau P04 có thể thấy E03 hoặc E04 trong lần trở lại; nhánh W05 là lựa chọn riêng; E07 chỉ xảy ra khi nhặt ảnh tùy chọn. Sau O05, đường về và mở giường không chạy thêm scare. Một event mạnh chưa đủ điều kiện không phải món nợ cần phát bù cuối game.

## 2 Các trạng thái chung

| Trạng thái | Ý nghĩa | Chuyển tiếp |
| --- | --- | --- |
| CHỜ | Chưa đạt mốc hoặc chưa vào vùng | Đủ tiến trình thì SẴN SÀNG |
| SẴN SÀNG | Có thể bắt đầu nhưng chưa chiếm điều khiển | Chờ hết đọc và có điều kiện an toàn |
| BÁO HIỆU | Âm hoặc ánh nhẹ đã bắt đầu | Sang cao trào hoặc kết thúc nhánh nhẹ |
| CAO TRÀO | Hình, tiếng và sáng phối hợp | Sang HỒI PHỤC |
| HỒI PHỤC | Trả điều khiển, ánh sáng ổn định | Sang HOÀN TẤT |
| HOÀN TẤT | Đã chạy hoặc đã bị bỏ theo luật | Không tự chạy lại trong lượt |

Mỗi event có một mã, mốc tiến trình, vùng phát, nguồn âm, đối tượng trước sau và cờ lưu. Chỉ một event trình diễn được quyền điều khiển camera hoặc L01 L05 tại một thời điểm. Âm thời tiết nền vẫn tồn tại nhưng các cú sấm lớn được điều phối, không đè lên cao trào khác.

Nhặt item chỉ đặt event vào SẴN SÀNG. Hệ thống chờ người chơi đóng chế độ xem, rời điểm tương tác và ở vùng đủ khoảng trống rồi mới báo hiệu. Nếu người chơi mở balo trước báo hiệu, tiếp tục chờ. Nếu họ rời hẳn vùng, event tùy chọn có thể bỏ; không dựng một con vật trước mặt để đuổi theo cho bằng được.

## 3 E01 Dấu hiệu đầu tiên

E01 mức thấp, sẵn sàng sau khi I00 đã vào balo và người chơi lần đầu đi ra R01. Một tiếng gỗ co ngắn từ phía phòng trực hoặc một tiếng gió ở ô kính G13 phát qua A03. Đèn không tắt, không ép quay đầu, không đổi đối tượng. Dấu hiệu này cho thấy không gian có nguồn âm nhưng vẫn cho người chơi tiếp tục tutorial.

Nếu người chơi quay lại R00, họ không thấy một clue mới được đặt lên bàn. Căn phòng giữ đúng cấu hình mở đầu. Event kết thúc ngay sau âm, lưu E01_DONE và không chạy mỗi lần qua cửa. Đây là nhịp nghỉ có chi tiết môi trường, không được trộn với sét gần hoặc tiếng gào.

## 4 E02 Vật rơi khi đang ở gian khác

E02 mức thấp, sẵn sàng khi nhặt O01. Điều kiện phát: người chơi đã rời R03, G14 và kệ G37 ngoài tầm nhìn, không đang đọc và không có event khác. G14 đổi từ trạng thái trên kệ sang dưới kệ sát tường. A06 gồm một tiếng chạm kệ, tiếng rơi và một đoạn lăn ngắn phát đúng tại R03.

Người chơi có thể đi theo tiếng và thấy lon, hoặc bỏ qua để làm P04. Lon không chứa item, không mở đường mới và không được nhặt. Nó chỉ chứng minh tiếng có hậu quả vật lý. Sổ mục tiêu vẫn chỉ dẫn kho R04, nên không nghe âm cũng không bị lạc khỏi đường chính.

Không mô phỏng lăn lon từ gian này qua gian khác. Dùng hai vị trí biên soạn sẵn và có thể thêm một đoạn lăn rất ngắn chỉ khi không nhìn thấy. Nếu Camera đang chụp được kệ, chưa đổi trạng thái. Nếu người chơi không rời R03 trong một thời gian dài, event tiếp tục chờ; không tắt đèn để buộc họ bỏ nhìn.

## 5 E03 Khung vừa rung

E03 mức thấp, sẵn sàng khi đã đọc I03 và trở lại R02. Khung W01 rung một lần rất nhẹ, cùng A07. Chỉ phát lúc đi lại, không trong chế độ xem tranh hoặc thao tác G20. Chuyển động không làm đổi bàn tay, vết sứt hoặc đáp án của tranh.

Khung dừng lại ở đúng vị trí ban đầu. Nếu người chơi quay về R02 bằng balo đang mở, chờ đóng balo rồi mới phát, hoặc bỏ nếu họ đã rời gian. Không có item rơi khỏi khung. Cảm giác bất an đến từ một vật quen thay đổi rất nhỏ sau khi hồ sơ chứng minh nó đã bị sửa.

Để tránh đoán nhầm khung có clue mặt sau, sổ không thêm một mục chưa giải khi E03 xảy ra. Người chơi vẫn có thể xem lại W01. Event chỉ rung một lần trong lượt, không rung ngẫu nhiên mỗi vài phút.

## 6 E04 Chim trên tượng

E04 là cao trào mạnh vừa, sẵn sàng sau P04 và khi người chơi đi qua hốc B01 tại R02. B02 là chim thật về hình dáng, vào được công trình qua khe hở gần hốc. Không cần xác định nó có yếu tố siêu nhiên. Tượng B01 không là vật chứa đáp án và không đổi mã dưới hiện vật D.

| Nhịp | Hình và ánh sáng | Âm | Điều kiện |
| --- | --- | --- | --- |
| Báo hiệu | Người chơi đi gần hốc; L01 giảm nhẹ | A08 cào và cánh khẽ từ hốc | Ngoài chế độ đọc |
| Khuất | Hốc ngoài tầm nhìn hoặc L05 tối hoàn toàn rất ngắn | Nền giảm vừa đủ | Không còn thấy B01 qua ánh L02 |
| Xuất hiện | B02 đã đứng trên B01; L01 sáng lại | Chưa phát sting | Có một nhịp để nhận ra chim |
| Giật | Chim giật hai cánh và nghiêng người | A09 khớp chuyển động | Không thêm chớp đèn liên tục |
| Hồi phục | Chim đứng hoặc rời một đoạn ngắn; hình rõ | Nền trở lại | Trả mọi mức sáng chuẩn |

Nhịp nhận ra nên kéo dài khoảng một đến hai giây trước cú cánh bật. Cú giật kéo ngắn hơn một giây. Tổng chuỗi không cần hơn khoảng sáu đến mười giây; đây là giá trị thử nghiệm, điều chỉnh theo tốc độ người chơi. Không dùng một khuôn mặt phủ kín màn hình không liên quan con chim.

Nếu người chơi không nhìn hốc sau khi chim xuất hiện, chim có thể đứng yên và event kết thúc mức nhẹ; không kéo camera cưỡng ép về nó. Nếu họ chụp được chim, ảnh được lưu bình thường trong Camera. Camera không kích hoạt một jumpscare thứ hai. Nếu chưa có điều kiện khuất, chỉ chạy A08 hoặc bỏ event, tuyệt đối không bật prefab ngay trước mắt.

Bản tiết kiệm animation chỉ cần chim đứng, quay đầu một chút và hai cánh quay trên bản lề. Bản tốt hơn thêm một đoạn nhảy khỏi bệ và chuyển trạng thái khi chim khuất. Không cần đường bay xuyên phòng, AI tránh vật cản hay tương tác bắt chim.

## 7 E05 Lời nhắc đừng quay đầu

E05 là tình huống lựa chọn trong nhánh phụ R01. Chỉ sẵn sàng khi đã xem W05, đạt P03 và còn ngân sách cao trào nếu người chơi chọn quay đầu. Người không đọc W05 hoặc không vào nhánh không bị phạt. Lời nhắn cho phép quay về khi chuông dừng, nên nó không tạo một quy tắc cấm quay đầu suốt game.

Khi đi vào đoạn thẳng cuối nhánh, phát ba nhịp A11 từ phía sau. Trong khoảng này, hệ thống theo hướng nhìn so với hướng đi vào đã ghi tại vùng thẳng. Nhìn lên, xuống hoặc lia nhẹ để đọc biển không tính là quay đầu. Chỉ khi góc nhìn đổi quá khoảng 100 độ về phía sau mới chuyển sang E06. Góc cuối được kiểm bằng chơi thử để không nhận nhầm thao tác bình thường.

Nếu đi thẳng tới biển cuối nhánh, chuông dừng ngay khi vào vùng biển. Lệnh cảnh báo kết thúc, người chơi có thể quay lại bình thường. Nếu chuông tự kết thúc trước khi tới biển, cũng được quay lại. Nếu người chơi lùi ra bằng cách đi lùi mà không quay đầu, event kết thúc khi ra khỏi vùng; không ép họ phải nhận scare.

Ở ngõ cụt, không khóa cửa hoặc cấm điều khiển. Biển ghi “KHU VỰC NIÊM PHONG — QUAY LẠI”. Phụ đề có thể báo “Chuông đã dừng”. Vùng kết thúc phải được kiểm trước vùng quay đầu trong cùng một frame, để người tới biển rồi quay lại không bị xử nhầm là vi phạm.

## 8 E06 Quay lại không thấy gì

E06 bắt đầu khi chủ động quay đầu trong đoạn cảnh báo của E05. Người chơi nhìn lại và hành lang trống. Đèn vẫn đủ thấy chỗ vừa đi qua; không đặt NPC ngay tại frame quay đầu. Sau một nhịp ngắn, một tiếng kính nhẹ phía trên làm góc nhìn nâng về ô kính G13, rồi sét và sấm mở cao trào.

Phần nâng góc nhìn là chuyển động trình diễn ngắn khoảng nửa giây, không lật camera 180 độ hoặc đẩy người chơi vào tường. Có thiết lập giảm chuyển động camera; khi bật, chỉ dùng âm phía trên và ánh sét trong phần nhìn hiện tại. Hai biến thể dưới dùng chung báo hiệu, chỉ chọn một cho bản chơi.

### E06A Bóng người và cú đánh ngất

Đây là biến thể sát ví dụ người chơi đề xuất. Sau khi nhìn lên và L04 sáng rồi hạ xuống, hình người B03 cầm gậy B04 xuất hiện ở khoảng gần trước hướng nhìn hạ xuống. B03 được giấu và chuyển trạng thái tại góc gấp khi ngoài tầm nhìn. Mặt nhân vật không cần nhìn rõ; dùng một pose có bóng và một chuyển động tay gậy ngắn, không dùng AI đi bộ hoặc rượt đuổi.

Gậy vụt một nhịp cùng A12, màn hình tối L05 tại điểm va chạm, rồi âm lùi vào A13. Người chơi ngất, không chết. Cảnh tỉnh lại đặt người chơi tại một điểm trống ở đoạn hành lang chính gần đầu nhánh, hướng về biển gian. Chuyển chỗ được thực hiện trong blackout; không phải animation NPC kéo người xuyên cả hành lang.

Giữ nguyên toàn bộ đồ, hồ sơ, đĩa và ngăn đã mở. Không đặt vật mới vào balo hoặc lấy mất dấu. Sau khoảng tối ngắn, sổ có thể mở ngay và mục tiêu chính vẫn như trước. Tổng chuỗi nên thử ở khoảng tám đến mười hai giây, với đoạn tỉnh lại gọn. Không bắt người chơi đi lại từ phòng R00 hoặc làm lại P03.

Hình người chỉ là một lần xuất hiện không xác định trong trải nghiệm của nhân vật; không xác nhận là người sống đang canh giữ chìa khóa. Người này không xuất hiện để đòi item, không đuổi theo và không cản đường kết thúc. Nếu muốn giải thích rõ danh tính về sau, cần một nhánh truyện bổ sung riêng; bản này giữ vai trò của cảnh ở mức hù dọa và choáng.

### E06B Biến thể ít animation

Nếu chưa làm được model và cú gậy thuyết phục, dùng bóng cầm gậy chỉ lóe ở mép nhìn sau sấm, một tiếng vụt từ phía khuất và blackout. Không cho thấy thân nhân vật hay điểm tiếp xúc. Tỉnh lại và giữ tiến trình giống biến thể A. Phải ghi chọn B trong danh sách sản xuất để không vô tình có cả bóng lẫn một NPC đánh lần nữa.

Biến thể B vẫn cần timing âm, sét và tối, nhưng giảm công dựng nhân vật. Nếu không muốn cảnh bị đánh ở bản đầu, có thể tắt E06 và chỉ giữ hành lang trống, sấm rồi hồi phục; việc này không thay flow hoặc yêu cầu vật phẩm. Cấu hình event được chọn trước lượt chơi, không ngẫu nhiên đổi giữa các lần tải.

### Xử lý bỏ cảnh và tải game

Khi vào E06, lưu một checkpoint nguyên tử gồm tiến trình, vị trí hồi phục và cờ E06 đang xử lý. Nếu tải trong blackout, đưa tới điểm hồi phục, đánh dấu event hoàn tất và trả ánh sáng chuẩn. Không lặp cú đánh mỗi lần tải. Khi chọn bỏ cảnh, chuyển thẳng sang hồi phục và vẫn giữ mọi đồ.

Không tính damage hoặc trừ máu cho cú đánh này. Nếu người chơi chưa đủ điều kiện vùng an toàn, bỏ nhánh cao trào và cho chuông dừng; không đánh ngất trên cầu thang, trong góc kẹt hoặc khi đang mở hồ sơ. Từ điểm tỉnh lại phải có đường về tất cả gian đang dùng. E06 chỉ chạy một lần trong lượt.

## 9 E07 Scare sau khi nhặt ảnh

E07 là event nhặt đồ, dùng F05 tùy chọn tại bàn đọc R04. Nhặt F05 đặt event vào sẵn sàng; đóng ảnh và đọc I05 không bị ngắt. Khi người chơi rời bàn qua đoạn nối có ô kính R01, A16 là một tiếng gõ mạnh và kính rung, cùng một đợt ánh L04 ngắn từ bên ngoài.

Không xuất hiện một item mới cần nhặt và không đổi nội dung F05. Kính vẫn nguyên, không cần mô phỏng vỡ. Sau tiếng gõ, âm mưa trở lại để có khoảng nghỉ. Một silhouette mờ ngoài ô kính có thể là phiên bản nâng cao, dùng một mặt phẳng hoặc model tĩnh đặt ngoài kính khi khuất; bản đầu không cần nó.

Nếu vừa có E04 hoặc E06, E07 bị hoãn hoặc bỏ. Nếu người chơi lấy F05 rất muộn sau O05, chỉ phát tiếng giấy A14, không chạy scare trên đường về. Nếu họ quay lại bàn nhiều lần, không tái kích hoạt. Người bỏ F05 không bỏ lỡ lời giải, chìa khóa hoặc một đoạn truyện bắt buộc.

## 10 Bảng điều phối và ngân sách

| Event | Trigger | Mức | Chi phí chính | Không phát khi |
| --- | --- | --- | --- | --- |
| E01 | Rời R00 lần đầu | Thấp | Một nguồn âm | Đọc I00 |
| E02 | O01 đã nhặt, rời R03 | Thấp | Hai trạng thái lon, âm 3D | Kệ còn trong tầm nhìn |
| E03 | I03 đã đọc, trở lại R02 | Thấp | Khung quay nhẹ | Xem tranh hoặc giải đĩa |
| E04 | Sau P04, đi gần hốc | Cao | Chim tĩnh, cánh, ánh, âm | Hốc chưa khuất, đang đọc |
| E05 | Đọc W05, vào nhánh sau P03 | Lựa chọn | Vùng nhìn và âm chuông | Không còn lượt cho E06 |
| E06 | Quay đầu trong cảnh báo | Cao | Camera, sét, pose gậy hoặc bóng | Tới biển, chuông dừng, vùng nguy hiểm |
| E07 | Nhặt F05 rồi rời bàn | Cao vừa | Kính rung, gõ, ánh sét | Đang đọc, vừa scare, đã có chìa khóa |

Ưu tiên mốc truyện và lựa chọn đang diễn ra hơn một event đang chờ. E05 E06 là một chuỗi và chỉ chiếm một lượt cao trào. Không phát E02 trong blackout E06 hoặc A10 đúng lúc chốt câu đố thành công. Event thấp cũng có khoảng tách ngắn để tiếng có thể nhận nguồn, nhưng không cần bộ đếm bắt người chơi đợi.

## 11 Luật thay đổi đối tượng ngoài tầm nhìn

“Ngoài tầm nhìn” phải gồm cả góc nhìn hiện tại và lần chụp Camera đang xử lý. Đối tượng sau không cắt vào đường đi, không trùng vị trí nguồn bắt buộc và không có collider đẩy người chơi. Với chim, bóng người và lon, chuẩn bị hai trạng thái cụ thể rồi chuyển khi được che; không chỉ đặt object tại một khoảng cách ngẫu nhiên phía sau lưng.

Tối màn hình là một điều kiện che hợp lệ nếu màn hình thật sự tối trong hiệu ứng; đèn pin tắt riêng lẻ có thể không đủ vì ánh trời vẫn còn. Nếu người chơi quay camera bất ngờ trong khi chờ chuyển trạng thái, kiểm lại trước khi đổi. Nếu không thể làm an toàn, bỏ phần xuất hiện và chỉ giữ nhịp âm nhẹ.

Vật mới không tự trở thành clue. Chim, lon và bóng không có ô thiếu trong sổ. Chỉ những nguồn đã liệt kê trong tài liệu clues tham gia điều kiện hộp. Event không xóa, sửa chữ hoặc di chuyển một nguồn bắt buộc từ chỗ cũ sang một chỗ không có chỉ dẫn.

## 12 Điều khiển và thiết lập trải nghiệm

Cho chỉnh cường độ scare, giảm chớp, giảm rung và giảm chuyển động camera. Khi giảm hiệu ứng, giữ thông tin từ môi trường, trạng thái vật sau event và tiến trình chính. E06 có thể chuyển sang biến thể không cú đánh trong cấu hình này; không coi người chơi chọn nhẹ là đã thất bại hoặc mất một phần kết thúc.

Không hiện một câu “đừng quay đầu” rồi liên tục cưỡng ép camera quay lại. Góc nhìn tự nâng ở E06 chỉ diễn ra sau lựa chọn quay đầu và được xác định là đoạn trình diễn. Khi trả điều khiển, xóa mọi khóa input, FOV tạm, độ mờ và độ sáng tạm. Thoát menu và tải game cũng dùng cùng bước khôi phục.

## 13 Ma trận kiểm tra logic

| Tình huống | Kết quả phải có |
| --- | --- |
| Đọc giấy lúc event sẵn sàng | Chờ, không che chữ và không tắt đèn |
| Vừa tới biển rồi quay đầu | E05 kết thúc an toàn, không chuyển E06 |
| Đi lùi ra khỏi nhánh | Bỏ qua scare, đường chính tiếp tục |
| Quay đầu trước khi nghe chuông | Không tính vi phạm |
| Quay đầu nhiều lần sau E06 | Không đánh ngất lần nữa |
| Tắt âm hoặc không đọc W05 | Không cần event để lấy chìa khóa |
| Chụp hốc hoặc kệ đúng lúc chuyển | Hoãn chuyển; không lộ prefab bật trước mắt |
| Tải trong ngất hoặc chớp | Tỉnh ở điểm hợp lệ, đèn chuẩn, đồ giữ nguyên |
| Lấy O05 khi event còn chờ | Hủy scare đang chờ, đường về ổn định |
| Đi nhanh bỏ qua vùng chim | Event được bỏ, không đuổi theo người chơi |
| Hai trigger cùng đủ điều kiện | Một event chạy, event kia hoãn hoặc bỏ |
| Chọn bỏ cảnh hoặc giảm hiệu ứng | Cùng tiến trình, không mất phần kết thúc |

Chơi thử riêng từng event trước khi ghép. Ghi thời điểm âm, sáng, đổi trạng thái và trả điều khiển để tìm lỗi không đồng bộ. Sau đó chạy một lượt theo đường chính không lấy đồ tùy chọn, một lượt khám phá mọi nhánh và một lượt cố tình quay đầu. Mỗi lượt phải lấy được O05, mở giường và kết thúc; khác nhau chỉ ở nhịp trải nghiệm và hồ sơ bổ sung.
