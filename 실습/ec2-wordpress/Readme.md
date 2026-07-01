
```
dnf install -y wget php-mysqlnd httpd php-fpm php-mysqli
dnf install -y mariadb118-server php-json php php-devel

wget https://wordpress.org/latest.tar.gz

wget https://wordpress.org/latest.tar.gz

systemctl enable mariadb httpd
systemctl start mariadb httpd

mysql_secure_installation
--- db -----
create user 'wpuser@localhost' identified by '4321';
create database wp-db;
grant all privileges on wp_db.* to 'wpuser@localhost';
--- db 끝-----

cd wordpress
cp wp-config-sample.php wp-config.php
ls wp-config*

vim wp-config.php

## cp -r ~/wordpress/* /var/www/html/

vim /etc/httpd/conf/httpd.conf

## AllowOverride None --> ALL

dnf install php-gd

chown -R apache.apache /var/www
chmod 2775 /var/www

find /var/www -type d -exec sudo chmod 2775 {} \;

find /var/www -type f -exec sudo chmod 0644 {} \;
```
