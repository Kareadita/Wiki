---
title: 'NGINX Example'
---

### NGINX Reverse Proxy Config

```
server{    
    location / {
         # The following configurations must be configured when proxying to Kavita

         # Host and X headers
         proxy_set_header        Host $host;
         proxy_set_header        X-Real-IP $remote_addr;
         proxy_set_header        X-Forwarded-For $proxy_add_x_forwarded_for; aio threads;
         proxy_set_header        X-Forwarded-Proto $scheme;

         # Proxy to Kavita running locally on port 5000 using ssl
         proxy_pass https://127.0.0.1:5000 ;
     }
        server_name kavita.example.com;

    listen 443 ssl; # managed by Certbot
    include /etc/letsencrypt/options-ssl-nginx.conf; # managed by Certbot
    ssl_dhparam /etc/letsencrypt/ssl-dhparams.pem; # managed by Certbot


    ssl_certificate /etc/letsencrypt/live/kavita.example.com/fullchain.pem; # managed by Certbot
    ssl_certificate_key /etc/letsencrypt/live/kavita.example.com/privkey.pem; # managed by Certbot

}

server {
    if ($host = kavita.example.com) {
        return 301 https://$host$request_uri;
    } # managed by Certbot

        listen 80;
        listen [::]:80;

        server_name kavita.example.com;
    return 404; # managed by Certbot

     
 }
 ```