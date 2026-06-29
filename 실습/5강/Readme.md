
'''
sudo -i
yum update -y
yum install -y nginx
systemctl enable nginx
systemctl start nginx
cd /usr/share/nginx/html
echo "<h1>Hello world</h1><h2>This is my First Instance</h2>" > index.html
```
