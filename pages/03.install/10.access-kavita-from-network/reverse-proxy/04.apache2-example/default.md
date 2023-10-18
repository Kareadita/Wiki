---
title: 'Apache2 Example'
---

### Apache2 Example
```
<IfModule mod_ssl.c>
<VirtualHost *:443>
        ServerName kavita.example.com
        SSLEngine on
        SSLProxyEngine on
        SSLProxyCheckPeerCN off
        SSLProxyCheckPeerName off
        SSLProxyCheckPeerExpire off
        SSLCertificateFile /etc/univention/letsencrypt/signed_chain.crt
        SSLCertificateKeyFile /etc/letsencrypt/domain.key
        SSLCACertificateFile /etc/ssl/ucsCA/CAcert.pem
        SSLCertificateChainFile /etc/letsencrypt/intermediate.pem
        ErrorLog ${APACHE_LOG_DIR}/proxy-error.log
        CustomLog ${APACHE_LOG_DIR}/proxy-access.log combined
        ProxyPass / http://192.168.1.17:5000/
        ProxyPassReverse / http://192.168.1.17:5000/
        ProxyPreserveHost On
        ProxyRequests Off
        RewriteEngine On
        RewriteCond %{HTTP:UPGRADE} ^WebSocket$ [NC]
        RewriteCond %{HTTP:CONNECTION} ^Upgrade$ [NC]
        RewriteRule .* wss://192.168.1.217%{REQUEST_URI} [P]
        RequestHeader set X-Forwarded-Proto "https"
        RequestHeader set X-Forwarded-Port "443"
        RequestHeader set X-Forwarded-For "%{REMOTE_ADDR}e"
</VirtualHost>
</IfModule>
```
In this example 192.168.1.17 is the IP address of the Kavita host.