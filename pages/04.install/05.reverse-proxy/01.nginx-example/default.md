---
title: 'NGINX Example'
---

### NGINX Reverse Proxy Config

```
 server {
     listen 443 ssl;
     ssl_certificate /etc/nginx/ssl/nginx.crt;
     ssl_certificate_key /etc/nginx/ssl/nginx.key;

     location / {
         # The following configurations must be configured when proxying to Kavita

         # WebSocket Support
         proxy_set_header        Upgrade $http_upgrade;
         proxy_set_header        Connection "upgrade";

         # Host and X headers
         proxy_set_header        Host $host;
         proxy_set_header        X-Real-IP $remote_addr;
         proxy_set_header        X-Forwarded-For $proxy_add_x_forwarded_for;
         proxy_set_header        X-Forwarded-Proto $scheme;

         # Connectivity Options
         proxy_http_version      1.1;
         proxy_read_timeout      1800s;
         proxy_send_timeout      1800s;
         proxy_connect_timeout   1800s;
         proxy_buffering         off;

         # Proxy to Kavita running locally on port 5000 using ssl
         proxy_pass https://127.0.0.1:5000 ;
     }
 }
 ```