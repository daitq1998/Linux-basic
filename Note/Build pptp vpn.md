# Giới thiệu về pptp và vpn
- **PPTP**:(Point-to-point Tunneling protocol là một mở rộng của ppp nó đóng gói các tin ppp vào gói tin ip (ip datagram)để truyền đi trên mạng công cộng Internet
  -  Một người dùng từ xa muốn nối với một mạng LAN cộng tác từ một vị trí mà bình thường là phải sử dụng đến một cuộc quay số đường dài, thay vì vậy người dùng nối kết vào ISP tại địa phương. Sau đó thiết lập một liên kết ảo băng qua Internet để đến mạng LAN nầy. Như vậy, chỉ cần tạo ra một liên kết cục bộ và người dùng có thể có được một nối kết đường dài thông qua Internet. Việc xác thực quyền và mã hóa có thể yêu cầu thêm trong các phiên quay số ảo để hỗ trợ các nối kết riêng tư hay bảo mật.
- **VPN**:(virtual private network):là mạng riêng ảo là một mạng dành riêng để kết nối các máy tính lại với nhau thông qua mạng internet công cộng. Những máy tính tham gia mạng riêng ảo sẽ kết nối lại với nhau như trong một mạng LAN. VPN cho phép các máy tính truyền thông với nhau thông qua một môi trường chia sẻ như mạng Internet nhưng vẫn đảm bảo được tính riêng tư và bảo mật dữ liệu.
# Cài đặt và cấu hình PPTP VPN trên server
- **Cài đặt PPTP: 
- Để cài đặt PPP:`sudo apt-get install pptpd`
- **Cấu hình PPTP**
- Để cấu hình PPTP vào file :`pptpd.conf` trong thư mục `/etc/` thêm địa chỉ ip của local vào dòng `localip`: và `remoteip` là dải ip mà bạn muốn chỉ định ![](
- Tiếp theo thêm user và password với định dang : `[username] [service] [password] [ip]` vơi dịch vụ này là `pptpd`![](
- Sau đó chỉnh sửa file `sysctl.conf`:sửa dòng `net.ipv4.ip_forward=1` và sysctl -p để apply
- Thêm DNS server trong file `/etc/ppp/pptpd-option` và change ![](
- Sau đó cấu hình firewall cho ip  Masquerading:`iptables -t nat -A POSTROUTING -s 192.168.122.0/24 -o eth0 -j MASQUERADE` Và `iptables -A FORWARD -p tcp --syn -s 192.168.122.0/24 -j TCPMSS --set-mss 1356` và restart lại pptpd
# Cài đặt và cấu hình PPTP VPN trên Client
-`sudo apt-get install pptp-linux`
