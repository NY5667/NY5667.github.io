---
layout: post
title:  'Setting up an Nginx Reverse Proxy'
date:   2023-08-30 09:26:06 +0800
categories: NY5667 update
---

1. Install Nginx:
* Open the terminal and execute the following commands to install Nginx:
```
sudo apt update
sudo apt install nginx
```
2. Configure the reverse proxy:
* Open the Nginx default configuration file /etc/nginx/sites-available/default using a text editor like `nano` or `vim`:
```
sudo nano /etc/nginx/sites-available/default
```
* Inside the opened file, locate the `server` block and modify it as follows:
```
server {
    listen 80;
    server_name example.com;  # Replace with your domain

    location / {
        proxy_pass http://192.168.220.73:8080/;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }
}
```
* Replace `example.com` with your actual domain name or server IP address.
3. Check and save the configuration file:
* Use the following command to check if the Nginx configuration file is correct:
```
sudo nginx -t
```
* If there are no errors, save and close the file editor.
4. Restart Nginx:
* Execute the following command to reload the Nginx configuration and start the service:
```
sudo systemctl restart nginx
```
5. Done:
* Nginx is now configured as a reverse proxy, forwarding requests to the website hosted at `192.168.220.73:8080`.

Please note that the above configuration is a basic example, and you may need to make appropriate modifications based on your specific requirements, such as changing the domain, port, or other proxy-related settings. Also, ensure that your server can access the website hosted at `192.168.220.73:8080`.