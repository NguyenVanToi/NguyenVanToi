#e. Các công cụ
<a name = ""></a>
##1. Wizard
- Wizard: Tạo 1 cấu hình mới để quét trang web mục tiêu.
- Khi bấm Wizard  trên thanh công cụ một cửa sổ mới sẽ hiện ra.

- Bạn sẽ chọn wizard từ cửa sổ:
	Infrastructure wizard(wizard cơ sở): thuật sĩ này sẽ tạo cho bạn 1 cấu hình quét với mục đích nào đó để xác định cơ sở hạ tầng 		trang Web mục tiêu.
	Short wizard: 1 thuật sĩ demo nhỏ để lấy mã GUI.
-  Tiếp tục chọn Run the Wizard: Bạn điền URL mục tiêu và chọn Next.
-  Sau đó bấm Next để cài đặt cho cấu hình mới. Cuối cùng là điền tên và mô tả về cấu hình mới sau đó bấm save.

<a name = ""></a>
##2.  Manual request (nhãn yêu cầu).
- Công cụ này cho phép bạn gửi yêu cầu đến HTTP.

<img src = "http://docs.w3af.org/en/latest/_images/manual-http.png">

- Mở manual request cửa sổ mới hiện ra: hiển thị yêu cầu HTTP và đáp ứng lại của HTTP(mỗi phần đều có raw(nguyên văn) và header(tiêu đề)).
- Bạn cũng có thể chỉnh sửa yêu cầu. Khi đã sẵn sàng chọn Send
- Sau đó sẽ nhận được hồi đáp ở phần Response.

<a name = ""></a>
##3. Fuzzy request (yêu cầu mờ)
- Công cụ này cho phép bạn gửi được nhiều yêu cầu đến HTTP một cách dễ dàng và kiểm soát được nó.
- Khi bạn tạo ra một yêu cầu, tất cả các văn bản được gửi đến đích, ngoại trừ những phần được bên trong hai dấu  $. Văn bản này được sử dụng bởi hệ thống để tạo ra một “máy phát  mờ”, mà nó sẽ tiêu thụ tạo ra nhiều yêu cầu.

- VD:  Nếu bạn đặt một văn bản giữa hai dấu $ mà tạo ra ba mục, bạn sẽ tạo ra ba yêu cầu, và sẽ có được ba hồi đáp. Bạn có thể đặt nhiều máy phát  mờ như bạn muốn, và hệ thống sẽ tạo ra nhiều yêu cầu sử dụng tất cả các kết hợp có thể. Vì vậy, nếu bạn giữ cho máy phát  đầu tiên (mà tạo ra ba mục), và chèn một cái mới mà tạo ra năm mục, hệ thống sẽ tạo 3 x 5 = 15 yêu cầu.

- Hệ thống này sẽ tạo ra các mục khác nhau bằng cách sử dụng văn bản giữa các dấu `$`, sử dụng trực tiếp `eval ()`, với một không gian gần như sạch (chỉ có các mô-đun chuỗi đã nhập khẩu). Không có cơ chế bảo mật trong việc đánh giá này. Sử dụng đánh giá này, ví dụ, bạn có thể làm:
	Số 0-4: `$ phạm vi (5) $`
	Mười kí tự đầu lá thư: `$ string.lowercase [: 10] $`
	Những từ spam và : `$` [ 'spam', 'egg'] `$`
	Các nội dung của một tập tin: `$ [l.strip () cho l trong tập tin ("INPUT.TXT ')] $`

- Kiểm tra có bao nhiêu yêu cầu hệ thống tạo ra, bằng  nút Analyze [3].  Ngoài ra, nếu bạn đánh dấu vào hộp kiểm Preview [4] sẽ cho bạn thấy nội dung của chúng trong một cửa sổ pop up mới.

<img src = "http://docs.w3af.org/en/latest/_images/fuzzy.png">

- Bạn có thể sử dụng Play và Stop [5] để gửi yêu cầu. Ngoài ra, bạn có thể xem yêu cầu nào đang thực hiện ở Throbber [6].

- Nút [9] để gửi yêu cầu hoặc phản ứng với các yêu cầu cụ bằng tay hoặc công cụ so sánh,  nút Clear [A] sẽ xóa tất cả các kết quả, và một Cluster (Cụm) Responses [B] sẽ gửi tất cả các câu trả lời các công cụ cluster (lưu ý rằng công cụ này là chỉ có thể truy cập qua ở đây, vì nó chỉ có ý nghĩa để sử dụng nó từ nhiều tạo ra phản ứng).

- Các công cụ Responses Cluster phép bạn phân tích tất cả các câu trả lời khi nhìn thấy đồ họa  chúng khác với nhau. Các biểu đồ sẽ cho bạn thấy những câu trả lời, và khoảng cách giữa chúng cho một phân tích tốt hơn.

-Ngoài ra bạn có các nút khác nhau giúp bạn xem đồ thị tốt hơn: phóng to, thu nhỏ, phù hợp với tất cả các đồ thị trong cửa sổ, và hiển thị các đồ thị trong các kích thước ban đầu.
##4. Encode and Decode
- Công cụ này cho phép bạn áp dụng một số chức năng mã hóa và giải mã trong văn bản mà bạn muốn.

<img src = "http://docs.w3af.org/en/latest/_images/encode-decode.png">

- Bạn có thể đưa các văn bản để mã hóa ở ô bên trên [1] bấm [3], và khi mã hóa sẽ xuất hiện trong cửa sổ bên dưới [2], và ngược lại: để giải mã một cái gì đó đưa văn bản vào khung bên dưới  rôi bấm [4] và sau khi giải mã nó sẽ xuất hiện ở phía trên cửa sổ.

- Bạn có chức năng mã hóa và giải mã sau đây:
	0xFFFF Encoding: phương pháp mã hóa 0x
	Base64 Mã hóa / Giải mã: Mã hóa và giải mã sử dụng Base64
	Double Nibble Hex Encoding: Đây là dựa vào phương pháp mã hóa hex tiêu chuẩn. Mỗi giá trị niibble thập lục phân được mã hóa bằng cách 			sử dụng mã hóa hex tiêu chuẩn
	Double Percent Hex Encoding: Đây là dựa trên các phương pháp thông thường mã hóa hex.Tỷ lệ này được mã hóa bằng cách sử dụng mã hóa 			hex tiếp theo là giá trị 16 byte được mã hóa
	Double URL Encode / Decode: Mã hóa và giải mã  đôi URL mã hóa.
	First Nibble Hex Encoding: Tương tự như tăng gấp đôi mã hóa hex nibble. Sự khác biệt là chỉ nibble đầu tiên được mã hóa
	HTML Escape / unescape: Mã hóa và giải mã HTML  thoát
	Hex Encoding / Decoding: Đây là một trong những cách RFC compliamt cho mã hóa một URL. Đây cũng là phương pháp đơn giản để mã hóa 			URL. Các phương pháp mã hóa bao gồm thoát một giá trị 16 byte cho mã hóa với 1%
	MD5 Hash: Mã hóa bằng MD5
	MS SQL Encode: Chuyển đổi văn bản đến một lệnh MS SQL  Microsoft% U Encoding: này trình bày một cách khác nhau để mã hóa các giá trị 			điểm mã Unicode lên đến 65.535 (hoặc hai byte). % U trước 4 giá trị nibble hệ 16 đại diện cho các giá trị điểm mã Unicode
	MySQL Encode: Chuyển đổi văn bản đến một lệnh MySQL 
	Random Lowercase: Thay đổi ký tự ngẫu nhiên của chuỗi sang chữ thường
	Random Uppercase: Thay đổi ký tự ngẫu nhiên của chuỗi sang chữ hoa
	SHA1 Hash: Mã hóa sử dụng SHA1
	Second Nibble Hex Encoding: Tương tự như tăng gấp đôi mã hóa hex nibble. Sự khác biệt là chỉ nibble thứ hai là mã hóa
	Encode URL / Decode : Mã hóa và giải mã URL mã hóa
	UTF-8 Barebyte Encoding: Chỉ cần một mã hóa bình thường UTF-8
	UTF-8 Endode:  Lưu ý rằng các giá trị thập lục phân được hiển thị với 1%.
## Comparing HTTP traffic
- Với công cụ này bạn sẽ có thể so sánh các yêu cầu khác nhau và hồi đáp.

- Trong công cụ này tất cả các thông tin được nối trong cùng một văn bản, để dễ dàng so sánh, nhưng bạn có nút [1] để kiểm soát một phần của thông tin xuất hiện trong văn bản: tiêu đề yêu cầu, nội dung yêu cầu , tiêu đề hồi đáp và nội dung hồi đáp.

- Việc so sánh được thực hiện giữa các yêu cầu / hồi đáp ở bên trái [2], và bất cứ yêu cầu / hồi đáp, bạn có ở bên phải [3]. Công cụ này được chuẩn bị để xử lý nhiều hơn so với hai yêu cầu / hồi đáp: bạn sẽ luôn luôn có một yêu cầu / hồi đáp ở bên trái, và tất cả các yêu cầu / hồi đáp mà bạn đã thêm vào ở bên phải. Để xem chính xác những gì bạn đang so sánh, hệ thống hiển thị bạn mỗi id [4].

<img src = "http://docs.w3af.org/en/latest/_images/compare-tool.png">

- Bạn có thể chọn các yêu cầu / hồi đáp mà bạn đã thêm so sánh với một ở bên phải [5]. Nếu bạn muốn thay đổi các yêu cầu / hồi đáp đó là ở bên trái, bạn có thể đặt nó bằng cách sử dụng văn bản nút Set [6] để so sánh. Bạn có thể xóa bất kỳ yêu cầu / phản ứng ở bên phải bằng cách sử dụng nút Delete [7], hoặc xóa tất cả chúng với Clear All [8].

- Các yêu cầu cũng có thể được gửi từ công cụ này để yêu cầu bằng tay hoặc yêu cầu những yêu cầu mờ, sử dụng các nút trên các văn bản [9]. Ngoài ra còn có một nút [A] để gửi tất cả các hồi đáp ở các quyền công cụ Responses Cluster.

##6. Using the Proxy
- Công cụ này là một proxy nó nghe một cổng trong máy bạn đang chạy chương trình w3af. Bạn có thể cấu hình bất kỳ chương trình mà vấn đề yêu cầu HTTP (như trình duyệt internet của bạn, ví dụ) để sử dụng proxy.

- Khi chương trình này yêu cầu các vấn đề khác, các proxy nắm bắt nó và bạn thấy nó ở [1]. Bạn có thể chọn để giảm yêu cầu này ở nút Drop [2], hoặc để yêu cầu tiếp tục. Nếu bạn chọn sau, bạn có thể chỉnh sửa theo yêu cầu như bạn muốn, và sau đó nhấn vào nút Gửi [3].

<img src = "http://docs.w3af.org/en/latest/_images/proxy.png">

- Vì vậy, hệ thống sẽ gửi yêu cầu, và nắm bắt các hồi đáp khi đến, và sẽ hiển thị nó cho bạn tại cửa sổ [4] ngay. Sau khi phân tích các hồi đáp , bạn có thể nhấp vào nút Tiếp theo [5] và chuẩn bị để nắm bắt những yêu cầu HTTP tới.

- Để làm việc với các yêu cầu HTTP và hồi đáp bạn ở nút [6] để gửi thông tin đến các công cụ khác. Ngoài ra bạn có một cửa sổ Lịch sử [7] cho phép bạn tìm kiếm trên tất cả các yêu cầu và trả lời.

- Trong thanh công cụ [8] bạn có một nút Activate để kiểm soát nếu proxy được kích hoạt hay không, một yêu cầu nút Trap đó sẽ xác định nếu các proxy là để cho các yêu cầu đi qua mà không có thủ tục giải thích ở trên, và một nút Configuration(tham khảo thêm [Certificate authority configuration](http://docs.w3af.org/en/latest/ca-config.html)).

*Nguồn* : http://docs.w3af.org/en/latest/gui/index.html

