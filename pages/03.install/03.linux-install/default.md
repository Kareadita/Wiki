---
title: 'Linux Install'
admin:
    children_display_order: collection
---

## 1. Download

Go to [https://github.com/Kareadita/Kavita/releases/latest](https://github.com/Kareadita/Kavita/releases/latest) and scroll down untill you see the 'assets' section
where there's a list of files that you can download

You should download the one that fits your system

<hr style="border:5px solid #4ac694">

## 2. Install Kavita

1. Unzip the archive to a writable directory with the command `tar -xzf kavita-linux-{arch}.tar.gz`
3. Use `chmod` and `chown` commands so Kavita can write to the directory you placed it in.
4. Run Kavita executable. Usually `./Kavita`

! **Note:**  For unprivileged LXC containers it may be necessary to use `tar -xzf kavita-linux-{arch}.tar.gz --no-same-owner` instead to prevent permission errors while extracting

<hr style="border:2px solid #4ac694">

### Install Kavita as a Service (Optional)

Optionally to have Kavita start in the background at boot, you may install it as a systemd service on your operating system. Save the following to a file named kavita.service in the directory `/etc/systemd/system`.

```ini
[Unit]
Description=Kavita Server
After=network.target

[Service]
User=kavita
Group=kavita
Type=simple
WorkingDirectory=/opt/Kavita
ExecStart=/opt/Kavita/Kavita
TimeoutStopSec=20
KillMode=process
Restart=on-failure

[Install]
WantedBy=multi-user.target
```

!!! **Note**: This file is an example and assumes you have installed Kavita in `/opt/Kavita` and you are running it as a separate user.
<br/>Please change those settings if that is not the case for you.

Once the file is saved you can run `systemctl start kavita.service` to test if it starts correctly, and if does, run `systemctl enable kavita.service` and it will start at boot for your system.

<hr style="border:5px solid #4ac694">

## 3. View Kavita

Browse to http://localhost:5000 to start using Kavita.

! **Note**: `localhost` should be replaced with the IP address of the machine that is running Kavita when accessing from inside your network from a different device like a phone or tablet.

For more instructions on how to make Kavita accessible from outside your home network... see [Accessing Kavita from external network](../10.access-kavita-from-network/default.en.md).

<hr style="border:5px solid #4ac694">

## 4. Updating Kavita

>>>**IMPORTANT**: If you are updating from a really old version you need to upgrade every 2 versions at a time. Doing otherwise you risk to having to restart with a fresh db

Kavita self-updating is down the road. Expected to be released in v0.6.0 per the [project page](https://github.com/Kareadita/Kavita/projects?type=classic)

Before updating Kavita, stop the program/service from running.
1. Follow the guide aguain but:
2. Copy/paste all files __**EXCEPT**__ `config/` to your Kavita install directory.

!!! **Warning**: If you replace `config/`, you will lose your data. 
