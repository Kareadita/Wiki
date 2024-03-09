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

! This page is completely out of date, please see this page for Email instructions: [https://wiki2.kavitareader.com/guides/admin-settings/email](https://wiki2.kavitareader.com/guides/admin-settings/email)

Kavita provides email functionality out of the box to invite users, send reset password links, and more. We currently use a Google account that sends the emails and then auto deletes them. However, not all users want to put trust in another party and for this, Kavita offers [KavitaEmail](https://github.com/Kareadita/KavitaEmail) microService, so you can use your own SMTP service.

For those that do use it, they must be aware that Kavita will not send emails for the above if the server is not accessible from a public IP. This is done by testing accessibility and having KavitaEmail (the one we run) ping your server during an attempt to send the email. However, if you have a reverse proxy setup, you can use `Host Name` field under Admin Settings to bypass the accessibility check and emails will always be sent. Note: Kavita will never use it's own implementation for sending files to devices. You will need to setup KavitaEmail for this functionality. 

# Kavita Email
To get started, head over to the KavitaEmail GitHub and download a release, or use our [Docker container](https://hub.docker.com/r/jvmilazz0/kavitaemail).

<hr style="border:5px solid #4ac694"> </hr>

# Installation

>>>>> If you use Gmail, you need to enable Insecure Apps or generate an app password.

### With Docker Run

`docker run --name kavita-email -p 5003:5003 -v [Your-Kavita-Email-config-path]:/app/config -d jvmilazz0/kavitaemail:latest`

### With Docker Compose

>>>>>> To setup the mail service with docker it's highly recommended to use docker-compose. This allows both containers to be accessible to each other. Later in Kavita you would only need to type down `http://[email-container-name]:[yourport]` in the SMTP service settings.
<br/>To do so just copy the config from "email" to the bottom and either create a new docker compose file or add it to your current Kavita compose.


```
version: '3'
services:
     email:
        image: jvmilazz0/kavitaemail:latest
        container_name: kavita-email
        volumes:
           - [Your-Kavita-Email-config-path]:/app/config
        ports:
           - "5003:5003"
        restart: unless-stopped
```
Example with both Kavita and Kavita-Email:
```
version: '3'
services:
     kavita:
        container_name: kavita
        image: jvmilazz0/kavita:nightly
        ports:
           - 5000:5000
        volumes:
           - [Your-media-path]:/media
           - [Your-Kavita-config-path]:/kavita/config
        restart: unless-stopped

     kavita-email:
        container_name: kavita-email
        image: jvmilazz0/kavitaemail:latest
        ports:
           - 5003:5003
        volumes:
           - [Your-Kavita-Email-config-path]:/app/config
        restart: unless-stopped
```

>>>>> After the first run, shut down the container and edit the appsettings.json file inside the config folder. When the settings are to your liking, restart and it should apply your SMTP settings.

### Non-Docker
1. Open appsettings.json in config/
2. Under SMTP, fill out the required settings that are blank.
3. Start KavitaEmail.exe or ./KavitaEmail


### Kavita Side
Once you have set up your KavitaEmail service, you can now link your Kavita instance with KavitaEmail service. Navigate to Server Settings and under Email, you can change the URL to your local service (and port if needed). Press Test to ensure it works; as of Kavita-email v0.1.15.0 and Kavita v0.7.1.35 this will send an actual test email to the admin account's email address.

![Email-Service-Link](Email-Service-Link.PNG "Email-Service-Link")

