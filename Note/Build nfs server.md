# Giới thiệu về nfs
- NFS là giao thức chia sẻ file phổ biến trên unix. Cho phép mount một thư mục trên máy tính từ xa vào một thư mục trên máy tính cục bộ
- NFS cho phép chia sẻ các thư mục và tệp với những người khác qua mạng. Dùng nfs người dùng và chương trình có thể truy cập các tệp trên hệ thống từ xa gần như thể chứng là các tệp cục bộ
- Lợi ích của NFS:
 - Các máy cục bộ sử dụng ít dung lượng đĩa hơn vì dữ liệu thường đc sử dụng có thể được lưu trữ trên một máy duy nhất và vẫn có thể truy cập đc cho những ng khác qua mạng
 - Không cần phải có các thư mục home riêng biệt trên mỗi máy mạng các thư mục chính có thể đc thiết lập trên máy chủ nfs và đc cung cấp trên toàn mạng 
# Cài đặt và cấu hình nfs
- Để cài đặt nfs dùng lệnh:*trên sever `sudo apt-get install nfs-kernel-server`* *Trên client `sudo apt-get install nfs-common`*
- Sau khi cài đặt nfs trên server xong ta tạo một thư mục chia sẻ là `nfs` thư mục vừa tạo là root và NFS sẽ dịch bất kỳ hoạt động root nào trên máy khách sang `nobody:nogroup`thông tin đăng nhập như một biện pháp bảo mật.Nên cần phải thay đổi quyền sở hữu của tệp
- **Cấu hinh nfs export trên server**
- để cấu hình nfs export cần chỉnh sửa file trong `/etc/export` trong file`export` cần thêm một số dòng với cú pháp sau `directory_to_share    client(share_option1,...,share_optionN)`![](
- Trong đó :
 - Derectory_to_share: là tên thư mục chia sẻ
 - Client là cso thể là địa chỉ ip của máy client share
 - Các tùy chọn là : `rw` (client cso khả năng đọc và ghi)
                   - `sync`: Tùy chọn này buộc NFS ghi các thay đổi vào đĩa trước khi trả lời. Điều này dẫn đến một môi trường                      ổn định và nhất quán hơn vì phản hồi phản ánh trạng thái thực tế của âm lượng từ xa. Tuy nhiên, nó cũng                        làm giảm tốc độ hoạt động của tập tin.
                   - `no_subtree_check`Tùy chọn này ngăn kiểm tra cây con, đây là một quá trình trong đó server  phải kiểm tra                      xem tệp có thực sự vẫn có sẵn trong cây được xuất cho mỗi yêu cầu hay không. Điều này có thể gây ra nhiều                      vấn đề khi một tệp được đổi tên trong khi client đã mở. Trong hầu hết các trường hợp, tốt hơn là vô                             hiệu hóa kiểm tra cây con.
                   - `no_root_squash`: Theo mặc định, NFS chuyển các yêu cầu từ user root từ xa sang người dùng không có                            đặc quyền trên máy chủ. Điều này được dự định là tính năng bảo mật để ngăn tài khoản root trên client sử                        dụng hệ thống tệp của máy chủ làm root
- Sau đó restart lại nfs:`systemctl restart nfs`
- Kiểm tra trạng thái của firewall
- Và mở port 2049 trên máy chủ để kết nối và thay thế vào đại chỉ ip client
**Cấu hình nfs trên client**
- Sau khi cài đặt nfs trên client xong tạo hai thư mục trong `/nfs`
- Tiếp theo mou cá thư mục từ server sang client vào thư mục vừa tạo
- Sau đó sử dụng df -h để kiểm tra kết quả
