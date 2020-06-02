# Mô hình OSI
- **Mô hình OSI**
   - Gồm 7 tầng 
      - Phisical `Tầng vật lý`
      - Datalink `Tầng liên kết dữ liệu`
      - Networks `Tầng mạng`
      - Transport `Tầng giao vận`
      - Session `Tầng phiên`
      - Presentaion `Tầng trình diễn`
      - Application `Tầng ứng dụng`
  - Ý nghĩa và Đơn vị của các tầng

  |   | Mô hình 7 tầng OSI | Chức năng | Đơn vị dữ liệu | Giao thức phổ biến |
  |---|--------------------|-----------|----------------|--------------------|
  | 7 | Application | Là tầng gần nhất với người dùng. Tầng ứng dụng không phải là hệ điều hành của thiết bị nhưng nó thường cùng cấp các dịch vụ email (SNMP & POP3), trình duyệt web( HTTP) và dịch vụ chuyển tệp (FTP) | Data | HTTP, FTP, TFTP, telnet, SNMP, DNS |
  | 6 | Presentation | Là tầng trình bày dữ liều chuyển tới tầng Application, nhiều phương tiện làm việc ở đây như MP4, JPEG, GIF chức nằng mã hóa giải mã dữ liệu cũng có ở lớp này | Data | Video(WMV, AVI, MP4) Bitmap(JPG, BMP, PNG) Audio(MP3, WAV, WMA) |
  | 5 | Session | Vai trò của tầng Session là cài đặt, quản lý, và chấm dứt các phiên hoặc đối thoại giữa các thiết bị. chúng diễn ra trên các liên kết logic và điều thực sự xảy ra là sự kết hợp của hai ứng dụng phần mềm. SQL, RPC và NFS đều hoạt động ở Lớp phiên | Data | SQL, RPC, NETBIOS |
  | 4 | Transport | Dòng điều khiển buffering, windowing, congestion avoidance. Giúp ngăn ngừa sự mất mát của các phân đoạn trên mạng và sự cần thiết phải truyền lại  Đây là tầng được đánh giá cao nhất có sự liên quan giữa việc trao đổi dữ liệu giữa các hệ thống mở | Segment | TCP (Transmission Control Protocol ), UDP (User Datagram Protocol) |
  | 3 | Networks | Xác định đường dẫn, Địa chỉ logic nguồn và đích | Packet, Datagram| IP, IPX, Apple talk |
  | 2 | Data link | Gồm các địa chỉ vật lý, Bao gồm 2 lớp:  Kiểm soát liên kết logic Logical Link control (LLC) và Kiểm soát truy cập phương tiện Media access control (MAC) | Frame | LAN và WAN(HDLC, PPP, Frame Relay) |
  |1 | Physical | Mã hóa truyền các bit dữ liệu: Tín hiệu điện và tín hiệu vô tuyến điện | Bit | FDDI, Ethernet |
  - **Mô hình TCP/IP**
    - Mô hình TCP/IP là một khung khác và thay thế cho mô hình OSI. Mô hình TCP/IP gồm 5 lớp. 
      - Bao gồm:
        |   | Mô hình 5 tầng TCP/IP | Giao thức phổ biến |
        |---|-----------------------|--------------------|
        | 5 | Applycation | Telnet, FTP, DNS, RIP, HTTP |
        | 4 | Transport/Host to host | TCP, UDP, ICMP |
        | 3 | Network | IPSec, IP |
        | 2 | Data Link | Ethernet, Frame Relay, PPP |
        | 1 | Link, Network interface, Physical | Bit on the wire |
      - Mô hình TCP/IP của và mô hình TCP/ip cũ đã thay đổi như thế nào :
        | Mô hình TCP/ip cũ | Layer | Mô hình TCP/IP mới |
        |-------------------|-------|--------------------|
        | Application | 5 | Application | 
        | Transport | 4 | Transport |
        | Internet | 3 | Network | 
        | Link/Network interface | 2 | Data link |
        |  | 1 | Physical |
      - Khái niệm về TCP/IP: TCP là một bộ hoàn chỉnh các giao thức và dịch vụ cho phép giao tiếp diễn ra trên mạng. TCP/IP là bộ tiêu chuẩn có sẵn và được sử dụng miễn phí được duy trì bởi Lực lượng đặc nhiệm kỹ thuật Internet (IETF) à được sử dụng để kết nói thiết bị đầu cuối   
      - Một số giao thức phổ biến thường dùng
       - **Transmission Control Protocol (TCP)**: TCP hoạt động ở tầng vận chuyển của mô hình OSI. TCP có khả năng truyền và nhận dữ liệu cùng một lúc — song công (full-duplex). Tính năng phục hồi dữ liệu bị mất trên đường truyền.Nó cung cấp một dịch vụ hướng kết nối để truyền dữ liệu đáng tin cậy giữa các thiết bị mạng. TCP cũng cung cấp kiểm soát luồng tuần tự, cửa sổ và phát hiện lỗi. Các cổng của TCP: 
       - **FTP Data: 20**
       - **FTP Control: 21**
       - **SSH: 22**
       - **Telnet: 23**
       - **SMTP: 25**
       - **DNS: 53**
       - **HTTP: 80**
       - **POP3: 110**
       - **NNTP: 119**
       - **NTP: 123**
       - **TLS/SSL: 443**
      - **Internet Protocol (IP)**: là giao thức hoạt động ở lớp mạng của mô hình OSI. Nó không kết nối và vận chuyển dữ liệu qua mạng, Địa chỉ IP là một giao thức của Internet. kiểm tra IP địa chỉ lớp mạng của mỗi gói và xác định đường dẫn tốt nhất để mỗi gói đến đích. 
      - **User Diagram Protocol (UDP)**: UDP hoạt động ở lớp vận chuyển của mô hình OSI. Nó vận chuyển thông tin giữa các thiết bị mạng. Không giống như TCP, không có kết nối nào thiết lập được trước tiên. UDP là không kết nối cung cấp nỗ lực tốt nhất và không đảm bảo dữ liệu không đến đích. UDP không quan tâm tới việc có gửi chính xác gói tin tới đúng địa chỉ hay không, không có cơ chế phục hồi dữ liệu bị mất. Giao thức UDP nhanh và hiệu quả hơn đối với các mục tiêu kích thước nhỏ và yêu cầu khắt khe về thời gian. Bản chất không trạng thái nên UDP hữu dụng đối với việc trả lời các truy vấn nhỏ với số lượng lớn người yêu cầu. UDP tiêu thụ ít băng thông hơn TCP phù hợp với các ứng dụng có độ trễ thấp. Các cổng của UDP :
      - **DNS: 63**
      - **TFTP: 69**
      - **SNMP: 167/162**
      - **File Transfer Protocol (FTP)**: là giao thức truyền file FTP hoạt động ở tầng ứng dụng và chịu trách nhiệm vận chuyển dữ liệu đáng tin cậy qua một liên kết từ xa. Bởi vì FTP sử dụng TCP để truyền dữ liệu. FTP có thể gỡ lỗi lưu lượng bằng lệnh ip ftp. FTP sử dụng cổng 20 và 21. Với giao thức FTP các máy Client trong mạng có thể kết nối tới các máy FTP để gửi và lấy dữ liệu. Người dùng có thể truy cập vào máy chủ FTP đề truyền và nhận dữ liệu từ xa
      - **Trivial File Transfer Protocol (TFTP)**: TFTP là một giao thức truyền file đơn giản cho phép client có thể upload hoặc dowload các tệp tin remote host như swith, router, server. TFTP chỉ đọc và ghi tệp từ các máy chủ từ xa. Do không được bảo mật trong quá trình truyền tệp nên TFTP thường được ứng dụng trong mạng cục bộ (LAN) để backup, import config IOS trên các thiết bị switch router firewall, hoặc cài đặt license cho các thiết bị này.TFTP sử dụng giao thức UDP làm giao thức truyền tải và sử dụng cổng 69 làm cổng mặc định 
      - **Simple Mail Transfer Protocol (SMTP)**: SMTP Là giao thức chuẩn TCP/IP được dùng để truyển tải thư điện tử (e-mail) trên Internet. Nó thiết lập mail client và mail server và thiết lập giữa mail gửi và mail nhận. Email sẽ được dẩy từ mail client lên mail server và từ mail server sẽ được server này gửi đi đến mail server nhận và POP3 là một giao thức để làm điều này. SMTP sử dụng cổng TCP 25
      - **Hyper Text Transfer Protocol (HTTP)**: Là giao thức truyền tải siêu văn bản, HTTP sử dụng cổng TCP 80 để fuwir các tệp văn bản đồ họa và các tệp khác từ máy chủ đến máy khách. Giao thức này cho phép bạn xem các trang web ả nó nằm ở tầng úng dụng của mô hình OSI. HTTPS và phiên bản  bảo mật của HTTP. Nó sử dụng lớp cổng bảo mật (**Secure Sockets layers "SSL"**) để mã hóa dữ liệu lúc truyền tải nhằm gia tăng tinh an toàn cho việc truyền dữ liệu giữa web Server và trình duyệt web. Có thể sử dụng lệnh debug ip http để gỡ lỗi lưu lượng HTTP
      - **Telnet**: sử dụng cổng 23 để cho phép kết nối từ xa đến các thiết bị mạng. Tuy nhiên Telnet không an toàn nên không được sử dụng phổ biến nên đa số sử dụng SSH (Secure shell) sử dụng cổng TCP 22 như một giải pháp  thay thế và kết nối an toàn 
      - **Internet Control Message Protocol (ICMP)**: ICMP là một giao thức được sử dụng để báo cáo vấn đề hoặc sự cố với các gói IP (hay diagram) trên mạng. ICMP là một yêu cầu cho bất kì nhà cung cấp nào muốn sử dụng ip trên mạng của họ. khi xảy ra sự cố với gói IP gói IP bị hủy và các thông báo ICMP được tạo và gửi đến máy chủ khởi tạo gói. Việc sử dụng ICMP phổ biến nhất là để gửi các gói ping để kiểm tra các kết nối mạng của các máy chủ từ xa 
      - **Traceroute**: Là một cơ sở được sử dụng rộng rãi có thể kiểm tra các kết nối mạng và là công cụ tiện dụng để đo lường và quản lý. Traceroute theo dõi các gói tin IP đích bằng cách gửi gói tin UDP với trường TTL tối đa nhỏ sau đó lắng nghe phản hồi vượt quá thời gian của ICMP khi các gói traceroute tiến triển các bản ghi được hiển thị bởi các hop
      | Tên | Tên đầy đủ | Routed protocol hỗ trợ |
      |-----|--------------|----------------------|
      | RIP | Routing Information Protocol | TCP/IP,IPX |
      | OSPF | Open Shortest Path First | TCP/IP |
      | IGRP | Interior Gateway Routing Protocol | TCP/IP |
      | EGP | Exterior Gateway Protocol | TCP/IP |
      | BGP | Border Gateway Protocol | TCP/IP |
      | IS-IS | Intermediate System to Intermediate System | TCP/IP |
      | EIGRP | Enhanced Interior Gateway Routing Protocol | TCP/IP |
      | NLSP | NetWare Link Services Protocol | IPX/SPX |
      | RTMP | Routing Table Maintenance Protocol | Apple Talk | 
