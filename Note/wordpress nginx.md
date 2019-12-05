**Cài đặt LEMP( Nginx,php.mysql)**
- Bước1 :Cài đặt ngix: `sudo apt-get install nginx`và cài đăt cổng vào tường lửa ![](https://github.com/daitq1998/Linux-basic/blob/master/Note/dirname/ufw.png)
  - Sau đó cầu hình virtual hosts để dc domain ta tạo một file mời trong `/etc/nginx/sites-available/daitq2303.com`
  sau đó kích hoạt:`ln -s /etc/nginx/sites-available/daitq2303.com /etc/nginx/sites-enabled/`
   ![](https://github.com/daitq1998/Linux-basic/blob/master/Note/dirname/daitq2303.com.png) và nhập tên domain lên trình duyệt thấy hình ảnh ntn là thành cmn công ![](https://github.com/daitq1998/Linux-basic/blob/master/Note/dirname/page.png)
 - Bước2: Cài đặt php : `sudo apt-get install php-fpm php-mysql` `sudo apt install php-fpm php-common php-mbstring php-xmlrpc php-soap php-gd php-xml php-intl php-mysql php-cli php-zip php-curl`
    - Sau khi cài xong vào fìle `/etc/php/7.2/fpm/php.ini` và bỏ dấu ; dòng`cgi.fix_pathinfo=0` và restart lại php:`systemctl restart php7.2-fpm` và nginx 
 - Bước 3: Cài đặt mysql:`apt install mysql-server`
    - sau đó cấu hình và tạo user cho mysql `mysql_secure_installation ` và đặt password ![](https://github.com/daitq1998/Linux-basic/blob/master/Note/dirname/mysqlnginx.png)
 - Bước 4: cài đăt wordpress `wget https://wordpress.org/latest.tar.gz` sau đó giải nén vào thư mục `/var/www/` và chỉnh sửa tên file trong wordpress `mv wp-config-sample.php wp-config.php`và chình sửa các tên và password sau đó thay đổi quyền user và group:`chown -R www-data:www-data /var/www/daitq2303.com``chmod -R 755 /var/www/daitq2303.com` và khởi động lại ngix 
 sau đó thêm địa chỉ ip và host và trong file host của client![](https://github.com/daitq1998/Linux-basic/blob/master/Note/dirname/hosts.png)
 và nhập domain vào trên trình duyệt![]( https://github.com/daitq1998/Linux-basic/blob/master/Note/dirname/xong.png)
 sau đó chọn ngôn ngữ và đăng kí tài khoản và password ![](https://github.com/daitq1998/Linux-basic/blob/master/Note/dirname/login%20.png)
 ![](https://github.com/daitq1998/Linux-basic/blob/master/Note/dirname/oke.png)
 

 


