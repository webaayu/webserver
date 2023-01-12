**Below are the Linux commands for nginx installation and multiple pages creation under different directory (applies to Amazon Linux-2). This can be used as Userdata file as well when deploying ec2 instance for the very first time.**  

- Add in beginning for shell script or userdata file
```s
#!/bin/sh
```
- Install nginx in amzon linux 2 server
```s
sudo amazon-linux-extras install nginx1 -y
```
- Start nginx service
```s
sudo systemctl start nginx
```
- create a blue dir in nginx root
```s
sudo mkdir /usr/share/nginx/html/blue
```
- copy the content of index.html(default webpage of nginx) to blue/index.html
```s
sudo cat /usr/share/nginx/html/index.html > /usr/share/nginx/html/blue/index.html
```
- Change the background colour in blue/index.html
```s
sudo sed -i 's/<body>/<body bgcolor="blue">/g' /usr/share/nginx/html/blue/index.html
```
- Repeat above last 3 steps for green dir 
```s
sudo mkdir /usr/share/nginx/html/green
sudo cat /usr/share/nginx/html/index.html > /usr/share/nginx/html/green/index.html
sudo sed -i 's/<body>/<body bgcolor="green">/g' /usr/share/nginx/html/green/index.html
```
- Rcestart nginx service
```s
sudo systemctl restart nginx
```
