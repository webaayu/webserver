## below is the Userdata file to be used for nginx installation and multiple pages under different directory

```s
#!/bin/sh
```
- 0. Install nginx in amzon linux 2 server
```s
sudo amazon-linux-extras install nginx1 -y
```
- 1. Start nginx service
```s
sudo systemctl start nginx
```
- 2. create a blue dir in nginx root
```s
sudo mkdir /usr/share/nginx/html/blue
```
- 3. copy the content of index.html(default webpage of nginx) to blue/index.html
```s
sudo cat /usr/share/nginx/html/index.html > /usr/share/nginx/html/blue/index.html
```
- 4. change the background colour in blue/index.html
```s
sudo sed -i 's/<body>/<body bgcolor="blue">/g' /usr/share/nginx/html/blue/index.html
```
- 5. Repeat above step 2 to 4 for green dir 
```s
sudo mkdir /usr/share/nginx/html/green
sudo cat /usr/share/nginx/html/index.html > /usr/share/nginx/html/green/index.html
sudo sed -i 's/<body>/<body bgcolor="green">/g' /usr/share/nginx/html/green/index.html
```
- 6. restart nginx service
```s
sudo systemctl restart nginx
```
