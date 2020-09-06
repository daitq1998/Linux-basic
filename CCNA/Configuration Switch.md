# SWitching basic

**Switch**: Là thiết bị chuyển mạch quan trọng trong mạng dùng để kết nối các đoạn mạng với nhau theo mô hình sao. Có nghĩa là tất cả các má ttinhs đều đc kết nối về đây từ đó tạo tuyến đường và chuyển dữ liệu đi. Swith có khả năng nhận dạng má đc kết nối thông qua địa chỉ MAC qua các nguồn trong frame nó nhận đc

**CSMA/CD(Carrier Sense, Multiple Access with Collision Detection)**: Có nghĩa là đa truy nhập nhận biết sóng mang phát hiện sung đột, là phương pháp truy cập hay sử dụng trong mạng LAN cải thiện từ phương pháp CSMA. Phương pháp này được hiểu như là: Khi một máy tính muốn truyền gói tin trước tiến nó sẽ lắng nghe xem đương truyền có tín hiệu hay không( có sóng mang) bằng cách lắng nghe tín hiệu của Carrier. Nếu khống có các gói tin sẽ được truyền theo các frame. Sau khi truyền gói tin nó vẫn tiếp tục lắng nghe xem có máy nào định truyền tin hay không. Nếu không có xung đột thì máy sẽ truyền các gói tin đến hết, nếu phát hiện xung độ nó sẽ gửi broadcast một gói tin và báo báo hiệu cho các máy không nên gửi để tránh làm nhiễu đường truyền. Sau đó chờ một khoảng thời gian trước khi tiến hành gửi lại gói tin

CSMA/CA: Tránh xung đột và CSMA/CD: phát hiện xung đột, và sử dụng ACK để xác nhận thay vì tùy ý sử dụng môi trường truyền khi có xung đột xảy ra việc sử dụng ACK rất đơn giản khi một thiết bị không giây gửi gói tin, đầu nhận sẽ đáp lại bằng ACK nếu như gói tin đó được nhận đúng và đầy đủ, nếu đâu kia không nhận được ACK thì xem ra nó đã có xung đột xảy ra và phải truyền lại gói tin

**Collision and Broadcast domains**: Miền xung đột là các đoạn mạng Ethernet hay Fast Ethernet nằm giữa một cặp bridge hay các thiết bị lớp 2 khác. Tring miền xung đột thiết bị gửi tín hiệu đến hub thì tất cả các thiêt bị đều nhận được. Các Hub mở rộng Collision domain còn các switch tạo ra các Collision domain

![](https://github.com/daitq1998/Linux-basic/blob/master/CCNA/png/collision%20domain.png)

**Broadcast domains**: gọi là miền quảng bá nó là một vùng trong đó thông tin được gửi tới tất cả các thiết bị được kết nối. Thiết bị giới hạn bởi các mền quảng bá là các router và cũng chính rouer tạo ra các miền quảng bá. Và như vậy mối router sẽ là một Broadcast domain một broadcast domains gồm nhiều Collistion domains

![](https://github.com/daitq1998/Linux-basic/blob/master/CCNA/png/Collision%20and%20broadcast%20domain.png)

# Configuration Switch
  **Câu lệnh cơ bản**: Để kết nối tới một switch có thể kết nối qua cổng console hay trên một chiếc máy tính
  ![](https://github.com/daitq1998/Linux-basic/blob/master/CCNA/png/M%E1%BB%99t%20s%E1%BB%91%20c%C3%A2u%20l%E1%BB%87nh%20show.jpg)
  Câu lệnh `show vesion`: Là lệnh dùng để show ra các thông tin của switch đó bao gồm 
  
   - Địa chỉ MAC
   - Version sw ..
   
   Để thay đổi tên switch sử dụng lênh : `Switch(config)#hostname TTY`
   
   VTY là các cổng ảo trên các thiết bị router và switch để truy cập từ xa với các giao thức telnet, ssh. Các cổng đấy bị đóng khi người quản trị xác thực cấu hình phương thức cho các dòng vty, khi cấu hình vty ta thấy có các cổng từ 0-4 hay 0-15
# Virtual Local Area Networks (VLAN)
  VLAN(Virtual Local Area Networks)
