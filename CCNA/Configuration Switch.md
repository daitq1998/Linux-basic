# SWitching basic

**CSMA/CD(Carrier Sense, Multiple Access with Collision Detection)**: Có nghĩa là đa truy nhập nhận biết sóng mang phát hiện sung đột, là phương pháp truy cập hay sử dụng trong mạng LAN cải thiện từ phương pháp CSMA. Phương pháp này được hiểu như là: Khi một máy tính muốn truyền gói tin trước tiến nó sẽ lắng nghe xem đương truyền có tín hiệu hay không( có sóng mang) bằng cách lắng nghe tín hiệu của Carrier. Nếu khống có các gói tin sẽ được truyền theo các frame. Sau khi truyền gói tin nó vẫn tiếp tục lắng nghe xem có máy nào định truyền tin hay không. Nếu không có xung đột thì máy sẽ truyền các gói tin đến hết, nếu phát hiện xung độ nó sẽ gửi broadcast một gói tin và báo báo hiệu cho các máy không nên gửi để tránh làm nhiễu đường truyền. Sau đó chờ một khoảng thời gian trước khi tiến hành gửi lại gói tin
  
    Tiến trình gồm các bước:
