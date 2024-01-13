---
title: 'Accessing Kavita from external network'
---

There are plenty ways to access your kavita from the external network.

This means access your kavita instance in your home when you are outside

These are the recommended ways:

|     Name      | Public Access | Requires external software | Notes                       |
|:-------------:|:-------------:|:--------------------------:|-----------------------------|
|      VPN      |      No       |            Yes             | Recommended for single user |
| Reverse Proxy |      Yes      |             No             | Recommened for multiuser    |

<hr style="border:5px solid #4ac694">

## Reverse Proxy
### What is a [Reverse Proxy](https://en.wikipedia.org/wiki/Reverse_proxy)?

A Reverse Proxy allows you to share web-based services, like Kavita, outside your home network through the upload bandwidth of your home internet connection.

This can be accomplished in several ways including a purchased domain name, a free domain name service such as [NoIP.com](https://www.noip.com/), etc in combination with some form of Dynamic DNS.

We will not cover how to achieve this here, but we will provide resources and examples of common Reverse Proxy configuration files.

If you would like to contribute your working Reverse Proxy config please join us in [Discord](https://discord.gg/b52wT37kt7) to discuss. 

### Config examples

* [NGINX Example](reverse-proxy/01.nginx-example/default.md)
* [NGINX Proxy Manager Example](reverse-proxy/nginx-proxy-manager-example)
* [HAPROXY Example](reverse-proxy/haproxy-example)
* [Caddy Example](reverse-proxy/caddy-example)
* [Apache2 Example](reverse-proxy/apache2-example)
* [SWAG Example](reverse-proxy/swag-example)

<hr style="border:5px solid #4ac694">

## VPN
If you plan to host your kavita for yourselves and don't want to have public access to your server you should setup a vpn. 

Users usually recommend using Zerotier for this purpose. It's a free easy to setup vpn. Which doens't require any technical skill.

To set up:
- Create an account at the main page and create a network
- Install the app in both the server and any device you wish to use
- Join the created network in your devices
- Authorize the devices in the network main panel

