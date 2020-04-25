# Mô hình OSI
- **Mô hìnhOSI**
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
  | 6 | Transport | Dòng điều khiển buffering, windowing, congestion avoidance. Giúp ngăn ngừa sự mất mát của các phân đoạn trên mạng và sự cần thiết phải truyền lại | Segment | TCP, UDP |
