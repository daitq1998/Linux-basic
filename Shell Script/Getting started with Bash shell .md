# GIỚI THIỆU TỔNG QUAN VỀ BASH SHELL VÀ SHELL SCRIPT
**Shell script**: là một chương trình được sử dụng cho nhiều mục đích khác nhau như thực thi lệnh trên shell chạy trên nhiều lệnh cùng nhau tùy chỉnh các tác vụ quản lý thực hiện tự động hóa. Shell script lập trình theo một chuỗi và các hệ thống phải thực thi nó. Shell script cũng có các vòng lăp for/do, điều kiện if/else/then
- *Tiện ích của shell script*
  - Nhận đầu vào từ nhiều phía (màn hình, bàn phím, file)
  - Tạo nhóm lệnh riêng, tiết kiệm thời gian
  - Thực hiện công việc một cách tự động hóa 
  **Trong shell script có nhiều loại như : Sh Shell, Bash Shell, Dash Shell**
- Bash shell là một shell của shell script
# BẮT ĐẦU VỚI BASH SHELL
1. Tương tác với shell
- Các tập lệnh được lưu trữ dứoi mộ tên tùy ý. Nhưng lưu ý với dòng đầu tiên trong bash shell phải bắt đầu bằng `shebang` 
- `#!/bin/bash` 
- *Ví dụ;*
    `#!/bin/bash
    echo "Ban la ai"`
