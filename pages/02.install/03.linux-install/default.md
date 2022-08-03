---
title: 'Linux Install'
admin:
    children_display_order: collection
---

#### 1. Download Kavita

Download the latest Linux archive with the following link and execute it. [Releases](https://github.com/Kareadita/Kavita/releases)

#### 2. Install Kavita

1. Unzip the archive to a writable directory.
2. Use `chmod` and `chown` commands so Kavita can write to the directory you placed it in.
3. Run Kavita executable. Usually `./Kavita`
4. Open http://localhost:5000 and set up your [user accounts](https://wiki.kavitareader.com/guides/user-management) and [Libraries](https://wiki.kavitareader.com/guides/adding-a-library) in the UI.


#### 3. View Kavita

Browse to http://localhost:5000 to start using Kavita.

#### 4. Install Kavita as a Service (Optional)

Optionally to have Kavita start in the background at boot, you may install it as a systemd service on your operating system. Save the following to a file named kavita.service in the directory `/etc/systemd/system`.

```
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

This file is an example and assumes you have installed Kavita to /opt/Kavita and you are running it as a separate user. Please change those settings if that is not the case for you.

Once the file is saved you can run `systemctl start kavita.service` to test if it starts correctly, and if does, run `systemctl enable kavita.service` and it will start at boot for your system.

### 5. Updating
In order to update Kavita, stop the program/service from running and copy/paste all files EXCEPT config/ to your Kavita install directory. If you replace the config, you will lose your data. 

! **Note**: Please contact us if you wish to port Kavita for any other distro.



