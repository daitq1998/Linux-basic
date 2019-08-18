# init
**init** Là cha của tất cả các process.Với vai trò chình của các init là tạo ra các process bằng cách chạy các chương trình đc quy định trong tệp tin. Vai trò chính của nó là tạo các quy trình từ một tập lệnh được lưu trữ trong tệp / etc / inittab

– Run level 0 (`init 0`): chế độ tắt máy.

– Run level 1 (`init 1`): chế độ này chỉ sử dụng được 1 người dùng.

– Run level 2 (`init 2`): chế độ đa người dùng nhưng không có dịch vụ NFS.

– Run level 3 (`init 3`): chế độ đa người dùng, có đầy đủ các dịch vụ.

– Run level 4 (`init 4`): chưa được sử dụng.

– Run level 5 (`init 5`): chế độ đồ họa.

– Run level 6 (`init 6`): khởi động lại máy.

Một runlevel là một cấu hình phần mềm của hệ thống mà chỉ cho phép một nhóm được lựa chọn của các quá trình tồn tại. Các quy trình được sinh ra bởi init cho mỗi runlevels này được xác định trong tệp / etc / inittab . Ban đầu có thể ở một trong tám đường băng: 0-6 và S hoặc s . Runlevel được thay đổi bằng cách có một người dùng đặc quyền chạy telinit , nó sẽ gửi các tín hiệu thích hợp đến init , cho biết runlevel sẽ thay đổi thành gì.

-Cú pháp:`init`

VD: `# init 6`:Dùng để khởi động lại

- `init` : có một số phần mềm sau

- sysV: là phầm mềm có từ lâu và ít đc sử dụng

- upstart: là phần mềm đc viết bởi Ubuntuvà bị thay thế băng system do Debian

- Systemd:là chương trình unix làm nhièu hơn những gì init từng làm. Nhưng hiện tại đã đc dúng phổ biên ở các phiên bản Debian, Ubuntu 16.04 trở đi, (và Mint vì Mint là distro base trên Ubuntu), Fedora, ArchLinux ...
- OSX có Launchd. Các hệ thống sử dụng systemd khi khởi động sẽ nhanh hơn các hệ thống sử dụng init trước đó. Do các hệ thống sử dụng systemd được thay thế loạt các bước được trình tự hoá với kỹ thuật song song cho phép nhiều dịch vụ khởi tạo cùng lúc.

Các shell khởi động phức tạp được thay thế bằng các tệp cấu hình đơn giản, liệt kê những gì phải được thực hiện trước khi một dịch vụ được khởi động, cách thực thi dịch vụ khởi động và điều kiện dịch vụ nào cần được thực hiện khi khởi động xong. Một điều cần lưu ý là /sbin/init bây giờ chỉ trỏ tới /lib/systemd/systemd. Systemd sẽ mất quá trình init.

# runlevel (**runlevel** `utmp`)

- Đọc tệp utmp hệ thống (thường là /var/run/utmp) để xác định bản ghi runlevel. sau đó in runlevel hệ thống trước đó và hiện tại trên đầu ra tiêu chuẩn của nó, cách nhau bởi một khoảng trắng. Nếu không có runlevel hệ thống trước đó, chữ N sẽ được in thay thế.Nếu không có tệp utmp tồn tại hoặc nếu không tìm thấy bản ghi runlevel , runlevel sẽ in từ không xác định và thoát với lỗi.

Runlevel có thể được sử dụng trong các tập lệnh RC để thay thế cho lệnh System-V who -r . Tuy nhiên, trong các phiên bản mới hơn của init
