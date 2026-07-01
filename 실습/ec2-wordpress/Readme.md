
```
sudo -i

# dnf update

dnf install -y wget php-mysqlnd httpd php-fpm php-mysqli
dnf install -y  php-json php php-devel
dnf install mariadb118
dnf install php-gd

*** mariadb118-server
wget https://wordpress.org/latest.tar.gz

tar -xfv latest.tar.gz
cp -r ~/wordpress/* /var/www/html/

## http.conf 수정
vim /etc/httpd/conf/httpd.conf
### <Directory "/var/www/html">
### AllowOverride None --> ALL

chown -R apache.apache /var/www
chmod 2775 /var/www
cd wordpress
cp wp-config-sample.php wp-config.php
ls wp-config*

vim wp-config.php

find /var/www -type d -exec sudo chmod 2775 {} \;

find /var/www -type f -exec sudo chmod 0644 {} \;

systemctl enable  httpd
systemctl start  httpd
```

-----------------





```
dnf install -y mariadb118-server
systemctl enable mariadb
systemctl start mariadb

## db 초기화 작업
mysql_secure_installation

mysql -u root -p
--- db -----
create user 'wpuser'@'localhost' identified by '4321';
create database wpdb;
grant all privileges on wpdb.* to 'wpuser'@'localhost';
--- db 끝-----

cd /var/www/html

vim wp-config.php
```


