---
title: Email
media_order: Email-Service-Link.PNG
published: true
taxonomy:
    category:
        - docs
    tag:
        - Mail
---

# Kavita Email
Kavita provides email functionality out of the box to invite users, send reset password links, and more. We currently use a Google account that sends the emails and then auto deletes them. However, not all users want to put trust in another party and for this, Kavita offers [KavitaEmail](https://github.com/Kareadita/KavitaEmail) microService, so you can use your own SMTP service.

To get started, head over to the KavitaEmail GitHub and download a release, or use our [Docker container](https://hub.docker.com/r/kizaing/kavitaemail).

<hr style="border:5px solid #4ac694"> </hr>

# Installation

### With Docker Run

`docker run --name kavita-email -p 5003:5003 -e SMTP_HOST="" -e SMTP_PORT="" -e SMTP_USER="" -e SMTP_PASS="" -e SEND_ADDR="" -e DISP_NAME="" -e ALLOW_SENDTO="true" -d kizaing/kavitaemail:latest`

### With Docker Compose

>>>>>> To setup the mail service with docker-compose it's highly recommended to use a docker stack. This allows both containers to be accesible from eachother.
Later in kavita you would only need to type down `http:kavita-email:3001` in the smpt service settings.<br/>
To do so just copy the config from "email" to the bottom and add it to your current kavita compose. 


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
           - ALLOW_SENDTO=<true/false if you want the service to email files for Kavita>
           - SIZE_LIMIT=<size in bytes that your SMTP provider can handle for a single email. This is optional, defaults to 25MB>
        ports:
           - "5003:5003"
        restart: unless-stopped
```

### Non-Docker
1. Open appsettings.json in config/
2. Under SMTP, fill out the required settings that are blank. Note: If you use Gmail, you need to enable Insecure Apps or generate a password key for the account.
3. Start KavitaEmail.exe or ./KavitaEmail


### Kavita Side
Once you have set up your KavitaEmail service, you can now link your Kavita instance with KavitaEmail service. Navigate to Server Settings and under Email, you can change the URL to your local service (and port if needed). Press Test to ensure it works.

![Email-Service-Link](Email-Service-Link.PNG "Email-Service-Link")

