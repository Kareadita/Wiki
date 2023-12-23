---
title: 'Apache2 Example'
---

These examples assume that Kavita is running on host 192.168.0.152 port 5000, and that apache is being used for SSL termination (Kavita is running http). If you intend for apache to serve http alone, rather than https with a redirect for http, you will need to make your virtualhost definitions use port 80, and remove all of the config lines starting with SSL. If upstream is running serving https, you'll need to modify the proxy lines to reference https and the websocket lines to reference wss instead of ws.

### Basic Apache2 Example
```
<IfModule mod_ssl.c>
<VirtualHost *:443>
        ServerName example.com
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
        ProxyPass / http://192.168.0.152:5000/
        ProxyPassReverse / http://192.168.0.152:5000/
        ProxyPreserveHost On
        ProxyRequests Off
        RewriteEngine On
        RewriteCond %{HTTP:UPGRADE} ^.*WebSocket.*$ [NC]
        RewriteCond %{HTTP:CONNECTION} ^.*Upgrade.*$ [NC]
        RewriteRule .* ws://192.168.0.152:5000%{REQUEST_URI} [P]
        RequestHeader set X-Forwarded-Proto "https"
        RequestHeader set X-Forwarded-Port "443"
        RequestHeader set X-Forwarded-For "%{REMOTE_ADDR}e"
</VirtualHost>
</IfModule>
```

### Kavita on a new domain/subdomain
```
<VirtualHost *:80>
# Since, We are using HTTPS, we redirect all HTTP queries to HTTPS.
# If you want to use HTTP only, then copy the 4 lines that start with Proxy and 3 lines that start with Rewrite below and paste them here. Also delete/comment out the redirect line, and the entire second virtualhost block.
        ServerName subdomain.example.com
# ServerName is the name of the domain/subdomain Kavita is being hosted on.
        Redirect permanent / https://subdomain.example.com
</VirtualHost>
<VirtualHost *:443>
    ServerName subdomain.example.com
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
# This specifies the location where your logs are stored. By default, it is stored in a combined log with all other apache configs.

    SSLEngine on
    SSLProxyEngine on
    SSLProxyVerify none
    SSLProxyCheckPeerCN off
    SSLProxyCheckPeerName off
    SSLProxyCheckPeerExpire off
# All of these are for the SSL and Reverse Proxy. If you need more info, refer here https://httpd.apache.org/docs/2.4/mod/mod_ssl.html

    SSLCertificateFile /etc/univention/letsencrypt/signed_chain.crt
    SSLCertificateKeyFile /etc/letsencrypt/domain.key
    SSLCACertificateFile /etc/ssl/ucsCA/CAcert.pem
    SSLCertificateChainFile /etc/letsencrypt/intermediate.pem
# Since we are using SSL, we will have to give locations for all the SSL Certificates. Note - Apache must be able to go into the directories you mention in the path above. (This means that the directory needs to have o+x or have apache as user or group of the directory.)

    ProxyPreserveHost On
    ProxyRequests Off
    ProxyPass / http://192.168.0.152:5000/
    ProxyPassReverse / http://192.168.0.152:5000/
    RewriteCond %{HTTP:UPGRADE} ^.*WebSocket.*$ [NC]
    RewriteCond %{HTTP:CONNECTION} ^.*Upgrade.*$ [NC]
    RewriteRule .* ws://192.168.0.152:5000%{REQUEST_URI} [P]
# For more info on Apache Proxy Config, see here https://httpd.apache.org/docs/2.4/mod/mod_proxy.html
# These lines tell Apache to send all requests to the root of the domain (/) to (http://192.168.0.152:5000/)
# The example assumes that Kavita is hosted on the IP 192.168.0.152. Use localhost if Kavita is on the same machine as Apache.
    
</VirtualHost>
```


### Kavita on an existing domain with subpath
When using this, make sure you set the Base URL field in Kavita Settings.
```
<VirtualHost *:80>
# Since, We are using HTTPS, we redirect all HTTP queries to HTTPS.
# If you want to use HTTP only, then copy the 9 lines below and paste them here
      <...Your existing config lines go here...>
</VirtualHost>
<VirtualHost *:443>
<...Your existing config lines go here ...>
ProxyPreserveHost On
ProxyRequests Off
<Location /kavita>
        ProxyPass http://192.168.0.152:5000
        ProxyPassReverse http://192.168.0.152:5000
        RewriteCond %{HTTP:UPGRADE} ^.*WebSocket.*$ [NC]
        RewriteCond %{HTTP:CONNECTION} ^.*Upgrade.*$ [NC]
        RewriteRule .* ws://192.168.0.152:5000%{REQUEST_URI} [P]
</Location>
# For HTTP config, the above 9 lines need to be copied and pasted.
# These lines tell Apache to send all requests from the subpath of the domain (/kavita) to (http://192.168.0.152:5000/)
# The example assumes that Kavita is hosted on the IP 192.168.0.152. Use localhost if Kavita is on the same machine as Apache.
    <... Your existing config lines go here...>
</VirtualHost>
```
