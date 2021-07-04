---
title: 'Caddy Example'
---

### Caddy Example
In this example IP address 192.168.0.1 is the IP of the Caddy machine.
```
192.168.0.1:443
 tls self_signed
 log stdout

 # Proxy to Kavita running locally on port 5000
 proxy / https://localhost:5000 {

         # WebSocket Support
         header_upstream Connection {>Connection}
         header_upstream Upgrade {>Upgrade}


         # Host and X headers
         header_upstream Host {host}
         header_upstream X-Real-IP {remote}
         header_upstream X-Forwarded-For {remote}
         header_upstream X-Forwarded-Port {server_port}
         header_upstream X-Forwarded-Proto {scheme}
 }
 ```