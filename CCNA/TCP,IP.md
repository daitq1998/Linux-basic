# 1. Giới thiệu về IP
   Địa chỉ IP là một địa chỉ dùng để định danh cho một số đối tượng trong mạng. Các đối tượng có thể là máy tính, điện thoại, máy in, camera gọi là các thiết bị cuối "end-user" ha là các host.
 - Một địa chỉ ip gồm hai phần là: `Network.Host` hay Net_id và Host_id. Các địa chỉ IP có cùng phần network là cũng mạng với nhau, mỗi địa chỉ IP là duy nhất
 - Địa chỉ IP hồm có hai loại:IPv4 và IPv6
# 2. Phân lớp địa chỉ IPv4
  Đia chỉ IPv4 có 32bit chia làm 4 phần(octet) mooic phần gồm 8 bit đc ngăn cách nhau bởi dấu `.`. Địa chỉ IPv4 có thể biểu diễn dưới dạng thập phân hoặc nhị phân. Được chia thành 5 lớp A, B, C, D.
  - Trong đó lớp A, B, C được dùng để gán cho các host
  - Lớp D là địa chỉ multicast
  - Lớp E không dùng
   - **Lớp A**:
         ![](https://github.com/daitq1998/Linux-basic/blob/master/CCNA/png/l%C6%A1%CC%81p%20A.PNG)
      - Ở Lớp A này có 1 octet đầu tiên làm phần Net còn 3 octet cuối làm phần host
      - Bit đầu tiên của phần Net là bit 0: có nghĩa là octet đầu tiên được đánh từ 000000000 - 11111111 hay từ 0 - 127( gián trị đầu tiên"0" thì không dùng còn 127 lf địa chỉ loopback. Vậy địa chỉ lớp A có octet đầu tiên mang giá trị 00000001 đến 01111110 (hay từ 1 đến 126)
      - Một mạng lớp A có thể đánh cho 2^24-2 địa chỉ host
   - **Lớp B**:
   ![](https://github.com/daitq1998/Linux-basic/blob/master/CCNA/png/l%C6%A1%CC%81p%20B.PNG)
      - Dành hai octet đầu tiên  làm Net còn 2 octet cuối làm host 
      - Hai bit đầu tiên của octet đầu tiên phải là bit 10 
      - Một mạng lớp A có thể đánh cho 2^16-2 địa chỉ host. Địa chỉ lớp B có octet đâu tiên mang giá trị nằm trong khoảng từ 128 - 191 
   - **Lớp C**:
   ![](https://github.com/daitq1998/Linux-basic/blob/master/CCNA/png/L%C6%A1%CC%81p%20C.PNG)
      - Dành 3 octet đầu tiên để làm địa chỉ Net và một octet để làm địa chỉ host
      - 3 bit đầu tiên của octet đầu tiên phải là bit 110
      - Một mạng lớp A có thể đánh cho 2^8-2 host. Địa chỉ lớp C có octet đâu tiên mạng giá trị nằm trong khoảng từ 192-223
   - **Lớp D**: là địa chỉ multicast
      - 4 bít đầu tiên của octet đầu là bit 1110. có giá trị từ 224 - 239
   - **Lớp E**: chưa sẻ dụng
      - 5 bit đầu tiên của octet đầu là 11110
# 3. Subnetmask
   Subnetmask có chiều dài bằng với địa chỉ ip được dùng để chỉ ra trong một địa chỉ ip những bit nào thuộc phần Net nhưng bit nào thuộc phần host 
   - Subnetmask được biểu diễn dưới dạng: (1) 4 octet giống như địa chỉ IP hoặc (2) /n vói n là số bit làm phần network
    - Subnetmask măc định cho các lớp ip như sau:
      - Lớp A: 255.0.0.0 hay /8
      - Lớp B: 255.255.0.0 hay /16
      - Lớp C: 255.255.255.0 hay /24
# 4. Kỹ thuật chia mạng con
   Subneting là một kỹ thuật cho phép tạo ra nhiều mạng con (subnetworks) từ một mạng lớn (major network). Với kỹ thuật này cho phép tao ra nhiều mạng con (subnetwork) vói số lượng host ít hơn phù hợp với ng sử dụng và tối ưu cho hệ thống
   - Để thực hiện điều này, người ta sử dụng một số bit ở phần host_id tham gia vào phần net_id
   ![](https://github.com/daitq1998/Linux-basic/blob/master/CCNA/png/Subneting.PNG)
   - Lưu ý:
     - Nếu gọi n là số bit mượn ở phần host để chia subneting thì số mạng con (subnetwork) có thể chia là 2^n  (VD: nếu mượn 1 bit thì số mạng con sẽ là 2^1=2)
     - Gọi m là số bit còn lại của phần host thì số host cho mạng con là 2^m-2
     - n+m là số bit phần host của mạng ban đầu
     - Số subnet có thể chia được:
      - 2^n nếu có hỗ trợ subnet – zero
      - 2^n – 2 nếu không hỗ trợ subnet – zero.
     - Số host có thể có trên mỗi subnet: 2^m-2(host/subnet)
     - bước nhảy : 2^m
     - Với mỗi subnet:
      - Địa chỉ mạng: Octet bị mượn bội số với bước nhảy.
      - Địa chỉ host đầu: Địa chỉ network +1
      - Địa chỉ host cuối: Địa chỉ broadcast -1
      - Địa chỉ broadcast: Địa chỉ mạng kế tiếp -1
      - Địa chỉ mạng kế tiếp: Địa chỉ mạng trước + bước nhảy
     - Subnet mask mới: 256 – Bước nhảy
       | n (Số bit mượn) | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 |
       | --------------- | - | - | - | - | - | - | - | - |
       | Bước nhảy | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
     - Hay có thể:
       | Số lượng subnet hoặc host | 1 | 2 | 4 | 8 | 16 | 32 | 64 | 128 | 512 | 1024 | ... |
       | ------------------------- | - | - | - | - | -- | -- | -- | --- | --- | ---- | --- |
       | Số bit mượn  | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | ... |
      - Ví dụ: Có địa chỉ mạng sau 192.168.1.0/24 có 24 bit ở phần net_id và 8 bit ở phần host_id và so subnetmask 255.255.255.0 hay /24 chia địa chỉ mạng trên thành 4 subnet
        - Bằng cách mượn 2 bit ở phần host so bit mượn n=2  => số bit host còn lại m=6 ==> có 2^6-2=62(subnetwork)
          |   | Subnet 1 | Subnet 2 | Subnet 3 | Subnet 4 |
          | - | -------- | -------- | -------- | -------- |
          | Địa chỉ mạng | 192.168.1.0 | 192.168.1.64 | 192.168.1.128 | 192.168.1.192 |
          | Địa chỉ host đầu | 192.168.1.1 | 192.168.1.65 | 192.168.1.129 | 192.168.1.193 |
          | Địa chỉ host cuối | 192.168.1.62 | 192.168.1.126 | 192.168.1.190 | 192.168.1.254 |
          | Địa chỉ broadcast | 192.168.1.63 | 192.168.1.127 | 192.168.1.191 | 192.168.1.255 |
        - Subnetmask của dải địa chỉ này là: 255.255.255.192 hay  /26
      - Ví dụ 2: một bài toán về ip cho một địa chỉ host. tìm xem địa chỉ mạng đó thuộc mạng nào
          Cho địa chỉ host: 202.162.4.165
          Subnet mask: 255.255.255.224 = 11111111.11111111.11111111.11100000
           => số bit còn lại của phần host_id: m=5
           => số bước nhảy: 2^m-2= 2^5=32
           => lấy 165 : 32 =  5.15625
           => lấy phần nguyên của kết quả trên: 5 x 32=160
           => Host trên thuộc net_id: 202.162.4.160
           
    # 5. Phương pháp VLSM
       - 
          
          
