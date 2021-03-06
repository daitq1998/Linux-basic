# Khái niệm về router
- **1. Nhiệm vụ của Router**
    - Router là thiết bị mạng hoạt động ở tầng thứ 3 của mô hình OSI. Router được chế tạo với hai mục đích chính là:
      - Phân tách các mạng máy tính thành các segment riêng biệt để giảm hiện tượng đụng độ giảm broadcast, hay thực hiện chức năng bảo mật
      - Kết nối các mạng máy tính hay kết nối các user với mạng máy tính ở khoảng cách xa với nhau qua các đường truyền thông
      - Đảm bảo việc truy cập các kết nối từ xa hay các kết nối WAN cho các hệ thống mạng LAN
    - *ARP Protocol (Address Resolution Protocol)*:ARP là một giao thức hoạt động dựa trên nguyên tắc: Khi một thiết bị mạng muốn biết địa chỉ MAC của một thiết bị nào đó mà nó đã biết địa chỉ mạng (IP,IPX..). Nó sẽ gửi một request bao gồm địa chỉ MAC address của nó và địa chỉ IP của thiết bị mà nó cần biết địa chỉ MAC address trên toàn bộ miền broadcast. Mỗi một thiết bị nhận được request nãy sẽ so sánh địa ip request với địa ip của tầng mạng nếu trùng địa chỉ thì thiết bị đấy phải gửi requets ngược lại cho thiết bị ARP một packet trong đó có địa chỉ MAC của mình
     - **Một số thuật ngữ cơ bản**
       - *Switching*: Quá trình chuyển dữ liệu (switching) là quá trình cơ bản của router dựa trên ARP protocol. Khi một máy muốn gửi packet qua router tới một máy tính ở mạng khác, nó gửi packet tới một router théo địa chỉ MAC của router kèm theo địa chỉ protocol (network address) của máy nhận. router sẽ xem sét các network address của máy nhậ để xem nó thuộc mạng nào, nếu router không biết được packet chuyển đi đâu thì gói tin sẽ bị bỏ (drop). Nếu router có thể chuyển các packet đến đích nó sẽ bổ sung địa chỉ MAC của máy nhận vào packet và gửi packet đi
       - *Định tuyến (Routing)*: Là các kỹ thuật tìm đường đi sao cho tối ưu nhất sao cho tốn ít băng thông nhất: Phân loại định tuyến : Định tuyến động (Routing dynamic), Định tuyến tĩnh (Routing Static)
         - Định tuyến động (dynamic Routing): Dùng các routing protocol để tự động cập nhật các router xung quanh tùy theo dạng thuật toán mà cơ chế cập nhật thông tin của các router sẽ khác nhau. Dynamic routing thường dùng trong hệ thống phức tạp hơn trong đó các router liên kết với nhau thành một mạng lưới   
         - Định tuyến tình (Static Routing): Là cơ chế trong đó người quản trị quyết định gán sẵn protocol cũng như địa chỉ đích của router : đến khi nào phải truyền qua port nào, địa chỉ là gì... Các thông tin này được chứa trong routing table và chỉ được cập nhật hoặc thay đổi bởi người quản trị. Routing static thích hợp cho hệ thống đơn giản kết nối giữa hai router trong đó đường truyền dữ liệu đã được xác đinh trước
        - Thuật toán định tuyến: gồm hai thuật toán là: link state Distance Vector
          - Link State: Được gọi là thuật toán (shortest path first) cập nhật tất cả các cơ chế routing cho tất cả các node trên hệ thống mạng mỗi routing sẽ gửi một phần của routing table, trong đó mô tả các trạng thái của các liên kết riêng của mình lên mạng. Có ưu điểm là tốc độ cao không chiếm dụng nhiều băng thông như thuật toán distance vector tuy nhiên đòi hỏi cao hơn về bộ nhớ và CPU cũng thực hiện khá phức tạp. Thuật toán này được sử dụng trong routing protocol: OSPF, NLSP
          - Distance Vector: Được gọi là thuật toán (Bellman-Ford) bắt buộc mỗi router phải gửi một phần hoặc toàn bộ router table của  mình cho router kết nối với nó theo một chu kì nhất định. Ưu điểm là dễ thực hiện dễ kiểm tra tuy nhiên có hạn chế là thời gian cập nhật lâu, chiếm dụng băng thông lớn trên mạng. Thuật toán này thường được dùng trong các routing protocol: RIP(IP/IPX), IGRP(IP), RTMP(Apple talk)... và thường áp dụng cho hệ thống mạng nhỏ
          - Ngoài ra còn kết hợp cả hai thuật toán này trong một số routing protocol: IS-IS, EIGRP
        - Metric: Là số do của thuật toán routing qua đó quyết định đường đi tối ưu nhất cho dữ liệu. Một thuật toán có thể sử dụng nhiều metric khác nhau. Các metric có thể kết hợp với nhau tạo thành một metric tổng quát. Một số metric thường dùng là :
          - Path Lenght: Là metric cơ bản thường dùng nhất. Path Lenght được xác định trên số hop nguồn và đích. Một hop được hiểu là một liên kết giữa hai router 
          - Reliability: Là khái niệm chỉ độ tin cậy của một liên kết 
          - Delay: Dùng để chỉ khoảng thời gian cần để chuyển packet từ nguồn đến đích trong hệ thống. Delay phụ thuộc và nhiều yếu tố như: Khoảng cách vật lý, băng thông liên kết, đụng độ, tranh chấp đường truyền.
          - Bandwidth: Là một metric quan trọng dùng đánh giá đường truyền. Bandwidth dùng để chỉ lưu lượng dữ liệu tối đa có thể truyền liên kết 
          - Load: nhằm để chỉ phần trăm network resourse đang trong trạng thái bận (busy). Load có thể là lưu lượng dữ liệu liên kết là độ chiếm dụng bộ nhớ 
       - **Routed protocol và routing protocol**:
         - *Routed protocol*: quy định dạng format và cách sử dụng các trường trong packet nhằm chuyển các packet từ nơi này sang nơi khác ví dụ như": IP, IPX
         - *Routing protocol*: Cho phép các router kết nối với nhau và cập nhật thông tin của nhau nhờ bảng routing. Routing protocol có thể sử dụng các routed protocol để truyền thông tin giữa các router như RIP, IGRP
     - **Một số routing protocol tiêu biểu**:
        -    | Tên | Tên đầy đủ | Routed protocol hỗ trợ |
             | --- | ---------- | ---------------------- |
             | RIP | Routing Information Protocol | TCP/IP,IPX |
             | OSPF | Open Shortest Path First | TCP/IP |
             | IGRP | Interior Gateway Routing Protocol | TCP/IP |
             | EGP | Exterior Gateway Protocol | TCP/IP |
             | BGP | Border Gateway Protocol | TCP/IP |
             | IS-IS | Intermediate System to Intermediate System | TCP/IP |
             | EIGRP | Enhanced Interior Gateway Routing Protocol | TCP/IP |
             | NLSP | NetWare Link Services Protocol | IPX/SPX |
             | RTMP | Routing Table Maintenance Protocol | Apple Talk | 
     - RIP(Routing information protocol): là giao thức đầu tiên được sử dụng. RIP dựa trên thuật toán distance vecto được sử dụng rộng rãi nhưng phud hợp cho hệ thống nhỏ và ít phức tạp. RIP tự động cập nhật thông tin router bằng cách gửi các broadcast lên mạng mỗi 30s và định tuyến đường đi bằng các hop count (path length). Số lượng hop tối đa là 15
     - IGRP(Interio gateway routing protocol): là các routing protocol được sử dụng nhiều nhất (phát triển bởi cisco) có một số đặc điểm
       - Sử dụng cơ chế advanced distance vector. Chỉ cập nhật thông tin khi có sự thay đổi cấu trúc. Xác định đường dựa trên các yếu tố như: số hop, băng thông, độ tin cậy, độ trì hoãn, có khả năng vượt quá giới hạn 15 hop, hỗ trợ nhiều đường liên kết và khả năng cân bằng tải. Linh hoạt thích hợp cho hệ thống lớn do dựa trên thuật toán linkstate và distance vector
     - OSPF: là giao thức định tuyến dự trên thuật toán tìm đường link-state có khả năng cập nhật và thay đổi routing table một cách nhanh nhất sử dụng IP multicast làm phương pháp truyền nhận thông tin, phù hợp với hệ thống lớn có nhiêu router liên kết với nhau
 - **2. Các chế dộ làm việc của Router(Router mode)**
   - **User mode**: Là chế độ đầu tiên khi khởi động bộ định tuyến là chế dộ người dùng và người dùng thực thi ở chế dộ này các câu lệnh rất hạn chế `Router>`là dấu hiệu nhận biết ở chế độ này
    - **Privileged mode(Chế độ đặc quyền)**: Nhập lệnh `enable` ở chế độ user mode để chuyển sáng chế độ Privileged. Ở chế độ này người dùng có thể xem điuọc thông tin chi tiết của toàn bộ định tuyến và là chìa khóa để vào Configuration Mode cho phép cấu hình tất cả các chức năng hoạt động của router
    - **Global Configuration Mode**: là chế độ cho phép cấu hình tất cả các router Cisco bao gồm interface, protocol, các line console, vty(telnet), tty. Các lệnh ở confuration mode ảnh hưởng trực tiếp đến cấu hình của router
       - Confuration mode có nhiều mode nhỏ, ngoài cùng là các global configuration mode sau đó là các interface configuration mode, line configuration mode, routing configuration mode.
       ![](https://github.com/daitq1998/Linux-basic/blob/master/CCNA/png/co%CC%80nig.PNG)
       ![](https://github.com/daitq1998/Linux-basic/blob/master/CCNA/png/mode.PNG)
     - **Interface Configuration mode**: Ở chế độ này cho phép người quản trị có thể cấu hình cho router về interface như FastEthernet, Serial
       - `Router>enable`
       - `Router#config terminal`
       - `Router (config)#interface Serial0`
       - `Router(config-if)#`
     - **Line Configuration mode**: ở chế độ này người quản trị có thể thay đổi bất kì với router và cpos thể kiểm soát truy cập trong router ở chế độ này 
       - `Router>enable`
       - `Router#config terminal`
       - `Router(config)#line console 0`
       - `Router(config-line)#`
