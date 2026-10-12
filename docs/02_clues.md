# Ảnh giấy và vật phẩm của bảo tàng

> Tài liệu gameplay cho giai đoạn sau. Các mã R dưới đây là vùng chức năng, không quyết định mặt bằng hoặc tọa độ nhà. Khi build kiến trúc, dùng [file 06](06_cach_build_bao_tang.md) và ZIP hình học. Việc ánh xạ item/event sang vị trí thật thực hiện sau khi chốt kiến trúc; hiện chỉ dựng kiến trúc thô.

Tài liệu clues · Thiết kế phiên bản 4 · 12 tháng 10 năm 2026

Danh mục này mô tả nội dung nhìn thấy, chữ in, mặt sau, khung và cách thu thập của từng nguồn thông tin. Những chi tiết có đáp án phải được đưa vào asset, không chỉ nằm trong lời mô tả thiết kế. Mã nguồn là căn cứ chung cho flow, kiến trúc, âm thanh và event.

## 1 Quy tắc phân loại và balo

| Mục balo | Nội dung | Hành vi |
| --- | --- | --- |
| Ảnh thu thập | F01 đến F08 | Xem trước sau, phóng to, đối chiếu; F01 đến F04 bắt buộc |
| Giấy | I00 đến I12 | Xem trước sau, phóng to, bản chép chữ; I00 đến I04 và I12 bắt buộc cho hồ sơ cuối |
| Vật phẩm | O01 đến O05 | Xoay bản xem, đọc nhãn, dùng tại điểm cố định |
| Sổ manh mối | W01 đến W05, W07 W08 và quan sát D01 đến D04 | Lưu bản xem được biên soạn sẵn và ghi chú; đồ trên tường vẫn ở nguyên chỗ |
| Camera | Ảnh do người chơi chụp | Album cá nhân có thời điểm và gian chụp; độc lập với ảnh F |

W06 và các nét nhiễu chỉ là trang trí, không tạo thẻ nguồn. Nếu người chơi chụp chúng, chúng xuất hiện trong Camera như mọi ảnh cá nhân khác. Balo không giới hạn số lượng giấy, ảnh hoặc dấu của đường chính. Đồ đã nhặt không được ném ra và không bị dùng mất.

“Bắt buộc nhặt” yêu cầu item nằm trong balo. “Bắt buộc xem” yêu cầu mở chế độ xem và thấy vùng thông tin đã xác định; hệ thống tự ghi nguồn vào sổ. Không bắt người chơi tự chụp ảnh tường để chứng minh đã xem. Chi tiết đáy hiện vật được nhận khi cả hình học và mã nằm trong vùng xem đủ rộng, không dùng một điểm ảnh nhỏ hoặc một góc xoay duy nhất.

## 2 Danh mục nguồn bắt buộc

| Mã | Loại | Vị trí chức năng | Nội dung quyết định |
| --- | --- | --- | --- |
| I00 | Giấy nhặt | Bàn R00 | Mục tiêu hình chìa khóa |
| F01 | Ảnh nhặt | Ngăn thấp R01 | Lá, chén, chuông theo thứ tự người |
| I01 | Giấy nhặt | Cùng ngăn R01 | Khung thật và quy tắc dùng ảnh lưu trữ |
| W01 | Tranh tường xem | R02 | Bức tranh đã đổi vật trong tay |
| W02 | Bảng tường xem | Dưới W01 | Thứ tự trái sang phải trong ảnh lưu trữ |
| F02 | Ảnh nhặt | Ngăn thưởng R02 | Chén số 1, lá số 2, chuông số 3 |
| D01 | Hiện vật xem | Đế chén R03 | Tam giác và R08 |
| D02 | Hiện vật xem | Đế lá R03 | Tròn và R17 |
| D03 | Hiện vật xem | Đế chuông R03 | Vuông và R23 |
| I02 | Giấy nhặt | Ngăn bàn R03 | Hồ sơ hiện vật trả từ phục chế |
| O01 | Dấu nhặt | Cùng ngăn R03 | Dấu hồ sơ hiện vật |
| W03 | Bảng tường xem | Dãy ngăn R04 | Hàng loại đồ, cột trạng thái |
| I03 | Giấy nhặt | Ngăn B2 R04 | B là bản gốc, R là bản sao; mã 08 17 23 |
| F03 | Ảnh nhặt | Ngăn B2 R04 | B08 B17 B23 được bàn giao qua kho |
| O02 | Dấu nhặt | Ngăn B2 R04 | Dấu hồ sơ đường đi |
| F04 | Ảnh nhặt | Sau bảng R05 | Mặt cắt tầng hai và lối dưới giường |
| I04 | Giấy nhặt | Sau bảng R05 | Cách mở hộp và lối kỹ thuật |
| O03 | Dấu nhặt | Sau bảng R05 | Dấu hồ sơ tầng |
| I12 | Giấy nhặt | Khay cửa R03 sau E08 | Phiếu gốc kiểm chứng dòng chén bị sửa |

O05 là chìa khóa lấy được sau 19 nguồn trên và ba kết luận đúng. Mọi nguồn tùy chọn đều được ghi rõ trong phần riêng. Hệ thống gợi ý dùng tên nguồn thân thiện với người chơi, không hiện mã nội bộ F hay I trên HUD.

## 3 Ảnh có thể nhặt

### F01 Gia đình trong ảnh lưu trữ

F01 bắt buộc nhặt, nằm trong ngăn kéo thấp R01 bên cạnh I01. Ảnh màu giấy mờ, tỷ lệ ngang 3 trên 2, có viền trắng ngà và góc dưới trái gập nhẹ. Không có khung gỗ đi kèm; chỉ nhặt tấm ảnh.

Mặt trước chụp W01 khi còn bản cũ, đủ thấy cả khung và ba người. Bên trái là người mẹ mặc xanh ngọc cầm một lá đồng có cuống dài. Giữa là người cha áo đỏ gạch cầm chiếc chén xanh lam. Bên phải là đứa trẻ áo vàng cầm chuông nhỏ. Vật cầm có hình dáng rõ, tách khỏi nền và không bị tay che hết. Khung trong ảnh có vết sứt tam giác ở góc dưới phải, trùng khung thật tại R02.

Ảnh không in lời giải LÁ CHÉN CHUÔNG. Dòng nhỏ trên viền dưới viết “Phòng chân dung trước lần thay nhãn”. Mặt sau viết “Ảnh lưu trữ. Không lật ngược khi đối chiếu.” Một mũi tên hướng lên nằm cạnh chữ để tránh người chơi hiểu nhầm ảnh bị soi gương. Phóng to vùng bàn tay vẫn phải giữ nét rõ. Nguồn này giải P02 và cho thấy tranh hiện tại đã bị thay.

### F02 Bàn phục chế và ba vị trí

F02 bắt buộc nhặt, nằm trong ngăn dưới W01 sau P02. Ảnh ngang 4 trên 3, giấy trắng hơi ngả xanh, không khung. Viền có ba lỗ ghim cũ nhưng không che thông tin.

Mặt trước chụp một bàn phục chế từ góc hơi cao. Chén ở bên trái, lá ở giữa, chuông ở bên phải. Mỗi món nằm trên một ô giấy có số lớn 1, 2, 3 tương ứng. Trên ảnh không nhìn thấy hình học ở đáy; chúng vẫn phải được tìm bằng cách xoay hiện vật 3D. Nền bàn không có vật giống ba biểu tượng của câu đố.

Chữ in trên mép ảnh là “Bàn kiểm tra mặt đáy”. Mặt sau viết “Giữ thứ tự các ô. Xoay từng hiện vật để xem mặt không trưng bày.” Một đường gạch dưới từ “thứ tự” giúp định hướng mà không ghi đáp án. Ảnh dùng cho P03, sau đó là một nguồn nhận diện bộ hiện vật trong hồ sơ cuối.

### F03 Chuyến bàn giao qua kho

F03 bắt buộc nhặt trong B2 tại R04, cùng I03 và O02. Ảnh màu đã bạc nhẹ, ngang 3 trên 2, viền trắng rộng ở cạnh dưới. Ảnh không khung và không có một vùng đáp án bị rách mất.

Mặt trước cho thấy thùng gỗ đang mở đặt dưới biển “KHO PHỤC CHẾ”. Bên trong có chén, lá và chuông, đặt trên vải xám. Ba thẻ dày buộc cạnh từng vật ghi rõ B08, B17, B23. Một cửa kỹ thuật và xe đẩy đứng ở hậu cảnh; không cần dựng chúng thành khu gameplay hoặc cho người chơi đẩy xe.

Viền dưới viết “Bàn giao bộ hiện vật sau phục chế”. Mặt sau có chữ “Đồ đi qua kho trước khi chuyển vào tuyến vận chuyển.” Chén trong ảnh có vết sứt chân trùng F07, bổ sung căn cứ hình ảnh để xác thực thẻ B08. Không ghi rằng hiện vật đang trưng bày là bản sao; người chơi phải đọc I03 và so mã R dưới các vật thật. Ảnh chứng minh tuyến KHO PHỤC CHẾ và việc các bản gốc đã được chuyển đi.

### F04 Mặt cắt và phòng trực

F04 bắt buộc nhặt sau bảng kỹ thuật R05, mở bằng O02. Đây là bản ảnh chụp lại một bản vẽ kỹ thuật, giấy ngang 4 trên 3, viền trắng đều, không khung. Phải đọc được cả khi không phân biệt tốt màu sắc.

Hình cho thấy hai dải ngang chồng lên nhau. Dải trên có chữ “TẦNG II” và các khối phòng đơn giản; một khối có biểu tượng giường và chữ “PHÒNG TRỰC”. Dải dưới ghi “TẦNG I” và một đường kỹ thuật dẫn sang ký hiệu cửa ngoài. Một mũi tên đi xuống từ dưới giường xuyên qua sàn tới đường này. Phần mặt cắt là sơ đồ giải thích tầng, không là bản đồ có tọa độ để định vị từng mét.

Nét đỏ vẽ đường xuống, nét xanh vẽ tuyến kỹ thuật; cả hai còn có nét liền và nét đứt khác nhau để không dựa vào màu đơn thuần. Góc dưới viết “Lối kỹ thuật bên dưới bệ giường”. Mặt sau viết “Đối chiếu với phiếu bảo trì phòng trực.” F04 và I04 cùng xác nhận vị trí thoát, tránh phụ thuộc vào một hình mơ hồ.

### F05 Ngày mở cửa bảo tàng

F05 tùy chọn nhặt, nằm trong ngăn kéo không khóa của bàn đọc R04. Ảnh ngang giấy bóng nhẹ, viền trắng, không khung. Mặt trước là nhóm nhân viên đứng trước sảnh sáng màu, người giữ chùm chìa khóa đứng ngoài cùng phải. Không có mã ổ khóa hoặc vật đáp án trong tay họ.

Viền viết “Ngày mở cửa”. Mặt sau viết “Linh đứng ngoài cùng bên phải. Người trực đầu tiên của khu trưng bày.” Nguồn này giúp người chơi biết tên người có liên quan, nhưng không xác nhận người chơi là Linh và không mở một cơ cấu nào. Từ tên Linh có thể dẫn người tò mò đọc I05.

### F06 Phòng trực khi còn sử dụng

F06 tùy chọn nhặt trong ngăn phụ R05, có thể lấy bất cứ khi nào vào gian. Ảnh dọc giấy mờ, hai góc có dấu băng dính cũ, không khung. Mặt trước là bàn và giường trong một căn phòng sáng ban ngày, bình hoa nhỏ ở cửa sổ và áo khoác trên ghế. Những đồ này thuộc quá khứ trong ảnh, không được đặt thành clue mới ở R00 hiện tại.

Viền dưới không có chữ. Mặt sau viết “Để lại đường về cho người đến sau. L.” Không vẽ chìa khóa, đường xuống hoặc gợi ý bắt buộc. Ảnh tạo cảm giác phòng xuất phát từng có người sống và bổ sung ý nghĩa cho I05. Nó không làm xuất hiện chữ Open.

## 4 Ảnh tranh và bảng cố định trên tường

### W01 Gia đình bên cửa sổ

W01 bắt buộc xem tại R02. Tranh có tỷ lệ ngang 3 trên 2; ba bàn tay đủ lớn để xem rõ từ khoảng tương tác bình thường. Khung gỗ sơn xanh ngọc, đường chỉ vàng mỏng, bốn góc đơn giản. Góc dưới phải sứt một miếng tam giác và lộ gỗ sáng. Khung gắn tường, không nhặt vào balo. Ba đĩa và ngăn thưởng nằm trên một đế cơ cấu riêng ngay dưới khung.

Tranh hiện tại có cùng ba người với F01. Thứ tự trái sang phải giữ nguyên, nhưng mẹ cầm chén, cha cầm chuông, trẻ cầm lá. Tư thế tay và khuôn mặt không thay đổi nên người chơi có thể nhận ra đây là cùng bức tranh. Không thêm một mặt người đột ngột chuyển động làm clue bắt buộc.

Mặt tranh không có chữ. Biển cạnh khung viết “Gia đình bên cửa sổ”. Mặt sau không xem được và không chứa thông tin; có thể dùng texture gỗ đơn giản. Chế độ xem toàn tranh và ba tay tự lưu W01 vào sổ. Event E03 chỉ làm khung rung nhẹ sau giai đoạn đối chiếu; không thay vật trong tay theo thời gian.

### W02 Quy tắc ảnh lưu trữ

W02 bắt buộc xem, là một bảng giấy cố định đặt thấp cạnh W01, không cùng texture với nhãn tên tranh. Nền kem, chữ đen, một đường kẻ xanh ngọc. Bảng được kẹp vào hai thanh gỗ mảnh ở cạnh trên và dưới; không dùng khung kính gây phản xạ che chữ.

Nội dung đầy đủ: “Đối chiếu ảnh lưu trữ. Chọn vật người trong ảnh lưu trữ đang giữ. Xếp theo thứ tự người từ trái sang phải. Tranh treo hiện tại có thể đã được sửa.” Dòng đầu lớn hơn phần còn lại. Góc dưới có ba ô rỗng minh họa thứ tự, không in sẵn biểu tượng đáp án.

Không xem mặt sau và không nhặt bảng. Khi đọc, sổ lưu nguyên văn. W02 làm rõ quy tắc P02 để việc chọn F01 thay vì W01 là một suy luận có cơ sở, không là đoán ý tác giả.

### W03 Bảng lưu hồ sơ

W03 bắt buộc xem ở R04 ngay đầu dãy ngăn. Bảng dọc nền trắng xám, chữ và đường lưới xanh lam đậm. Khung nhôm mỏng, có hai vít nhìn thấy, không kính. Một góc bong sơn nhưng toàn bộ quy tắc còn đọc được.

Bảng viết “HÀNG: A TRANH; B HIỆN VẬT; C GIẤY” và “CỘT: 1 TRƯNG BÀY; 2 PHỤC CHẾ; 3 VẬN CHUYỂN”. Bên dưới là ma trận 3 nhân 3 với nhãn A1 đến C3. Không tô sáng B2. Các nhãn trên ngăn thật trùng chính xác ma trận. Mặt sau không truy cập và không có clue.

Khi xem bảng, sổ giữ ma trận và hai dòng giải thích để có thể đặt cạnh I02. Người chơi cần kết hợp loại đồ với trạng thái, thay vì thử lần lượt chín ngăn. B2 không có vết sáng riêng khiến đáp án bị lộ trước khi đọc.

### W04 Ảnh cầu thang cũ

W04 tùy chọn xem ở đoạn nối R01 với R05. Ảnh đen trắng dọc, khung gỗ nâu phẳng, một tấm kính ít phản xạ. Hình chụp cầu thang nội bộ có bảng “II” trên chiếu nghỉ trên cùng và “I” bên dưới. Người đứng ở mép ảnh bị cắt khỏi khung, không có khuôn mặt dùng làm jumpscare.

Nhãn dưới ảnh viết “Cầu thang nội bộ trước khi niêm phong”. Không có chữ phía sau để mở khung tìm. W04 là dấu gợi tầng hai từ sớm, nhưng không thay thế F04 và I04 trong hồ sơ bắt buộc. Sổ chỉ lưu nó dưới mục bổ sung, không đánh dấu thiếu nếu chưa xem.

### W05 Tờ nhắn ở nhánh cụt

W05 tùy chọn xem trong nhánh phụ R01. Là một trang giấy dọc được ghim lên tường bằng hai đinh đầu tròn; không khung, không kính, không nhặt. Mép dưới xé một đoạn nhưng không mất chữ.

Nội dung đúng: “Nếu nghe tiếng chuông phía sau, đừng quay đầu lại. Đi tới tấm biển cuối nhánh. Khi chuông ngừng, quay về.” Chữ dòng đầu viết đậm hơn; dòng cuối đủ lớn và không bị cố ý giấu. Tờ nhắn không hứa sẽ giết người nếu quay đầu. Tài liệu event quy định riêng hai phản ứng có thể xảy ra khi làm theo hoặc quay lại.

Cuối nhánh có biển bình thường “KHU VỰC NIÊM PHONG — QUAY LẠI”. Biển này không là clue của hộp. Nó giải quyết ngõ cụt ngay trong nội dung, không buộc người chơi tìm đường xuyên tường. W05 tạo một tình huống lựa chọn tùy chọn và không khóa đường chính.

### W06 Tranh mảng màu

W06 là tranh trang trí tại R02, không cần xem để hoàn thành. Các mảng vàng men, xanh lam, đỏ gạch và kem tạo bố cục giống cửa sổ. Không có con số, hình lá, chén, chuông hoặc tam giác tròn vuông xếp thành hàng. Nhãn tên là “Nắng trong sân”. Khung gỗ sáng mỏng và không có cơ cấu phía sau.

Tranh không đổi texture để ngầm chứa một mật mã thứ hai. Người chơi có thể chụp vào Camera nhưng sổ không tạo một ô chưa giải. Cách này cho bảo tàng hình ảnh phong phú mà không khiến mọi thứ trang trí trông như một câu đố bị bỏ sót.

## 5 Giấy có thể nhặt

### I00 Hướng dẫn trên bàn

I00 bắt buộc nhặt, là tờ giấy duy nhất trên bàn R00. Giấy dọc khổ gần A5, màu kem, đặt phẳng không khung, không phong bì và không ghim thêm một mẩu riêng. Mặt trước sạch ở vùng chữ, mép hơi cũ để hợp với căn phòng.

Nội dung chính xác: “Nếu đọc được tờ này, hãy mang theo nó. Đèn còn hoạt động. Ra hành lang và xem kỹ các hiện vật. Ảnh và giấy rời có thể giữ lại. Những thứ gắn trên tường chỉ cần xem kỹ.” Bên dưới là khoảng trắng, sau đó hình một chiếc chìa khóa đồng có đầu vòng tròn, một rãnh hẹp ở cổ và ba răng không đều. Dòng cuối dưới hình đúng là “nó ở đâu...”. Không thêm mũi tên, số tầng, lời giải hộp hoặc chỉ dẫn giường ở cuối trang.

Mặt sau để trống, chỉ có vệt giấy, không viết chìm bằng đèn pin. Khi đóng lần đọc đầu, game tự cất I00 và giải thích cách mở balo bằng một hướng dẫn giao diện ngắn. Chìa khóa O05 phải có cùng đầu vòng, rãnh cổ và bộ răng để người chơi nhận ra đúng mục tiêu.

### I01 Phiếu kiểm tra tranh

I01 bắt buộc nhặt trong ngăn R01 cùng F01. Giấy nhỏ dọc màu trắng ngà, một đường gấp ngang, không khung. Tiêu đề “PHIẾU KIỂM TRA TRANH” in đen đậm; phần thân dùng cùng một kiểu chữ rõ, không làm toàn bộ bằng chữ viết tay khó đọc.

Nội dung: “Đối chiếu đúng khung có góc dưới bên phải bị sứt. Ảnh lưu trữ ghi nhận vật trước khi chỉnh sửa. Xem bảng hướng dẫn đặt cạnh khung.” Mặt sau có dấu “LƯU TRỮ”, không chứa thêm đáp án. I01 nối F01 với W01 và W02, không cần tên phòng được đoán từ màu tường.

### I02 Phiếu trả từ xưởng

I02 bắt buộc nhặt trong ngăn bàn R03 sau P03. Giấy ngang dạng phiếu, góc trên có lỗ dập và một vệt mực không chạm chữ. Không khung và không phong bì. Hai dòng cần suy luận được đặt trong cùng vùng nhìn.

Nội dung: “PHIẾU TRẢ TỪ XƯỞNG. Hồ sơ của bộ hiện vật đã trả về từ xưởng phục chế. Tra dãy ngăn theo loại đồ và trạng thái cuối cùng. Dùng dấu hiện vật để mở đúng ngăn.” Không in B2 trực tiếp. Mặt sau ghi “Ba món cùng một bộ: chén, lá, chuông.” I02 kết hợp với W03 tạo đáp án B2.

### I03 Sổ kiểm kê bộ ba

I03 bắt buộc nhặt trong B2 ở R04. Dạng hai trang gập nhưng là một item, giấy vàng nhạt có đường kẻ mảnh. Giao diện có nút lật trang, không yêu cầu mở một quyển sách vật lý nhiều animation. Không khung.

Trang đầu viết “MÃ KIỂM KÊ. B = BẢN GỐC. R = BẢN SAO. 08 = CHÉN. 17 = LÁ. 23 = CHUÔNG.” Trang thứ hai viết “B08, B17, B23: chuyển từ xưởng vào kho phục chế, sau đó bàn giao qua tuyến vận chuyển nội bộ. R08, R17, R23: thay vào vị trí trưng bày. Khi kiểm tra, phải đối chiếu mã trên vật với ảnh bàn giao.”

Lề dưới có dòng “Dấu đường đi mở bảng kỹ thuật trong gian kỹ thuật.” Mặt ngoài sau khi gập có tiêu đề “Bộ ba hiện vật”; không giấu một dòng bắt buộc ở đường gấp. Nguồn này đủ chứng minh hành vi tráo đồ khi kết hợp F03 và đáy D01 đến D03. I03 nói rõ việc thay bản sao, nhưng người chơi vẫn phải xác thực đủ ba mã trên vật đang có.

### I04 Phiếu bảo trì phòng trực

I04 bắt buộc nhặt cùng F04 và O03 sau bảng kỹ thuật R05. Giấy dọc màu xám kem, in rõ, một dấu “PHÒNG TRỰC” ở đầu. Không khung. Mặt trước có hai phần cách nhau bằng một đường kẻ, không dựa vào màu để tách nội dung.

Nội dung phần đầu: “Phòng trực nằm ở tầng hai. Giường che lối xuống tuyến kỹ thuật tầng một. Lối này mở bằng chìa khóa đầu vòng tròn.” Phần sau: “Hộp chìa khóa cần ba hồ sơ: hiện vật, đường đi, tầng. Đối chiếu đủ nguồn rồi áp ba dấu cùng tên. Dấu không giữ lại trong hộp. Mang chìa khóa về phòng trực.”

Mặt sau ghi “Không cố nâng cả giường. Mở phần cánh có bản lề sau khi mở khóa.” Dòng này là mô tả hành vi chung; hình thức cánh cụ thể được quyết định khi dựng model. I04 không tạo một cơ chế nhấc và dời giường tự do.

### I05 Lời nhắn cuối của Linh

I05 tùy chọn nhặt ở bàn đọc R04 bên cạnh F05. Giấy trắng ngà có nét viết tay được biên soạn rõ; không khung. Mặt trước viết: “Tôi đã đối chiếu ảnh với những thứ đang treo. Mọi mã đều đã đổi. Tôi giữ lại hồ sơ và để đường xuống cho người đến sau. Nếu tìm được đường ra, mang chúng theo. Linh.”

Mặt sau để trống. Giấy giải thích động cơ của người để hướng dẫn và việc giữ bằng chứng. Nó không cấp một dấu mới hoặc làm hộp khóa bắt đầu hoạt động. Người bỏ qua I05 vẫn hiểu bí mật từ I03 và F03.

### I06 Phiếu bảo dưỡng đèn

I06 tùy chọn nhặt trong ngăn phụ R03. Giấy nhỏ ngang màu xanh nhạt, không khung, mặt sau trống. Nội dung: “Đèn kiểm tra dùng nguồn duy trì. Nếu tiếp điểm rung, ánh sáng có thể chớp ngắn. Đợi tiếp điểm ổn định rồi đọc nhãn.”

Giấy giải thích một đặc điểm môi trường, không mở hệ thống tìm pin hoặc làm đèn sáng hơn. Game không có pin bắt buộc nhặt để tiếp tục. Các chớp được kiểm soát bởi event và không diễn ra khi người chơi đang đọc nguồn chính.

### I07 Phiếu vệ sinh trưng bày

I07 tùy chọn nhặt ở ngăn không khóa R02. Giấy dọc trắng xám, không khung, góc trên có hình khăn lau nhỏ. Nội dung: “Không lau mất số dưới đáy hiện vật. Không mở cơ cấu sau khung khi đang treo. Đánh dấu mép khung bằng bút chì trước khi căn lại.”

Mặt sau ghi “Các nét đo trên tường phục vụ bảo dưỡng.” Giấy giúp giải thích một số nét nhiễu và cảm giác nơi này từng được chăm sóc. Nó không thay thế F02 hoặc cung cấp đầy đủ câu trả lời P03.

## 6 Hiện vật cố định cần xoay

### D01 Chén men xanh lam

D01 bắt buộc xem, ở đế trái bàn hiện vật R03. Chén có thân tròn, chân thấp, hai đường men xanh lam trên nền kem và một vết xước nhỏ gần vành. Bản trưng bày có lớp màu mô phỏng men; không buộc người chơi phân biệt chất liệu bằng thị giác. Đế cho xoay ngang và nghiêng có giới hạn để đưa đáy ra trước; không nhấc chén đi chỗ khác.

Mặt đáy có tam giác lớn và mã “R08” ngay dưới. Hình và mã cùng nằm trên một mảng sáng, không bị lỗ gá che. Không có chữ trong lòng chén. Cạnh mảng tam giác và R08 có một tem tròn riêng mang dấu trăng, dùng cho E08. Vùng hình học và tem kiểm định có viền khác nhau để phân biệt hai cơ cấu. Chén hiện tại không có vết sứt chân của bản gốc trong F07. Chế độ xem giữ hình đáy trong sổ khi cả hai phần đã thấy. Khi rời tương tác, vật giữ góc vừa xoay; có nút đưa về góc trưng bày để dễ đọc lại.

### D02 Lá đồng

D02 bắt buộc xem, ở đế giữa R03. Lá có cuống dài, bề mặt xanh đồng, gân chính nổi và một đầu lá khuyết nhỏ giống F01. Trên đế, lá có thể xoay quanh trục và nghiêng để xem mặt dưới. Không bẻ lá, tháo cuống hoặc mang đi.

Mặt dưới có hình tròn và mã “R17”, đặt ở vùng phẳng gần cuống. Chữ không phụ thuộc vào ánh kim lóe tại một góc duy nhất. Dấu và mã được lưu trong sổ sau khi xem. Một tem kiểm định riêng gần cuống mang dấu sóng, dùng cho E08. Phần trên không chứa chữ phụ để khiến người chơi nghĩ phải đọc thêm một mã khác.

### D03 Chuông nhỏ

D03 bắt buộc xem, ở đế phải R03. Chuông vàng đồng, thân loe, tay cầm có vòng nhỏ. Chuông có thể xoay và nghiêng, nhưng không bật mô phỏng con lắc hay cho người chơi rung bằng vật lý tự do. Một nút thử tiếng tùy chọn có thể phát A11, không có tác dụng mở khóa.

Vành đáy có một mảng phẳng mang hình vuông và mã “R23”. Vùng mảng đủ lớn để nhìn rõ khi nghiêng; không bắt nhìn vào trong tối của chuông. Âm chuông là chi tiết để nhận ra event E05, không là nguồn đáp án bắt buộc. Hình vuông và R23 cùng được lưu vào sổ. Một tem riêng ở cạnh vành mang dấu cây cho E08; không dùng dấu cây thay hình vuông trong P03.

## 7 Vật phẩm nhặt và sử dụng

| Mã | Bắt buộc | Hình dáng và nhãn | Nơi lấy và công dụng |
| --- | --- | --- | --- |
| O01 | Có | Dấu đồng nhỏ có biểu tượng hiện vật và chữ HIỆN VẬT; mặt sau có một vạch | Ngăn R03; mở B2 và áp hồ sơ hiện vật ở hộp R05 |
| O02 | Có | Dấu đồng có hình đường rẽ và chữ ĐƯỜNG ĐI; mặt sau hai vạch | B2 R04; mở bảng kỹ thuật và áp hồ sơ đường đi |
| O03 | Có | Dấu đồng có hình hai bậc và chữ TẦNG; mặt sau ba vạch | Sau bảng R05; áp hồ sơ tầng |
| O04 | Không | Máy ảnh cũ nhỏ, màn hình hoạt động, dây đeo xám, không nhãn mật mã | Kệ R01; mở chức năng chụp và album Camera |
| O05 | Có ở đoạn kết | Chìa khóa đồng đầu vòng, rãnh cổ hẹp, ba răng trùng I00 | Hộp R05; làm hiện Open trên giường R00 |

Ba dấu phân biệt bằng chữ và số vạch, không chỉ bằng màu. Khi dùng dấu, giao diện chọn item và nhấn lên cơ cấu cố định; cơ cấu xoay hoặc mở để phản hồi. Không cần animation bàn tay cầm dấu, lắp vật trong thế giới hoặc hệ thống kéo thả tự do. Mỗi dấu vẫn còn trong balo ngay sau thao tác.

Chìa khóa không mất khi mở giường. Nếu người chơi đóng balo hoặc đi khỏi hộp trước khi nhặt O05, mục tiêu chỉ dẫn vẫn nói lấy chìa khóa trong hộp; không tự đổi sang quay về phòng. Giường kiểm tra KEY_OWNED, không kiểm tra một tấm ảnh chìa khóa.

## 8 Camera và ảnh cá nhân

O04 nằm trên kệ R01, dễ thấy sau tutorial nhưng không chặn lối. Có thể nhặt trước hoặc sau F01. Máy ảnh dùng để ghi lại hình đang nhìn từ góc người chơi. Bản đầu nên chụp hình game hiện tại, tạm ẩn HUD, tâm ngắm và bảng balo trong lần chụp; không tạo cảnh 3D từ ảnh.

Đèn pin vẫn chiếu theo góc nhìn khi chụp. Máy ảnh không có flash ở bản đầu, tránh thêm một nguồn sáng vừa lộ đáp án vừa thay đổi event. Nút chụp bị khóa khi đang đọc giấy, giải cơ cấu hoặc mở album; có phản hồi ngắn “Đóng chế độ xem để chụp”. Người chơi vẫn có thể chụp hiện vật và tường từ chế độ đi lại.

Ảnh được cất trong Camera, không trộn với F01 đến F08. Mỗi ảnh có mã cá nhân C0001 tăng dần, gian chụp, thời gian trong lượt chơi, ảnh nhỏ và ảnh lớn. Người chơi có thể đặt tên ngắn, ghim, xóa hoặc so cạnh một ảnh thu thập. Xóa ảnh không xóa cờ đã xem clue hoặc vật đã nhặt. Thời điểm chụp không là mật mã.

Mức đề xuất cho bản đầu là 1280 nhân 720 pixel và tối đa 80 ảnh, dùng định dạng nén. Đây là lựa chọn cần đo hiệu năng, không phải yêu cầu khóa cứng. Khi đầy, thông báo và mở album để xóa, không ghi đè ảnh cũ âm thầm. Hết chỗ ảnh không ngăn giải game. Album và metadata được lưu cùng lượt chơi; kiểm tra dung lượng và thao tác xóa sau khi tải lại.

Không dùng nhận diện hình ảnh để biến một ảnh chụp thành đáp án. Không yêu cầu chụp đúng một frame event, ký hiệu chỉ lóe một lần hoặc chi tiết dưới một giây. Những gì camera giúp ghi nhớ đều có thể xem lại tại nguồn hoặc trong sổ. Ảnh chụp event có thể giữ thay đổi đang thấy, nhưng không tạo một tuyến kết thúc khác.

## 9 Nét nhiễu và dấu gợi phụ

N01 là ba nét bút chì đo chiều cao khung gần W06, không tạo tam giác tròn vuông hoàn chỉnh. N02 là vết ố hình nhánh nước ở R01, không cố vẽ thành chữ. N03 là ký hiệu ống gió “V2” ở R05, đi kèm mũi tên nhỏ và chữ “THÔNG GIÓ” để không bị đọc như một mã tầng. Các nét này không phát hiệu ứng khi soi đèn và không được đổi vị trí sau mỗi lượt.

Clue thật dùng ít nhất hai căn cứ: hình hoặc mã rõ và một nguồn khác chỉ cách hiểu. Nét nhiễu không được chép y nguyên biểu tượng đáp án rồi xuất hiện bên cạnh ổ khóa. Mọi dấu gợi phụ có vai trò phải có mô tả riêng, ví dụ II trên W04 gợi tầng hai. Không thêm một lớp “mọi thứ đều có thể là clue” để kéo dài thời gian.

## 10 Kiểm tra asset trước khi nhập game

Kiểm từng ảnh ở kích thước xem bình thường và khi phóng to. Ba đồ cầm trong F01 phải phân biệt được, mã B trong F03 không nhầm thành R, nét II trong F04 không giống hai vết bẩn. Kiểm cùng lúc màu, hình và chữ; không để một câu đố chỉ giải được nhờ phân biệt đỏ với xanh.

Với giấy, kiểm bản chép chữ trùng texture từng câu, kể cả dòng “nó ở đâu...”. Bản chép không được tiết lộ chữ ở mặt sau trước khi lật; sau khi đã lật có thể đọc lại cả hai mặt trong balo. Phông chữ tiếng Việt phải có đủ dấu, cùng cách viết chén, lá, chuông và các mã giữa mọi nguồn.

Với nguồn cố định, kiểm vào và ra chế độ xem, cờ ghi nhận, lưu tải và khả năng xem lại. Với đồ nhặt, kiểm rời bàn hoặc ngăn sau khi vào balo; không để item vừa nằm trên bàn vừa nhặt vô hạn. Với ba hiện vật, kiểm đáy không bị đế che, góc xoay có thể đưa cả hình và mã vào khung, và ảnh sổ đúng với model.

Không đưa texture nháp có chữ giả vào bản chơi. Nếu chưa hoàn thiện một hình, dùng bản thiết kế có chữ và hình quyết định rõ để thử câu đố trước; chỉ thay mỹ thuật khi đáp án, dấu nhận diện và khả năng đọc vẫn giữ nguyên.

## 11 Nguồn của cụm cửa niêm phong

E08 chỉ xảy ra ở R03. Chín nhóm nguồn gồm F07; D01 đến D04; I08; F08; I09; I10; W07; I11; W08. Tất cả đặt trong phòng, ngoài các ngăn khóa bởi P03. I08 đến I11 và F07 F08 có thể cất vào balo. W07 W08 là nguồn cố định, tự ghi vào sổ sau khi xem. D04 là vật đối chứng của câu đố cửa, không làm bộ ba hiện vật trong hồ sơ chính thành bộ bốn.

Các nguồn này cung cấp thông tin suy luận; cửa chỉ kiểm tổ hợp 3581 và thao tác tay gạt. Không yêu cầu chụp, không kiểm đủ số lần mở tài liệu và không đòi item từ một gian khác. I12 là phần thưởng phải nhặt cho hồ sơ chính; nếu chưa lấy, sổ chỉ rõ phiếu còn trong khay cửa.

### F07 Ảnh khai trương gian kiểm định

Ảnh rời ngang 3 trên 2, giấy màu mờ, viền trắng ngà, không khung; đặt trên kệ mở R03. Hình thấy bốn bệ chén, lá, mặt nạ, chuông và cánh cửa có bốn vòng số đang dùng. Chén gốc có vết sứt bán nguyệt rõ ở chân. Không đặt vật chắn hoặc bóng phủ vết sứt. Viền in “Khai trương gian kiểm định — 2012”. Mặt sau viết “Cửa và cụm kiểm định được đưa vào sử dụng cùng ngày.” Ảnh cho năm lắp cửa và căn cứ hình ảnh nhận diện chén gốc, không in mã mở.

### F08 Bộ sáu ảnh kiểm định

Một bảng ảnh rời có sáu ảnh in xếp hai hàng ba cột, nền giấy kem cứng, không khung. Mỗi ô có tên hiện vật, mã máy A hoặc B, ngày 14 tháng 9 năm 2016 và giờ rõ. Các ô không đánh số theo thứ tự đúng. Ô chén không sứt chân vẫn có thẻ B08 gắn cạnh vật: thẻ đã bị gắn sai, vì vậy không thể chỉ tin nhãn. Mặt sau viết “Cùng một đêm kiểm định. Giờ in là giờ của từng máy.”

| Ô từ trái sang phải theo hàng | Hình và máy | Giờ in | Chi tiết cần đọc |
| --- | --- | --- | --- |
| Trên trái | Chén, A | 21:24 | Không có vết sứt chân; bản sao |
| Trên giữa | Mặt nạ, B | 21:17 | Chụp sau báo động khi hiệu chỉnh |
| Trên phải | Lá, B | 21:09 | Mã hiện vật B17 |
| Dưới trái | Chuông, B | 21:13 | Mã hiện vật B23 |
| Dưới giữa | Chén, A | 21:19 | Có vết sứt bán nguyệt ở chân |
| Dưới phải | Mặt nạ, A | 21:23 | Vật đối chứng B31 |

F08 đặt trong ngăn không khóa G35. Chế độ xem cho phóng to từng ô và chuyển sang ô khác; tất cả vẫn là một item. Giữ nét vết sứt và thời gian ở mức xem thông thường, không dựa vào một pixel hay trí nhớ ảnh chớp.

### D04 Mặt nạ đối chứng

Mặt nạ gỗ màu kem đỏ trên đế phụ R03, chỉ xoay tại chỗ. Mặt sau có tem dấu sao và mã B31. Nó là vật đối chứng, không nằm trong bộ ba bản sao cần xác nhận ở P05. Không có số mở cửa trên mặt trước. Tem trăng của chén, sóng của lá, sao của mặt nạ và cây của chuông thuộc hệ kiểm định, được W08 đổi thành số. D04 có thể quay nhẹ ngoài tầm nhìn trong E08; tem và trạng thái đã quan sát không đổi.

### I08 Phiếu sửa khóa

Giấy ngang màu xám kem trong ngăn G35 không khóa, không khung. Mặt trước ghi “Khóa giữ bảng quy đổi dấu của ngày lắp. Trước niêm phong, người trực đặt tổ hợp theo lần kiểm định cuối của bản gốc. Đổi nhãn trưng bày không cập nhật bảng quy đổi. Xác định năm lắp bằng ảnh khai trương.” Mặt sau ghi “Cửa tự cài khi đóng mạnh. Bốn vòng số và tay gạt mở từ bên trong, đồng thời thu chốt tự cài về chế độ mở thường.” Không ghi năm 2012 hoặc 3581 trực tiếp.

### I09 Phiếu bảo dưỡng hai máy ảnh

Giấy dọc màu trắng ngà trên bàn R03, không khung. Nội dung: “Ngày 14 tháng 9 năm 2016. Máy A chạy nhanh 7 phút. Máy B chạy chậm 5 phút. Giờ của hai máy chưa được chỉnh trong đêm kiểm định.” Mặt sau có hai ví dụ thao tác không dùng giờ trong F08: “A in 20:07 thì giờ thật là 20:00. B in 19:55 thì giờ thật là 20:00.” Ví dụ làm quy tắc rõ nhưng người chơi vẫn phải xử lý sáu ảnh.

### I10 Biên bản bàn giao đã sửa

Giấy dọc vàng nhạt dưới kẹp bàn R03, không khung. Nội dung: “Ngày 14 tháng 9 năm 2016. Kiểm định cuối trước báo động. B08 chén — 21:17. B17 lá — 21:14. B31 mặt nạ — 21:16. B23 chuông — 21:18. Cả bốn là bản gốc.” Cuối giấy ký “H.”; không tự tô đỏ dòng sai. Mặt sau trống. Dòng chén được kiểm chứng bằng F07 F08 và sau đó I12. Biên bản là lời khai không đáng tin hoàn toàn, không phải giấy ngẫu nhiên chứa một mã giả để đánh lừa vô cớ.

### I11 Nhật ký báo động

Giấy nhỏ dọc trong ngăn mở gần kệ G37, không khung. Nội dung: “Ngày 14 tháng 9 năm 2016. Chuông báo động bắt đầu lúc 21:20 theo giờ chuẩn. Các ảnh sau thời điểm này thuộc lượt kiểm tra bổ sung.” Mặt sau ghi “Không trộn lượt bổ sung với danh sách kiểm định cuối trước báo động.” Giấy luôn tiếp cận được; vật rơi trong event chỉ gợi chú ý, không sinh ra hay che khóa giấy.

### I12 Phiếu vận chuyển gốc

Giấy dọc màu kem trong khay G62, chỉ lấy sau khi cửa nhận 3581. Mặt trước ghi “Ngày 14 tháng 9 năm 2016. B08 chén gốc — kiểm định 21:12. B17 lá — 21:14. B31 mặt nạ đối chứng — 21:16. B23 chuông — 21:18. Bộ ba B08 B17 B23 đi qua kho phục chế vào tuyến vận chuyển nội bộ; B31 ở lại gian kiểm định.” Mặt sau ghi “Bản lưu trước khi sửa biên bản bàn giao.” Dấu xác nhận và chữ vẫn rõ; không đưa đáp án hộp cuối, tầng hai hoặc giường vào giấy này.

I12 nối cụm cửa với vụ tráo hiện vật và là nguồn thứ 19 của hồ sơ chính. F03, I03 và các mã R vẫn cần để xác nhận ba món đang trưng bày. Không yêu cầu người chơi làm lại phép chỉnh giờ trong các gian còn lại.

### W07 Quy trình khôi phục trên cửa

Bảng kim loại cố định trên mặt trong G60, nền men kem, chữ đen, không kính và không khung rời. Chữ đầy đủ: “Khôi phục danh sách kiểm định cuối cùng trước báo động. Dùng ảnh của bản gốc. Với mỗi hiện vật, lấy lượt cuối trước báo động theo giờ chuẩn. Xếp các hiện vật theo giờ đó. Đổi dấu kiểm định mặt dưới sang số theo chuẩn lắp đặt. Đặt bốn vòng rồi gạt chốt.” Cả bảng đọc được khi cửa đóng hoặc đã mở. Mặt sau không truy cập. Không dùng chữ chìm hoặc đèn UV.

### W08 Bảng đổi dấu kiểm định

Bảng giấy cố định trong khung gỗ mỏng màu xám tại R03, không kính. Tiêu đề “DẤU KIỂM ĐỊNH”. Bảng có hàng trăng, sóng, sao, cây và hai cột ghi 2012, 2016. Các dấu vẽ cùng thiết kế với tem mặt dưới hiện vật. Mặt sau không xem được và không có clue khác.

| Dấu | Chuẩn 2012 | Chuẩn 2016 |
| --- | --- | --- |
| Trăng | 3 | 6 |
| Sóng | 5 | 2 |
| Sao | 8 | 7 |
| Cây | 1 | 4 |

Nguồn không tô sẵn cột đúng. Người chơi cần I08 và F07 để chọn 2012. Tất cả dấu có tên chữ để không phụ thuộc vào màu. Những số này chỉ thuộc cửa R03, không dùng lại cho ba đĩa P03 hoặc hộp chìa khóa.

## 12 Camera trong các event

E10 dùng B05 đã hiện diện thật trong hốc kính hành lang trước khi người chơi chụp. Ảnh Camera lưu đúng frame được chụp, không dán một người giả vào ảnh sau đó. B05 chỉ biến mất khi hốc ngoài tầm nhìn và không còn job chụp. Nếu người chơi giữ nhìn, bóng vẫn ở đó; không ép chớp đèn để che việc đổi trạng thái. Ảnh cá nhân này không là nguồn thứ 20 hoặc điều kiện của một kết thúc khác.

E04 và E08 cũng cho chụp chim hoặc mặt nạ nếu chúng đang thấy. Ảnh giấy và tranh làm bằng chứng không đổi nội dung do scare. Chỉ pose của đối tượng trình diễn, nguồn âm hoặc đồ trang trí có thể đổi theo trạng thái event đã định nghĩa.

## 13 Lời preview và dữ liệu hiện trên item

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

Dùng bảng dưới làm lời preview; dùng các mục mô tả nguồn trong chính file này để dựng chữ và hình thực tế. Ghi chú kỹ thuật, mã và điều kiện không phải lời preview để copy thẳng. Lời giải ở file 01/05 chỉ là dữ liệu thiết kế, không in trên item nếu không được quy định.

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
