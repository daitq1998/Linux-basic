# init
**init** Là cha của tất cả các process.Với vai trò chình của các init là tạo ra các process bằng cách chạy các chương trình đc quy định trong tệp tin
– Run level 0 (`init 0`): chế độ tắt máy.

– Run level 1 (`init 1`): chế độ này chỉ sử dụng được 1 người dùng.

– Run level 2 (`init 2`): chế độ đa người dùng nhưng không có dịch vụ NFS.

– Run level 3 (`linit 3`): chế độ đa người dùng, có đầy đủ các dịch vụ.

– Run level 4 (`init 4`): chưa được sử dụng.

– Run level 5 (`init 5`): chế độ đồ họa.

– Run level 6 (`init 6`): khởi động lại máy.

-Cú pháp:`init`

VD: `# init 6`:Dùng để khởi động lại

- `init` : có một số phần mềm sau

- sysV: là phầm mềm có từ lâu và ít đc sử dụng

- upstart: là phần mềm đc viết bởi Ubuntuvà bị thay thế băng system do Debian

- Systemd:là chương trình unix làm nhièu hơn những gì init từng làm. Nhưng hiện tại đã đc dúng phổ biên ở các phiên bản Debian, Ubuntu 16.04 trở đi, (và Mint vì Mint là distro base trên Ubuntu), Fedora, ArchLinux ...
- OSX có Launchd. Các hệ thống sử dụng systemd khi khởi động sẽ nhanh hơn các hệ thống sử dụng init trước đó. Do các hệ thống sử dụng systemd được thay thế loạt các bước được trình tự hoá với kỹ thuật song song cho phép nhiều dịch vụ khởi tạo cùng lúc.

