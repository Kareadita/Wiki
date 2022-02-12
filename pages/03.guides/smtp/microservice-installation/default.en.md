---
title: 'Microservice Installation'
---

# Installation

### With Docker Run

`docker run --name kavita-email -p 5003:5003 -e SMTP_HOST="" -e SMTP_PORT="" -e SMTP_USER="" -e SMTP_PASS="" -e SEND_ADDR="" -e DISP_NAME="" -d kizaing/kavitaemail:latest`

### With Docker Compose

```
version: '3'
services:
     email:
        image: kizaing/kavitaemail:latest
        container_name: kavita-email
        environment:
           - SMTP_HOST=<your smtp hostname here>
           - SMTP_PORT=<smtp port>
           - SMTP_USER=<smtp username>
           - SMTP_PASS=<smtp password>
           - SEND_ADDR=<address you are sending emails from>
           - DISP_NAME=<display name to use>
        ports:
           - "5003:5003"
        restart: unless-stopped
```

Simply fill in the variables with your SMTP settings and then in Kavita put in the address of this email service. If running with Kavita in a docker-compose stack you can use the service name you defined for this email relay. 

Kavita Email on github: https://github.com/Kareadita/KavitaEmail

Kavita Email on docker: https://hub.docker.com/r/kizaing/kavitaemail
