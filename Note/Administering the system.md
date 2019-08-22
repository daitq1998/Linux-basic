# Syslogd
**Syslog** 
- Là một gói phần mềm tronh hệ thống linux nhằm để ghi bản tin log của hệ thống trong quá trình hoạt động như của kernel, deamon, cron, auth hoặc các ứng dụng chạy trên hệ thống như dhcp, dns,http,ntp
- các tác dụng của log : Log ghi lại liên tục các thông báo về hoạt động của cả hệ thống hoặc của các dịch vụ được triển khai trên hệ thống và file tương ứng. Log file thường là các file văn bản thông thường dưới dạng “clear text” tức là bạn có thể dễ dàng đọc được nó, vì thế có thể sử dụng các trình soạn thảo văn bản (vi, vim, nano...) hoặc các trình xem văn bản thông thường (`cat`, `tailf`, `head`...) là có thể xem được file log.
- Các file log có thể nói cho bạn bất cứ thứ gì bạn cần biết, để giải quyết các rắc rối mà bạn gặp phải miễn là bạn biết ứng dụng nào, tiến trình nào được ghi vào log nào cụ thể. Trong hầu hết hệ thống Linux thì /var/log là nơi lưu lại tất cả các log.
- ứng dụng của log: phân tích nguyên nhân gốc dễ cảu một vấn đề. Giúp cho một hệ thống khi gắp vấn đề đc khắc phục nhanh hơn. Giúp cho việc phát hiện dự đoán một vấn đề có thể xảy ra đôi với hệ thống
**Trong syslogd có 4 khái niệm cần hiểu**
- **Facility**: Facility giúp kiểm soát các log đến dựa vào các nguồn gốc đc quy định như ứng dụng hay tiến trình nào. Syslog sử dung facility để quy hoạch lại log như vậy có thể coi các fácility là đại diện đối tượng tạo ra thông báo(kernel, process, app..)
- **Priority (level)** :mức độ quan trong của log message đc chỉ định
- **Selector**: sự kết hợp giữa facility và level
- **Action**: đại diện cho địa chỉ messages tương úng với facility.level.Action có thể là một tên file hoặc có thể là một host name đứng trc kí tự @

**Trong facility** có cácloại facility đc sử dụng và quy định trong hệ thống Linux

|  Facility  |	Miêu tả |
|------------|----------|
| auth  |  Các hoạt động liên quan đến yêu cầu tên và mật khẩu (getty, su, login)|
|  authpriv |	Tương tự như auth nhưng ghi log tới một file mà chỉ có thể được đọc bởi những người dùng được chọn.|
| console | Sử dụng để bắt các thông báo mà thường trực tiếp gửi tới bàn điều khiển hệ thống.|
| cron  |  Các thông báo từ người lập hệ thống cron.|
| daemon |	Hệ thống daemon nhận tất cả.|
| ftp | Các thông báo liên quan đến hệ thống ftp deamon.|
| kern |	Các thông báo kernel. |
| local0.local7 | 	Các phương tiện nội bộ được xác định cho mỗi site. |
| lpr | 	Các thông báo từ dòng hệ thống in. |
| mail |	Các thông báo liên quan tới hệ thống mail. |
| mark |	Các sự kiện giả được sử dụng để tạo timestamp trong các file hệ thống. |
| news |	Các thông báo liên quan tới mạng lưới giao thức tin tức (network news protocol) |
| ntp |	Các thông báo liên quan đến giao thức thời gian mạng. |
| user |	Các tiến trình người dùng thông thường. |
| uucp |	Hệ thống phụ UUCP.|
- Theo măc định các bản tin log của hệ thống được syslog lưu vào trong thư mục /var/log, và được lưu riêng rẽ đối với từng tác vụ trong hệ thông nhưng đối với tiến trình cron thì sẽ lưu trong file cron.log.
-file câu hình của linux đc lưu trong bản ghi có đường dẫn là : `/etc/rsyslog.conf`.  nhưng các rule được định nghĩa riêng trong `/etc/rsyslog.d/50-defaul.conf` . File rule này được khai báo include từ file cấu hình `/etc/rsyslog.conf`
**Syslog priority**

| Priority | Miêu tả |
| -------- | ------- |
| debug | Các message ở chế độ debug |
| ìno | Các message mang thông tin |
| notice | message mang tính chất thông báo |
| warning | Các mesage mang tính chất cảnh cáo |
| ere | cá message lỗi |
| crit | các message nguy hiểm |
| alert | các mesage về các hành động phải thực hiện ngay |
| emerg | message khi hệ thống không dùng đc nữa |

#Lệnh `at`
Chương trình tại cho phép một lệnh hoặc tập lệnh được lên lịch cho một lần thực hiện tại một thời gian sau Chức năng lập lịch trình thực sự khá linh hoạt và có thể lấy một số định dạng. Ví dụ, bạn có thể lên lịch một sự kiện liên quan đến thời gian hiện tại

