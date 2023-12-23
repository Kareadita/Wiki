---
title: 'NGINX Example'
---

### NGINX Reverse Proxy Config

```
server{    
    set $server "Your_Kavita_IP_Here";
    set $port "Your_Kavita_Port_Here";
    set $domain "kavita.example.com";
    #set $organizr "organizr.example.com"; #Uncomment this for organizr support
    server_name $domain;
    
    location / {
         # The following configurations must be configured when proxying to Kavita

         # Host and X headers
         proxy_set_header        Host $host;
         proxy_set_header        X-Real-IP $remote_addr;
         proxy_set_header        X-Forwarded-For $proxy_add_x_forwarded_for; aio threads;
         proxy_set_header        X-Forwarded-Proto $scheme;

         # Headers to proxy websocket connections
         proxy_http_version 1.1;
         proxy_set_header Upgrade $http_upgrade;
         proxy_set_header Connection "Upgrade"; 

         # Proxy to Kavita running locally on port 5000 using ssl
         proxy_pass http://$server:$port;
         
         # Organizr support - uncomment both of the following lines
         #proxy_hide_header "Content-Security-Policy";
         #add_header Content-Security-Policy "frame-ancestors $organizr;"; 
    }
     
    

    listen 443 ssl; # managed by Certbot
    include /etc/letsencrypt/options-ssl-nginx.conf; # managed by Certbot
    ssl_dhparam /etc/letsencrypt/ssl-dhparams.pem; # managed by Certbot


    ssl_certificate /etc/letsencrypt/live/kavita.example.com/fullchain.pem; # managed by Certbot
    ssl_certificate_key /etc/letsencrypt/live/kavita.example.com/privkey.pem; # managed by Certbot

}

server {
    if ($host = $domain) {
        return 301 https://$host$request_uri;
     } # managed by Certbot

       listen 80;
       listen [::]:80;

       server_name $domain;
    return 404; # managed by Certbot
  
 }
 ```
