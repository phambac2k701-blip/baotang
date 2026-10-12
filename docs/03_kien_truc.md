# Kiến trúc và đối tượng trong bảo tàng

Tài liệu kiến trúc · Thiết kế phiên bản 3 · 12 tháng 10 năm 2026

Bảo tàng được chia theo chức năng của câu đố và nhịp khám phá. Tài liệu này xác định từng gian, đường nối, vật thể và chuyển động cần làm; chưa chốt tọa độ, kích thước cuối hay hình dáng cánh giường. Các vị trí được mô tả theo quan hệ như cạnh bảng, trên đế hoặc trong ngăn.

## 1 Quy mô và đường nối

Mốc 70 mét vuông của ý tưởng ban đầu được giữ làm tham chiếu cho diện tích khu khám phá chính. Với phiên bản có nhiều gian, chưa khóa tổng diện tích: cần dựng khối thử để kiểm tra khả năng đọc hình, đường đi và góc máy. Không cố nhét nhiều câu đố vào một căn duy nhất rồi kéo dài bằng việc đi vòng. Các gian có thể là những phần ngăn của cùng một mặt bằng nhỏ.

R00 nối R01 bằng một lối mở không khóa. R01 là hành lang có vài góc gấp và nối đến R02, R03, R04, R05. Người chơi đi qua lại các gian từ đầu; cửa ra ngoài công trình không nằm ở cuối hành lang này. R01 có một nhánh cụt phụ dành cho W05, không đặt nguồn bắt buộc trong nhánh đó.

R04 và R05 nên có một đoạn nối ngắn nhìn thấy biển gian để việc mang O02 sang bảng kỹ thuật hợp lý. R03 và R02 ở đủ gần để quay lại đối chiếu hiện vật không thành một chuyến đi dài. Các đường nối không được thay hình học hoặc đóng vĩnh viễn sau một event. Riêng cửa G60 nối R01 với R03 đóng khóa một lần ở E08; mở đúng sẽ giữ mở khóa vĩnh viễn. Những gian khác vẫn đi lại bình thường. Hình thù bất thường đến từ tường lệch, góc gấp và các hốc trưng bày, không từ mê cung tự đổi.

| Gian | Chức năng | Điểm dễ nhận ra |
| --- | --- | --- |
| R00 | Phòng tỉnh dậy và lối kết thúc | Giường, bàn, cửa trong nhà |
| R01 | Nối các gian, tutorial, nhánh event | Biển gian và kệ máy ảnh |
| R02 | So ảnh cũ với tranh hiện tại | Khung xanh ngọc sứt góc |
| R03 | Xoay hiện vật, niêm phong một lần | Ba đế chén, lá, chuông |
| R04 | Tra ngăn, hồ sơ bàn giao | Dãy ngăn có bảng ma trận |
| R05 | Sơ đồ tầng và hộp chìa khóa | Bảng kỹ thuật có chốt đường đi |
| R06 | Đoạn thoát ở tầng dưới | Tuyến kỹ thuật và ánh sáng ngoài trời |

## 2 R00 Phòng trực

R00 mở đầu bằng tầm nhìn vào giường hoặc bàn, không phải một cánh cửa thoát giả. Đặt bàn trong vùng người chơi dễ soi khi vừa có điều khiển, còn lối sang R01 nằm trên đường đi rõ. Giường có mặt khóa hoặc tấm che nhỏ ở cạnh để phản hồi Locked dễ hiểu.

Danh sách đối tượng: giường G00, cơ cấu cánh G01 gắn cùng giường, nắp hoặc miệng lối xuống G02 bị che, bàn G03, giấy I00, lối mở G04 và phần vỏ phòng. Đèn pin là đồ người chơi đã giữ, không đặt thêm pin hoặc một máy ảnh ở đây. Không có ngăn bí mật trên bàn, tranh bổ sung, giấy dưới gối hoặc đồ giải đố cạnh giường.

G00 đứng cố định. G01 là phần có thể mở bằng một chuyển động bản lề sau KEY_OWNED. Tạm dùng một mảng hình học đơn giản cho cánh, sau này chọn kiểu giường và trục cụ thể. Không dựng animation nhấc cả giường rồi đặt sang bên. G02 không có tương tác riêng trước khi mở giường; vật lý và collider phải chặn người đi xuống sớm.

Khi G01 mở, vùng quét của cánh không va vào bàn hay đứng đè lên người chơi. Nếu người chơi đứng trong vùng quét, tương tác yêu cầu lùi nhẹ bằng một dấu hướng trên sàn; không mất chìa khóa. Khi đã mở, cánh giữ nguyên và lối xuống có đủ khoảng cho góc nhìn thứ nhất. R00 là vùng yên tĩnh: không đặt jumpscare tại chỗ đọc I00 hoặc ngay sau khi trở về có chìa khóa.

## 3 R01 Hành lang và nhánh phụ

R01 có các biển R02 Chân dung, R03 Phục chế, R04 Lưu trữ, R05 Kỹ thuật bằng chữ dễ đọc. Không hiển thị mã R cho người chơi; mã chỉ dùng trong tài liệu. Tường có mảng sơn xanh lam cũ, chân tường kem và vết ố N02. Mỗi góc gấp vẫn cho thấy biển tiếp theo hoặc một mốc kiến trúc để không phải mò hoàn toàn bằng tường tối.

Đối tượng đường chính: tủ thấp G10 với một ngăn kéo G11 chứa F01 và I01, kệ G12 đặt máy ảnh O04, các biển gian, cửa kính cao hoặc ô sáng trời G13, đoạn ống và khe gió trang trí. Ngăn G11 không khóa, tay nắm sáng hơn nền và là tutorial mở ngăn. Máy ảnh có dây đeo và màn hình nhỏ giúp phân biệt với đồ chỉ trang trí. Thêm một hốc trưng bày có kính G68, không mở hoặc đi xuyên được, cho pose B05 của E10. B05 nằm trên nền đế thật trong hốc, không đứng lơ lửng ngoài ô kính tầng hai. Đồng hồ G66 ở hành lang có nhãn ĐỒNG HỒ HỎNG, không dùng làm thời gian câu đố.

W04 treo ở đoạn gần R05, không che biển hướng dẫn. Nhánh phụ có W05 ở đầu, biển quay lại ở cuối, một góc gấp trước đoạn cuối và vị trí dàn cảnh E05 E06. Nhánh không dẫn tới phòng chứa clues bắt buộc. Người đọc W05 có thể bỏ qua nhánh hoặc đi vào; đường quay về luôn mở.

Góc gấp tạo một vùng khuất cho đạo cụ event. Một lon kim loại nhẹ G14 có hai trạng thái: nằm trên kệ ở gian khác và nằm trên sàn sát tường sau E02. Không đặt G14 giữa đường khiến người chơi vấp hoặc phải nhặt. Các trạng thái được chuyển khi khuất tầm nhìn; không cần mô phỏng vật lý lăn toàn bộ tuyến.

## 4 R02 Gian chân dung

R02 có W01 làm trọng tâm, W02 đặt trong cùng vùng tương tác, còn W06 nằm ở mảng tường khác để tạo màu. Ba đĩa biểu tượng G20 và tay gạt G21 nằm trên bệ dưới W01. Ngăn G22 chứa F02 chỉ mở sau điều kiện P02. Biểu tượng trên đĩa cần cùng thiết kế với lá, chén và chuông trong ảnh, không dùng ba icon không liên hệ với hình thực.

Một bàn phụ G23 có ngăn không khóa chứa I07. Bút chì G65 ở mép bàn là đạo cụ event nhỏ, không có số hoặc clue. Bàn này không giống ngăn thưởng G22 để tránh hiểu nhầm lời giải. Tượng trang trí B01 là tượng bán thân nhỏ trên bệ ở một hốc tường, nằm ngoài đường quét ánh sáng dùng đọc W01. Không có chữ dưới đáy B01 và không xoay B01 như hiện vật D.

B01 hỗ trợ event chim E04. Chim B02 có phiên bản đứng im trên đầu tượng và một chuyển động giật cánh ngắn. Có khe thông gió hoặc ô kính vỡ ở cao gần hốc để sự xuất hiện của chim có nguồn hợp lý. Khi chưa có event, người chơi có thể nghe cánh xa rất nhẹ nhưng không nhìn thấy một con chim bị dịch chuyển trước mắt.

Khung W01 có thể rung rất nhẹ bằng chuyển động quay vài độ ở E03. Hình tranh, tay nhân vật và mã clue giữ nguyên. Vết sứt góc vẫn nhận ra được sau rung. Bệ tranh và ngăn G22 là đối tượng độc lập, nên animation rung khung không vô tình di chuyển collider ngăn.

## 5 R03 Gian phục chế

R03 có bàn hiện vật G30 với ba đế cố định và D01 D02 D03. Thêm một đế phụ cho mặt nạ D04 để phục vụ E08, không đổi thứ tự ba đế của P03. Các đế giữ vị trí, chỉ hiện vật xoay hoặc nghiêng trong giới hạn. Có mặt nền sáng vừa đủ bên dưới để đáy không chìm đen khi nhìn nghiêng. Đèn pin không xuyên đế để đọc ký hiệu; người chơi phải xoay vật.

Bàn kiểm tra G31 có ba đĩa hình học G32, tay gạt G33 và ngăn G34 chứa I02 cùng O01. Đĩa dùng tam giác, tròn, vuông đúng hình dưới D. Ngăn phụ G35 không khóa chứa I06, F08 và I08, đặt tách nhau để có thể lấy hết. I09 và I10 trên bàn; I11 trong một ngăn mở gần G37; F07 trên kệ mở. W08 gắn tường. Không nguồn mở cửa nào nằm trong G34 bị khóa bởi P03. Dụng cụ trang trí như khăn, bút và kẹp nằm gọn ở rìa, không có số hoặc biểu tượng trùng đáp án.

D01 đến D03 không bị nhặt. Mỗi đối tượng có nút xem, xoay ngang, nghiêng và trả góc. Có thể dùng cùng một bộ điều khiển cho cả ba. Sổ lưu hai chi tiết đáy mỗi vật: hình học và mã R. Khi đã xác nhận hồ sơ P05, một chốt nhỏ G36 có thể xoay và phát A05; không biến dạng đồ vật hoặc tháo đế ra.

Cửa G60 là lối duy nhất vào ra R03, quay bản lề bình thường. Mặt trong có bốn vòng số và tay gạt G61 cùng bảng W07. Khay G62 gắn bên cơ cấu chứa I12, mở khi giải E08. Vùng trigger nằm sâu hơn vùng quét cánh cửa; nếu người chơi đang ở đường quét, hoãn đóng. Collider chặn đường khi cửa thực sự đóng, không dựng tường vô hình giữa phòng.

Kệ G37 có lon G14 cho E02 và hộp sắt dẹt G69 cho E08. Mỗi đạo cụ có hai trạng thái độc lập, không đặt lại lên kệ sau khi rơi. Kệ đủ xa nguồn cần đọc để đạo cụ không che clue. Lon và âm thanh chỉ tạo một lý do xem lại gian; ngăn quan trọng vẫn có chỉ dẫn bằng sổ nếu người chơi không nghe được tiếng rơi.

## 6 R04 Gian lưu trữ

R04 có dãy ngăn G40 ba hàng ba cột. Các nhãn A1 đến C3 đủ lớn, đặt cùng kiểu và không đổi qua event. W03 gắn đầu dãy ngăn và nhìn thấy trước khi thử mở. Tất cả các ngăn có tay nắm, nhưng chỉ B2 có khóa khớp O01; những ngăn còn lại có thể mở nông với giấy kê trang trí hoặc phản hồi không thuộc hồ sơ này.

B2 là ngăn G41. Trong ngăn có I03, F03 và O02 đặt tách nhau, cùng nhìn thấy khi mở. Tương tác chọn từng món; nếu còn món, ngăn giữ trạng thái mở và balo có nhắc chưa lấy hết hồ sơ. Không xếp một dấu dưới ảnh để yêu cầu vật lý nhấc ảnh rồi mới thấy nó.

Bàn đọc G42 có ngăn tùy chọn G43 chứa F05 và I05. Máy phát bản ghi G63 đặt cạnh bàn, có nhãn nguồn tự duy trì, nút Play Stop và cuộn quay đơn giản cho E11. Không dùng thoại để thay bằng chứng bắt buộc. Giấy trắng G67 chỉ trang trí, không nhặt. Có một ghế cố định và đèn bàn hỏng chỉ làm đạo cụ, không tự sáng thành nguồn ánh sáng mới. Góc bàn là vùng nghỉ đọc hồ sơ. Event nhặt F05 chỉ được xếp lịch sau khi người chơi đóng chế độ xem và rời bàn; tuyệt đối không che chữ I03.

Một khoảng mở nhìn về đoạn nối R05 giúp người chơi nhận ra nơi dùng O02 sau khi đọc I03. Không đặt cửa thoát ngoài trời ở R04; các cửa sổ là ô cao hoặc bị chắn, phục vụ ánh sáng và bối cảnh thời tiết, không là đường ra thứ hai.

## 7 R05 Gian kỹ thuật

R05 có bảng kỹ thuật G50 với chốt G51 mang biểu tượng đường đi, khớp O02. Khi dùng dấu, cánh G52 mở trên bản lề để lộ F04, I04, O03 trong một hốc nông. Ba nguồn đều là vật rời có thể nhặt; bản sơ đồ lớn trang trí ngoài bảng, nếu có, không được chứa toàn bộ thông tin F04 để người chơi nhầm đã lấy đủ.

Hộp chìa khóa G53 đặt trên bệ cố định, có ba hàng kết luận G54 và các điểm áp dấu. Khi chưa đủ hồ sơ, điểm thiếu hiện tên hồ sơ cần bổ sung; không đưa thông báo lỗi mơ hồ. Nắp G55 mở bản lề khi ba hàng xác nhận. O05 nằm trong lòng hộp đã được model từ đầu và chỉ có thể nhặt sau khi nắp mở.

Ngăn phụ G56 chứa F06, không khóa và không ảnh hưởng G50. N03 trên ống gió có chữ THÔNG GIÓ. Một khe ống thấp G64 là điểm kết thúc điều tra âm của E09; hình lưới và hướng ống đi xuống cho thấy âm truyền từ tuyến kỹ thuật. Trong gian có tiếng thông gió thấp A03, không tiếng người hướng dẫn đáp án. Không đặt một vật trượt khỏi bệ ở gần hộp sau khi người chơi lấy chìa khóa; giai đoạn này ưu tiên đưa họ quay lại R00 rõ ràng.

## 8 R06 Tuyến thoát

R06 chỉ xuất hiện sau khi giường mở. Đoạn đầu là bậc xuống hoặc điểm chuyển cảnh dưới G02. Đoạn sau là đường kỹ thuật ngắn có ống, tường thô và ánh sáng ngoài trời từ cửa cuối. Không chứa mã mới, dấu mới hay một vật phẩm bắt buộc khác.

Cửa cuối đã mở đủ cho người chơi đi qua. Khi qua ranh giới ngoài nhà, lưu END_REACHED rồi mở màn hình kết thúc. Âm mưa hoặc gió chuyển từ nghe qua kết cấu sang không gian ngoài trời. Không dùng cửa cuối để thêm một lớp khóa kéo dài game.

## 9 Danh sách animation cần làm

| Chuyển động | Đối tượng | Cách làm cơ bản | Điều kiện |
| --- | --- | --- | --- |
| Xoay và nghiêng | D01 D02 D03 | Quay quanh trục tại đế, giới hạn góc | Đưa được đáy ra trước |
| Xoay đĩa | G20 G32 G54 | Quay theo nấc, dùng cùng bộ điều khiển | Mỗi nấc có biểu tượng rõ |
| Kéo ngăn | G11 G22 G34 G41 G43 G56 | Tịnh tiến trên một trục | Không cắt xuyên item |
| Gạt chốt | G21 G33 G36 G51 | Quay hoặc trượt ngắn | Có trạng thái đóng mở |
| Mở cánh | G52 G55 G01 | Quay bản lề | G01 cần thử vùng quét |
| Rung khung | W01 | Quay lệch nhỏ rồi trả về | Chỉ ngoài lúc xem clue |
| Rơi đạo cụ | G14 | Đổi hai trạng thái ngoài tầm nhìn | Tiếng và vị trí sau khớp |
| Chim giật cánh | B02 | Quay hai cánh và dịch một đoạn ngắn | Event tùy chọn, không bay vòng |
| Đánh ngất | B03 B04 | Một pose bóng người và gậy quay một nhịp | Nhánh E06 nâng cao |
| Cửa niêm phong | G60 G61 G62 | Cánh quay, vòng xoay nấc, khay trượt | Chỉ R03 khóa một lần |
| Máy phát ghi âm | G63 | Nút nhấn, cuộn quay, trạng thái Play Stop | Không cần animation tay |
| Bóng trong Camera | B05 G68 | Hai trạng thái tĩnh của hốc | Đổi khi khuất, ảnh lưu frame thật |
| Mờ và chớp | Góc nhìn và đèn pin | Hiệu ứng màn hình, đổi cường độ sáng | Có mức giảm hiệu ứng |

B03 là hình người cầm gậy xuất hiện rất ngắn trong nhánh E06, B04 là gậy gắn vào pose. Không cần đi bộ, rượt đuổi, đối thoại hay hệ thống AI. Nếu chưa làm được pose và chuyển động gậy thuyết phục, dùng biến thể E06B được mô tả trong file event. Hai biến thể không cùng chạy trong một lượt.

## 10 Những quan hệ cần kiểm tra khi dựng khối

W02 phải ở gần W01, nhưng không che khuôn mặt hoặc tay trong tranh. W03 phải đọc được trước dãy ngăn. Ba hiện vật phải có đủ khoảng cho góc nghiêng mà không xuyên nhau. O02 và biểu tượng G51 phải trùng nhau. Giường mở xong phải còn đường đứng và đi xuống.

Nhánh W05 có khoảng trống quay lại, không cửa khóa tự động và không lối có thể vô tình rơi khỏi map. Dàn cảnh E06 dùng đoạn góc gấp để giấu B03, không đặt hình người tại một gian khác rồi dịch qua trước mắt. E04 cần một góc khuất thực của hốc tượng; chỉ tắt đèn pin không bảo đảm đối tượng đang khuất nếu ánh sáng trời vẫn chiếu tới.

Các góc gấp giúp đạo cụ biến đổi ngoài tầm nhìn, nhưng mỗi gian phải có ít nhất một mốc nhận biết ổn định. Nếu người chơi đi theo âm tới G14, họ nhìn thấy lon nằm dưới kệ và hiểu tiếng phát từ đó. Không phát tiếng rơi ở R04 rồi đặt lon tại R03.

## 11 Thứ tự sản xuất đề xuất

Dựng R00, R01 và các gian bằng khối, hoàn thiện toàn bộ đường chính với texture clues đọc được, balo và lưu game. Sau khi kiểm chứng được một lượt đi hết, làm model ba hiện vật, tranh, ngăn, hộp và giường. Tiếp theo chỉnh âm thanh ánh sáng rồi thêm event ngoài tầm nhìn.

Ưu tiên G01, hệ thống xem ảnh giấy, ba bộ xoay, balo, 19 nguồn hồ sơ cuối và các nguồn E08 trong R03. O04 cùng album Camera là tính năng thứ hai. E04 chim và E06 hình người là lớp trình diễn sau cùng; việc chưa có chúng không ảnh hưởng đáp án, điều kiện lấy chìa khóa hoặc lối kết thúc.

## 12 Vị trí phục vụ các cụm khác

E09 dùng các điểm âm cố định ở R01, R04 và R05, nối qua hành lang đã có. Không cần đổi phòng, đóng thêm cửa hoặc làm một mê cung mới. Nguồn cuối tại G64 thấp gần chân tường. Người chơi có thể bỏ điều tra và tiếp tục tới bảng G50 bằng sổ.

E10 dùng hốc kính G68 ở R01, có vùng nền để thấy silhouette và khoảng đứng để hướng Camera. Hốc cách cửa R03 đủ để không cùng phát E08; vị trí cụ thể chỉ chốt khi dựng khối. B05 là pose tĩnh có thể dùng lại model nhân vật, không có AI hoặc tương tác đánh nhau.

E11 dùng G63 trên bàn R04 và một điểm âm sau ghế trống. Ghế giữ nguyên, không cần có người ngồi hoặc dịch ghế. Nhấn Stop có thể đổi nhánh âm nhưng không khóa ngăn hoặc giấu hồ sơ. Cả sáu cụm lớn dùng đường đi và đồ cố định; chỉ E08 có cơ chế nhốt phòng.

Bóng dưới khe G60 có thể dùng một vật che nhỏ B06 ở phía hành lang, trượt ngắn trong vùng khuất và đổ bóng từ ánh hắt L02 có thật. Nếu góc sáng không tạo được bóng hợp lý, chỉ giữ A19 bước chân. Không thêm một nguồn sáng vô hình hoặc yêu cầu một NPC đi bộ để làm nhịp này.
