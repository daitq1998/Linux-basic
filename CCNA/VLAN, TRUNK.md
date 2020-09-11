# Virtual Local Area Networks (VLAN)
  VLAN(Virtual Local Area Networks): Được dùng để chia 1 mạng vật lý thành nhiều mạng nhỏ. về mặt kĩ thuật VLAN là một miền quảng bá đc tạo bởi các switch, bình thường thì router dóng vái trò tạo ra miền quảng bá còn VLAN thì switch ssongs vai trò tạo ra miền quảng bá 
  - Tiêu chuẩn mà VLAN đc sử dụng là IEEE802.1q
  - Mỗi một VLAN đc gán một id cụ thể có giá trị từ 1 - 4094 trong đó id bằng 1 thường được sử dụng để quản lý vì vậy không nên dùng
  
  **Phân loại VLAN**: 
   - port-bassed VLAN: là cách cấu hình VLAN đơn giản và phổ biến mỗi cổng của switch đc gắn với một VLAN xác định. Do vậy mỗi host khi được gắn vào cổng đều thuộc một VLAN nào đó 
   - MAC address bassed VLAN: Cách cấu hình này hiện nay ít đc sử dụng do bất tiện trong viêc quản lý. Mỗi địa chỉ MAC được đánh dấu với một VLAN xác định
   - Protocol-bassed VLAN: cách cấu hình này tương tự như MAC address bassed nhưng sử dụng môt địa chỉ logic hay địa chỉ ip thay thế cho địac chỉ MAC. Tuy nhiên các cấu hình nà không còn thông dụng nữa nhờ sử dụng DHCP
   
