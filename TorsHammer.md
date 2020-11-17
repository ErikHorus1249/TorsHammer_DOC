
## I. Công cụ sử dụng
Torshammer là một công cụ DoS slow-rate HTTP POST (Layer 7) được tạo bởi phiral.net. Xuất hiện công khai đầu tiên của công cụ này là vào đầu năm 2011.
### 1. Nguyên lý
Torshammer thực hiện một cuộc tấn công DoS bằng cách sử dụng một cuộc tấn công classic slow POST attack , trong đó các trường POST HTML được truyền với tốc độ chậm trong cùng một phiên (tốc độ thực tế được chọn ngẫu nhiên trong giới hạn 0,5-3 giây).
![](https://i.imgur.com/xtTpAsD.png)
Tương tự như R.U.D.Y trước đây. (R-U-Dead-Yet), cuộc tấn công  slow POST attack, khiến các luồng ứng dụng máy chủ web phải chờ kết thúc các bài đăng vô hạn để xử lý chúng. Điều này gây ra sự cạn kiệt tài nguyên của máy chủ web và khiến nó rơi vào trạng thái từ chối dịch vụ đối với bất kỳ lưu lượng truy cập hợp pháp nào.

Một chức năng mới được thêm vào Tor's Hammer là khả năng ẩn danh lưu lượng truy cập. DoS một ttacks có thể được thực hiện thông qua Mạng Tor(Tor Network) bằng cách sử dụng một socks proxy  được tích hợp trong các máy khách Tor. Điều này cho phép khởi động cuộc tấn công từ các địa chỉ IP nguồn ngẫu nhiên, khiến việc theo dõi kẻ tấn công gần như không thể

Mặc dù khó theo dõi, Radware có thể vô hiệu hóa cuộc tấn công dựa trên Tor's Hammer và nhiều dạng tấn công DoS khác. Tìm hiểu thêm về cách bảo vệ trang web của bạn tại đây.

Slow rate 
Định nghĩa :

Trong một cuộc tấn công Slow Post DDoS, kẻ tấn công sẽ gửi các header HTTP POST hợp pháp đến máy chủ Web. Trong các theader này, kích thước của nội dung (message body) theo sau được chỉ định chính xác. Tuy nhiên, nội dung tin nhắn được gửi đi với tốc độ rất thấp. Những tốc độ này có thể chậm đến một byte sau mỗi hai phút.

Vì message  được xử lý bình thường, máy chủ bị tấn công sẽ cố gắng hết sức để tuân theo các quy tắc được chỉ định. Máy chủ sau đó sẽ chậm xử lý các yêu cầu chậm hơn. Vấn đề sẽ nghiêm trọng, khi những kẻ tấn công khởi chạy hàng trăm hoặc thậm chí hàng nghìn cuộc tấn công Slow POST cùng một lúc, tài nguyên máy chủ sẽ bị tiêu hao nhanh chóng, khiến các kết nối hợp pháp không thể đạt được.

Dấu hiệu :

Các cuộc tấn công Slow Post được đặc trưng bởi việc truyền các resquest  header post HTTP nhắm mục tiêu đến các máy chủ web dựa trên luồng, gửi dữ liệu cực kỳ chậm(extremely slowly), nhưng không chậm đến mức khiến máy chủ hết thời gian chờ. Bởi vì máy chủ giữ kết nối mở để đề phòng dữ liệu bổ sung, người dùng bị ngăn truy cập vào máy chủ. Các máy chủ có một số lượng lớn các máy khách được kết nối nhưng tải xử lý thực tế sẽ rất thấp.

Nguy hiểm :

Vì các cuộc tấn công Slow Post không yêu cầu băng thông rộng, chẳng hạn như cần thiết với các cuộc tấn công brute-force DDoS , chúng có thể khó phân biệt với lưu lượng truy cập thông thường. Vì các kiểu tấn công lớp ứng dụng này không yêu cầu nhiều tài nguyên, chúng có thể được kích hoạt từ một máy tính, khiến chúng rất dễ khởi chạy và khó giảm thiểu.

HTTP chậm là các cuộc tấn công Từ chối Dịch vụ (DoS) của lớp ứng dụng và có khả năng đánh sập một máy chủ có tài nguyên hạn chế. Do bản chất của cuộc tấn công (tốc độ chậm và âm lượng thấp), chúng khó bị phát hiện và có thể gây ra thiệt hại tương đương với DDoS khối lượng lớn. Trong bài đăng này, tôi sẽ chia sẻ kinh nghiệm của mình với những cuộc tấn công này
	

