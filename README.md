

# Install nginx in amzon linux 2 server
sudo amazon-linux-extras install nginx1
 
# Start nginx service
sudo systemctl start nginx

# 2. create a blue dir in nginx root
sudo mkdir /usr/share/nginx/html/blue

# 3. copy the content of index.html(default webpage of nginx) to blue/index.html
sudo cat /usr/share/nginx/html/index.html > /usr/share/nginx/html/blue/index.html

# 4. change the background colour in blue/index.html
sudo sed -i 's/<body>/<body bgcolor="blue">/g' /usr/share/nginx/html/blue/index.html

# 5. Repeat above step 2 to 4 for green dir 
sudo mkdir /usr/share/nginx/html/green
sudo cat /usr/share/nginx/html/index.html > /usr/share/nginx/html/green/index.html
sudo sed -i 's/<body>/<body bgcolor="green">/g' /usr/share/nginx/html/green/index.html

# restart nginx service
sudo systemctl restart nginx
