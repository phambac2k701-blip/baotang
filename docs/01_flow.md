# Bảo tàng và chiếc chìa khóa

Tài liệu flow · Thiết kế phiên bản 3 · 12 tháng 10 năm 2026

Người chơi tỉnh dậy trong phòng trực của một bảo tàng bỏ hoang, tìm chiếc chìa khóa được vẽ trên tờ hướng dẫn rồi trở lại mở giường để xuống lối thoát. Tài liệu này chốt diễn biến, đáp án, điều kiện tiến triển và cách xử lý những người tìm được vị trí lối ra quá sớm. Mã clues, phòng và event được dùng thống nhất trong bốn tài liệu còn lại.

## 1 Trải nghiệm và phạm vi

Game khám phá ở góc nhìn thứ nhất, có trình tự truyện xác định trong một bảo tàng nhỏ. Không gian gồm phòng xuất phát, hành lang nối và các gian có chức năng riêng; người chơi được đi lại, nhưng việc mở hồ sơ và lấy chìa khóa tuân theo chuỗi phụ thuộc. Các hiện vật giữ màu đỏ gạch, xanh ngọc, vàng men và xanh lam, nổi lên dưới đèn pin trong một công trình tối, cũ và yên tĩnh.

Thao tác chính là nhìn kỹ, xoay hiện vật tại chỗ, lật ảnh hoặc giấy trong chế độ xem, mở ngăn kéo, nhấn cơ cấu cố định và nhặt đồ vào balo. Ảnh là tài liệu để đối chiếu với đồ vật đã tồn tại trong không gian. Không có việc biến ảnh 2D thành không gian 3D, di chuyển tủ lớn hoặc mô phỏng đặt đồ tự do.

Mục tiêu thiết kế sau khi bổ sung cụm cửa niêm phong là khoảng 120 đến 150 phút cho lượt chơi đầu với mức hỗ trợ mặc định. Đây là dự kiến cần kiểm chứng bằng chơi thử, không phải thời lượng đã đo. Người hiểu đáp án hoặc chơi lại có thể hoàn thành nhanh hơn; game không khóa tiến trình bằng đồng hồ để buộc đủ 90 phút.

## 2 Phòng xuất phát

R00 chỉ có giường khóa, bàn với một tờ hướng dẫn I00, đèn pin người chơi đang giữ và phần kiến trúc cần thiết. Không đặt thêm ảnh, giấy, món đồ nhặt được hoặc câu đố bí mật tại đây. Lối mở sang hành lang R01 nhìn thấy được, đi qua bình thường và không phải cửa thoát khỏi bảo tàng.

I00 là tương tác đầu tiên được giới thiệu. Khi người chơi đóng chế độ đọc lần đầu, giấy tự vào balo. Phía trên trang có vài câu hướng dẫn thao tác; cuối trang có hình chiếc chìa khóa và đúng dòng “nó ở đâu...”. Hình không chỉ vị trí giấu chìa khóa. Nội dung và hình dáng cụ thể được chốt trong tài liệu clues.

Giường che một nắp lối xuống ngay bên dưới phần chân hoặc sát cạnh giường. Mép khu vực này có thể được người tinh ý phát hiện sớm. Tương tác giường lúc chưa có O05 chỉ hiện “Locked” và hình khóa nhỏ. Không có nút “Open”, không có lời yêu cầu chờ đến một thời điểm và không cho thử lật giường bằng spam tương tác.

## 3 Sự thật của bảo tàng

Ba hiện vật được giới thiệu là bản gốc thực ra là bản sao. Một bộ ảnh bàn giao và sổ kiểm kê chứng minh các bản gốc đã được chuyển qua kho phục chế rồi ra tuyến vận chuyển nội bộ. Các khung trưng bày đã đổi chi tiết để che dấu sự không khớp giữa ảnh lưu trữ và hiện vật hiện tại.

Người trực cuối cùng phát hiện việc tráo đồ. Họ để lại tờ hướng dẫn và giữ chìa khóa lối kỹ thuật trong hộp kiểm kê, một thiết bị vốn yêu cầu ba dấu xác nhận. Họ muốn người tìm đường ra đồng thời mang được bằng chứng khỏi công trình. Tờ hướng dẫn là dấu vết cũ của người này; game không cần một NPC còn sống đứng chặn lối.

Bí mật thứ hai là khu vực người chơi đang đi thuộc tầng hai. Cửa phòng trực nối vào khu trưng bày, còn đường xuống tầng dưới được che bởi giường. Sơ đồ F04 và giấy bảo trì I04 xác nhận điều đó trước đoạn kết. Danh tính người chơi có thể để mở; ảnh tùy chọn F06 và giấy I05 giải thích người để lại hướng dẫn, không buộc một cú lật rằng người chơi chính là họ.

## 4 Vòng lặp gameplay

Mỗi cụm bắt đầu bằng một câu hỏi cụ thể, chẳng hạn người trong tranh ban đầu cầm gì, ngăn nào lưu hồ sơ trả từ xưởng, hoặc ký hiệu R dưới đáy nghĩa là gì. Người chơi tìm nguồn thông tin, xem hoặc nhặt nguồn đó, đối chiếu với một nguồn khác rồi thao tác cơ cấu liên quan. Cơ cấu phản hồi bằng chuyển động, tiếng chốt và một kết quả mới nhìn thấy được.

Kết quả tạo lý do quay lại một đồ vật quen thuộc với cách hiểu mới. Lượt đầu xem đáy hiện vật để đọc hình học. Lượt sau đọc số và chữ R tại chính đáy đó để kiểm chứng bản sao. Việc quay lại có mục đích và một câu hỏi mới, thay vì dò lại toàn bộ phòng sau mỗi sự kiện.

Balo giữ ảnh, giấy và vật phẩm đã nhặt. Sổ manh mối lưu những phần quan trọng đã quan sát trên ảnh treo tường và hiện vật cố định. Máy ảnh tùy chọn O04 tạo ảnh cá nhân trong album Camera; ảnh cá nhân giúp ghi nhớ nhưng không được dùng để nhận diện đáp án tự động hoặc thay thế vật phẩm bắt buộc.

## 5 Trình tự chính và đáp án

| Cụm | Câu hỏi và thao tác | Kết quả | Dự kiến phút |
| --- | --- | --- | --- |
| P00 | Đọc I00, thử giường khóa, ra R01 | Hiểu mục tiêu chiếc chìa khóa | 5 đến 8 |
| P01 | Mở ngăn kéo thấp ở R01 bằng một tay nắm rõ ràng; lấy F01 và I01 | Học nhặt, lật ảnh, so sánh | 7 đến 10 |
| P02 | So F01 với W01, dùng quy tắc W02 và I01; xoay ba đĩa dưới khung | Đáp án LÁ, CHÉN, CHUÔNG; ngăn mở chứa F02 | 13 đến 17 |
| E08 | Lần đầu vào R03, cửa đóng khóa; dựng lại hồ sơ kiểm định bằng các nguồn trong phòng | Mở cửa bằng 3581 và nhặt I12 | 20 đến 35 |
| P03 | So F02 với đáy D01, D02, D03; xoay ba đĩa ở bàn R03 | Đáp án TAM GIÁC, TRÒN, VUÔNG; lấy I02 và O01 | 13 đến 17 |
| P04 | Đọc I02 và bảng W03; chọn đúng ngăn kho R04 | Ngăn B2 mở; lấy I03, F03, O02 | 12 đến 15 |
| P05 | Đọc I03, so F03 với các chữ R dưới D01 đến D03 | Xác nhận cả ba hiện vật hiện tại là bản sao | 12 đến 16 |
| P06 | Dùng O02 trên chốt bảng kỹ thuật R05; mở cánh bản lề | Lấy F04, I04, O03; hiểu tầng hai và đường dưới giường | 10 đến 13 |
| P07 | Đối chiếu ba hồ sơ tại hộp R05 và áp ba dấu | Hộp mở; nhặt chìa khóa O05 | 12 đến 16 |
| P08 | Quay lại R00, chọn Open trên giường và đi xuống | Lối kỹ thuật dẫn ra ngoài; kết thúc | 6 đến 8 |

Các khoảng trên, gồm E08, cộng lại thành 110 đến 155 phút tùy nhịp đọc và khám phá. Khi chơi thử, mục tiêu là nhóm trung vị đạt 120 đến 150 phút bằng việc điều chỉnh độ rõ và chiều sâu đối chiếu của câu đố. Nếu prototype ngắn hơn, cần thêm nội dung suy luận có nghĩa trước khi chốt thời lượng. Không tăng số tổ hợp vô nghĩa hay thời gian tắt đèn để kéo dài lượt chơi.

### P02 Tranh đã bị sửa

F01 cho thấy ba người từ trái sang phải: người mẹ cầm lá, người cha cầm chén, đứa trẻ cầm chuông. W01 hiện tại đổi thành chén, chuông, lá. W02 nói lấy vật trong ảnh lưu trữ, theo thứ tự người từ trái sang phải; I01 nhắc xác định khung bằng vết sứt góc dưới bên phải. Người chơi dùng chính bức ảnh F01 làm đáp án, không lấy đồ vật trong W01 đã bị sửa.

Ba đĩa có cùng ba biểu tượng rõ ràng. Khi chọn LÁ, CHÉN, CHUÔNG và nhấn tay gạt, ngăn dưới khung mở. F02 ở trong ngăn. Sai tổ hợp chỉ tạo tiếng chốt không ăn, không đóng lại đường đi hoặc mất vật phẩm. Một gợi ý sau nhiều lần thử nhắc xem lại tay người trong ảnh lưu trữ.

### E08 Một lần bị nhốt ở gian phục chế

Chỉ R03 có cửa tự đóng và khóa một lần khi người chơi đi hẳn vào. Tất cả nguồn mở cửa nằm trong R03 và tiếp cận được ngay, kể cả khi người chơi chưa lấy F02 ngoài phòng. P03 vẫn là cơ cấu ngăn bàn riêng; hoàn thành nó chưa tự mở cửa. Có thể giải hai việc theo thứ tự tùy chọn nếu đã có nguồn của P03.

Cửa yêu cầu khôi phục thứ tự kiểm định cuối của các bản gốc trước báo động. Người chơi đối chiếu ảnh khai trương F07, bốn hiện vật D01 đến D04, phiếu sửa khóa I08, bộ sáu ảnh F08, phiếu lệch giờ I09, biên bản đáng ngờ I10, quy trình W07, nhật ký báo động I11 và bảng mã W08. Đây là chín nhóm nguồn trong một câu đố địa phương; không đưa cùng công thức vào những gian khác.

F07 ghi năm 2012 và cho thấy chén gốc sứt chân. I09 cho biết máy A nhanh 7 phút, máy B chậm 5 phút. Sau hiệu chỉnh, ảnh hợp lệ trước báo động 21:20 có thứ tự chén 21:12, lá 21:14, mặt nạ 21:16, chuông 21:18. Ảnh chén 21:17 không có vết sứt nên là bản sao; ảnh mặt nạ 21:22 nằm sau báo động. I10 gọi chén 21:17 là bản gốc, vì vậy dòng đó đã bị sửa.

Mặt dưới bốn vật lần lượt có trăng, sóng, sao, cây. I08 nói khóa giữ chuẩn khi lắp đặt; F07 xác định năm 2012. Cột 2012 trên W08 đổi bốn dấu thành 3, 5, 8, 1. Đặt 3581 rồi gạt chốt sẽ mở khóa cửa và nhả khay I12. Người chơi cần nhặt I12 để hoàn tất hồ sơ hiện vật ở đoạn cuối. Không có chìa khóa thứ hai cho phòng này.

Cửa nhận đáp án đúng ngay, không kiểm một bộ đếm đọc hoặc đồng hồ. Người biết lời giải có thể giải nhanh. Giải sai giữ nguyên đồ, góc vật và vòng số. Sau khi giải, cửa giữ trạng thái mở khóa, không nhốt lần nữa khi quay lại. Cảnh đóng cửa, tiếng gõ, vật rơi, bóng dưới khe và khoảng nghỉ được mô tả theo từng trạng thái trong file event. Chúng không che nội dung bằng chứng.

### P03 Xem mặt khuất của hiện vật

F02 là ảnh bàn phục chế: chén bên trái mang số 1, lá ở giữa mang số 2, chuông bên phải mang số 3. Ba hiện vật D01, D02, D03 tại R03 xoay trên đế cố định. Người chơi đưa mặt đáy vào vùng nhìn để thấy lần lượt tam giác, tròn và vuông. Hình trên ảnh không chứa sẵn toàn bộ đáp án; ảnh cho thứ tự, vật 3D cho hình học.

Mỗi đáy cũng có chữ R và số tương ứng 08, 17, 23, nhưng ý nghĩa chưa được giải thích. Sổ manh mối giữ cả phần đáy đã xem để người chơi không cần nhớ bằng trí nhớ. Đặt ba đĩa trên bàn theo TAM GIÁC, TRÒN, VUÔNG rồi gạt chốt để lấy I02 và dấu O01. Dấu này đại diện hồ sơ hiện vật, nhưng hồ sơ chưa hoàn tất cho đến P05.

### P04 Kho có quy tắc

W03 định nghĩa hàng A là tranh, hàng B là hiện vật, hàng C là giấy; cột 1 là trưng bày, cột 2 là phục chế, cột 3 là vận chuyển. I02 mô tả hồ sơ của hiện vật trả từ xưởng phục chế. Giao của hai thông tin là B2. Những ngăn khác có giấy kê hoặc vật trang trí không thể nhặt, không chứa một manh mối bắt buộc ngẫu nhiên.

Chỉ ngăn B2 có cơ cấu cho mở bằng O01. O01 vẫn ở balo sau thao tác. Nếu thử dấu ở một ngăn khác, cơ cấu nhả ra và sổ nhắc rằng loại đồ và trạng thái phải cùng khớp. Trong B2 có ba vật cần lấy riêng: I03, F03 và O02; balo báo còn vật trong ngăn nếu người chơi mới lấy một phần.

### P05 Chứng minh việc tráo đồ

I12 là phiếu vận chuyển gốc lấy từ khay cửa R03, dùng kiểm chứng dòng chén bị sửa trong I10. I03 định nghĩa B là bản gốc, R là bản sao; mã 08 thuộc chén, 17 thuộc lá, 23 thuộc chuông. F03 cho thấy thùng bàn giao chứa B08, B17 và B23. Đáy các hiện vật trong phòng ghi R08, R17 và R23. Người chơi chọn ba dòng đối chiếu trong sổ để xác nhận từng cặp. Sổ chỉ cho xác nhận dòng có đủ nguồn ảnh, giấy và quan sát đáy.

Hồ sơ hiện vật hoàn tất khi ba dòng đều kết luận “Bản sao”. Không cần người chơi đoán chất liệu nhờ độ bóng, đọc nét chữ cực nhỏ hoặc tự hiểu một mã chưa từng được giải thích. Khi thiếu một nguồn, dòng đó nêu tên nguồn cần xem lại. Một tiếng cơ cấu nhỏ A05 từ R03 xác nhận đế đã nhả một chốt, tạo cảm giác việc kiểm chứng có ảnh hưởng đến không gian.

### P06 Đường đi và tầng thật

O02 khớp với chốt gắn trên bảng kỹ thuật ở R05. Người chơi nhấn sử dụng dấu, cánh bảng mở trên một bản lề và lộ bộ tài liệu. F04 là mặt cắt công trình, còn I04 gọi tên phòng trực, giường che lối xuống và ba hồ sơ của hộp chìa khóa. Đây là giai đoạn giải đáp vị trí thoát, trước lúc nhận chìa khóa.

Hồ sơ đường đi ghi “Kho phục chế”, dựa vào I02, W03, I03 và F03: đồ được đưa từ xưởng vào kho trước khi đi qua tuyến vận chuyển. Hồ sơ tầng ghi “Tầng hai”, dựa vào F04 và I04. O03 là dấu của tuyến kỹ thuật. Các dấu chỉ được áp lên điểm tương tác cố định; không yêu cầu kéo chúng ra khỏi balo rồi đặt chính xác trong không gian.

### P07 Hộp chìa khóa

Mặt hộp chia ba hàng có tên “HIỆN VẬT”, “ĐƯỜNG ĐI”, “TẦNG”. Từng hàng cho chọn một kết luận và áp dấu tương ứng O01, O02, O03. Đáp án cuối là BẢN SAO, KHO PHỤC CHẾ, TẦNG HAI. Hộp ghi rõ “Đối chiếu đủ hồ sơ rồi áp dấu. Các dấu không giữ lại trong hộp.”

Ba câu hỏi hiện nguyên văn khi xem hộp: “Hiện vật đang trưng bày là gì?” với lựa chọn Bản gốc hoặc Bản sao; “Đồ bàn giao đi qua đâu sau xưởng?” với Trưng bày, Kho phục chế hoặc Phòng trực; “Phòng trực ở tầng nào?” với Tầng một, Tầng hai hoặc Tầng ba. Câu hỏi đường đi chỉ rõ mốc sau xưởng để không có hai đáp án hợp lý giữa kho và tuyến vận chuyển.

Điều kiện mở là đủ 19 nguồn bắt buộc trong danh mục, ba hồ sơ đúng và đủ ba dấu. Mỗi hàng chỉ nhận xác nhận khi các nguồn của nó đã được ghi nhận; giao diện nói rõ nguồn thiếu trước khi cho chốt hàng. Không để người chơi giải đúng toàn bộ rồi gặp một lớp khóa vô hình. Ba hàng nhớ trạng thái xác nhận qua lưu game.

Chìa khóa O05 đã nằm trong hộp từ đầu; mở hộp chỉ làm nó tiếp cận được, không sinh ra chiếc chìa khóa bằng phép biến đổi. Nhặt O05 ghi trạng thái KEY_OWNED. Hộp không tự nhặt chìa khóa thay người chơi, và thông báo mục tiêu nhắc “Mang chìa khóa về nơi tỉnh dậy”.

### P08 Kết thúc

Khi trở về R00 và có O05, tương tác giường hiện đúng “Open”. Người chơi chủ động nhấn; giường mở một phần có bản lề, rồi nắp lối xuống xuất hiện. Hình thức cánh giường có thể chọn sau, nhưng điểm tương tác, không gian trống khi mở và lối đi phải được kiểm tra trước khi làm model cuối.

Đoạn xuống dùng vài bậc hoặc chuyển cảnh ngắn, sau đó người chơi đi qua đoạn kỹ thuật ở tầng dưới để thấy ánh sáng ngoài trời. Không thêm một khóa mới hoặc nhân vật chặn lối. Game kết thúc sau khi ra khỏi công trình; ảnh và giấy đã thu thập xuất hiện trong màn hình hồ sơ để nhấn mạnh người chơi mang được bằng chứng theo.

## 6 Danh sách điều kiện bắt buộc

| Nhóm | Mã phải có | Cách ghi nhận |
| --- | --- | --- |
| Giấy | I00, I01, I02, I03, I04, I12 | Đọc I00 lần đầu tự cất; các giấy khác nhặt vào balo |
| Ảnh mang theo | F01, F02, F03, F04 | Nhặt bản ảnh cố định |
| Tường | W01, W02, W03 | Mở chế độ xem toàn hình hoặc chữ; tự ghi vào sổ |
| Hiện vật | D01, D02, D03 | Xem rõ cả hình học và mã trên đáy; vùng nhận diện rộng |
| Dấu | O01, O02, O03 | Nhặt vào balo; sử dụng nhiều lần |

Có 19 nguồn bắt buộc trước chìa khóa. I12 làm cụm E08 nối vào hồ sơ chính; F07, F08, I08 đến I11, W07, W08 và D04 phục vụ lời giải cửa nhưng không tạo thêm hạn ngạch nhặt ở hộp cuối. O05 là phần thưởng bắt buộc cho đoạn kết. O04, F05, F06, I05, I06, I07, W04, W05, W06 và các ảnh chụp Camera đều không nằm trong điều kiện mở hộp. Đồ trang trí và nét nhiễu không có cờ tiến trình.

## 7 Xử lý phát hiện sớm và các đường tắt

Tìm thấy đường dưới giường sớm là một khám phá được công nhận. Sổ ghi “Có một cơ cấu khóa dưới giường”; mục tiêu chiếc chìa khóa vẫn giữ nguyên. Người chơi có thể trở lại bất cứ lúc nào. Mép nắp không có tương tác mở độc lập và không có khe để rơi xuyên xuống.

Nếu đoán đúng tổ hợp của P02 hoặc P03 sớm, cơ cấu yêu cầu bộ nguồn của câu đố đã ghi nhận và báo nguồn còn thiếu ngay tại bảng. Khi đã có nguồn, giải nhanh được chấp nhận. Đây là điều kiện thu thập bằng chứng của game, không phải một bộ đếm thời gian. Chỉ áp dụng cho nguồn đã liệt kê là bắt buộc, không yêu cầu khám phá 100 phần trăm trang trí.

Nếu đến R05 sớm, người chơi thấy hộp và ba ô hồ sơ trống. O02 mở bảng kỹ thuật, nên F04, I04 và O03 chưa lấy được trước khi tìm đúng B2. Nếu đã đoán rằng đang ở tầng hai hoặc chụp được sơ đồ qua khe, ảnh tự chụp không thay thế F04 và I04 cần mang theo.

Máy ảnh, ảnh tùy chọn và các cảnh hù không được giữ chìa khóa hoặc nguồn bắt buộc. E08 là một cụm gameplay bắt buộc riêng: cửa R03 tạm khóa và I12 nằm trong khay mở bằng câu đố. Mọi dữ liệu cần cho E08 đều ở trong phòng, không phụ thuộc cảnh hù, Camera hoặc đồ ngoài phòng. Không tồn tại NPC giết người, đánh mất đồ do thử sai hay yêu cầu bắt đầu lại lượt chơi.

## 8 Hỗ trợ khi bí và giữ nhịp

Sổ hiển thị ba hồ sơ và nguồn đang thiếu trong hồ sơ đang làm. Khi bị nhốt trong E08, mục tiêu cục bộ mở cửa được ưu tiên; giải xong trả về mục tiêu chính. Có thể đối chiếu nhiều tài liệu đồng thời, không chỉ hai thẻ. Một nút gợi ý có ba mức: chỉ loại nguồn cần xem, chỉ chi tiết liên quan, rồi giải thích thao tác hoặc đáp án. Gợi ý không tự bật lời giải sau một thời gian cố định; người chơi chủ động dùng. Sau ba lần thử sai cùng một cơ cấu, game có thể nhắc rằng nút gợi ý đang có sẵn.

Clue mới có vùng xem lớn, chữ tương phản và bản chép nội dung để đọc trong balo. Người chơi có thể đặt hai ảnh hoặc giấy cạnh nhau trong giao diện. Các chi tiết quyết định đều được đánh dấu trong sổ sau khi kiểm chứng đúng, nhưng không bị khoanh sẵn trên texture để lộ đáp án ngay từ đầu.

Event được đặt giữa hai cụm suy luận hoặc lúc di chuyển. Khi đọc giấy hay giải cơ cấu, hệ thống không tắt đèn và không phát một cú giật lớn che thông tin. Một nguồn âm từ gian khác có thể gợi quay lại hiện vật, nhưng sổ luôn có cách chỉ đường thay thế. Tài liệu event quy định rõ lượt quay đầu và ngõ cụt để bảo đảm không tạo kẹt. Nhánh scare đánh ngất là tùy chọn, không chết và giữ tiến trình; sau khi có chìa khóa không chạy thêm scare trên đường về. Sáu cụm lớn gồm E08 cửa niêm phong, E04 chim, E05 E06 lựa chọn quay đầu, E09 truy nguồn tiếng gõ, E10 Camera và bóng trong hốc, E11 bản ghi âm. Chỉ E08 đóng khóa một phòng; những cụm khác không bắt giải lại cùng dạng câu đố.

## 9 Trạng thái lưu và tiêu chí chơi thử

Lưu cả trạng thái cửa E08, bốn vòng số, khay I12 và các nguồn của câu đố địa phương. Lưu các nguồn đã nhặt, nguồn đã quan sát, góc xoay hiện vật, đĩa đang chọn, ngăn đã mở, kết luận hồ sơ, dấu đã áp, key_owned, bed_open và các event đã hoàn tất. Các item không bị tiêu hao. Tải game không đóng ngăn chứa vật chưa nhặt, không tạo thêm chìa khóa và không chạy lại một jumpscare đã xem.

Trước khi chốt bản chơi, thử vào R03 trước F02, bỏ âm, không nhặt Camera, đoán đúng 3581 ngay, lấy thiếu I12, tải trong lúc cửa đang đóng và quay lại R03 sau khi giải. Tiếp tục thử các tình huống: đi thẳng tới giường; tới hộp trước mọi câu đố; đoán đúng tổ hợp nhưng thiếu một nguồn; lấy thiếu một món trong B2; bỏ máy ảnh; chụp rồi xóa toàn bộ ảnh cá nhân; bỏ mọi nội dung tùy chọn; dùng gợi ý cuối; lưu trước và sau khi lấy chìa khóa; tải lại khi giường đang mở. Mỗi trường hợp phải kết thúc được và nêu rõ bước còn thiếu.

Đo riêng thời gian đọc, suy luận, di chuyển và đi lạc của lượt chơi đầu. Nếu thời gian tăng do người chơi không nhìn ra điểm tương tác, sửa hình hoặc bố trí. Nếu thời gian thấp vì câu đố chỉ sao chép một dòng sang ổ khóa, tăng một bước đối chiếu có nghĩa giữa hai nguồn. Chỉ số cần theo dõi là hoàn thành không trợ giúp, số lần mở gợi ý và điểm người chơi bắt đầu mất mục tiêu; không lấy tổng phút làm thước đo duy nhất.
