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

   
      
