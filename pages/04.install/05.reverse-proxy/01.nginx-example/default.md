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

         # Host and X headers
         proxy_set_header        Host $host;
         proxy_set_header        X-Real-IP $remote_addr;
         proxy_set_header        X-Forwarded-For $proxy_add_x_forwarded_for; aiothreads;
         proxy_set_header        X-Forwarded-Proto $scheme;

         # Proxy to Kavita running locally on port 5000 using ssl
         proxy_pass https://127.0.0.1:5000 ;
     }
 }
 ```