# Giới thiệu SSH

**SSH :** Là một giao thức bảo mật và các thông tin thường nhất để truy cập từ xa tới server một cách an toàn
* SSH cung cấp một cơ chế thiết lập các kết nối bảo mật đc mã hóa giữa hai bên xác thực lẫn nhau và thông qua các thao tác tới server từ xa
* Ngoài ra ssh là một phương pháp cho việc điều khiển từ xa một cách bảo mật từ một máy tính này đến một máy tính khác
* SSH hoat động ở lớp ứng dụng của phân lớp TCP/IP
* SSH cung cấp các tùy chọn thay thế cho :khả năng xác thực mạnh mẽ, bảo vệ sự bảo mật, và toàn vẹn với khả năng mã hóa cho toàn bộ kết nối
**Đặc điểm**
*Tính bí mật*: thông qua khả năng mã hóa mạnh mẽ
*Tính toàn vẹn*: Đảm bảo dữ liệu trên kênh truyền và gửi giữa hai bên toàn vẹn không bị thay đổi
*Authentication*:cung cấp khả năng xác thực giữa bên gửi và bên nhận
*Authorization*:cung cấp khả năng ủy quyền dùng để truy cập thông qua các tài khoản
# Cài đặt SSH
- Để cài đặt ssh ta cần tạo 2 máy ssh-server và ssh-client
**Trên Server**: để cài đăt ssh trên server ta dùng lệnh :`sudo apt-get install openssh-server`
**Trên Client**:để cài đặt ssh trên client ta dùng lệnh :`sudo apt-get install openssh-client`
