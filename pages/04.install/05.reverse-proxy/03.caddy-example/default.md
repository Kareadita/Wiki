---
title: 'Caddy Example'
---

### Caddy Example
In this example IP address 192.168.0.1 is the IP of the Caddy machine.
```
 # Proxy to Kavita running locally on port 5000
kavita.yourdomain.com {
	tls youremail@youremail.com
	gzip

    proxy / localhost:5000 192.168.0.1:5000 {
        websocket
        transparent
    }

}
 ```