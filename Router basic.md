# Khái niệm về router
- **1. Nhiệm vụ của Router**
    - Router là thiết bị mạng hoạt động ở tầng thứ 3 của mô hình OSI. Router được chế tạo với hai mục đích chính là:
      - Phân tách các mạng máy tính thành các segment riêng biệt để giảm hiện tượng đụng độ giảm broadcast, hay thực hiện chức năng bảo mật
      - Kết nối các mạng máy tính hay kết nối các user với mạng máy tính ở khoảng cách xa với nhau qua các đường truyền thông
      - Đảm bảo việc truy cập các kết nối từ xa hay các kết nối WAN cho các hệ thống mạng LAN
     *ARP Protocol (Address Resolution Protocol)*:ARP là một giao thức hoạt động dựa trên nguyên tắc: Khi một thiết bị mạng muốn biết địa chỉ MAC của một thiết bị nào đó mà nó đã biết địa chỉ mạng (IP,IPX..). Nó sẽ gửi một request bao gồm địa chỉ MAC address của nó và địa chỉ IP của thiết bị mà nó cần biết địa chỉ MAC address trên toàn bộ miền broadcast. Mỗi một thiết bị nhận được request nãy sẽ so sánh địa ip request với địa ip của tầng mạng nếu trùng địa chỉ thì thiết bị đấy phải gửi requets ngược lại cho thiết bị ARP một packet trong đó có địa chỉ MAC của mình
     - **Một số thuật ngữ cơ bản**
     
