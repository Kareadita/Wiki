---
title: 'Windows Install'
---

### 1. Download Kavita

Download the Windows Installer with the following link and execute it. Download [here](https://github.com/Kareadita/Kavita/releases).

### 2. Install Kavita

1. Unzip the archive to a writable directory. Do not place it in `Program Files/` or `Program Files (x86)/`.
2. Run the Kavita executable.
3. Open [http://localhost:5000](http://localhost:5000) and set up your [user accounts](https://wiki.kavitareader.com/guides/user-management) and [Libraries](https://wiki.kavitareader.com/guides/adding-a-library) in the UI.

Alternate methods to run Kavita upon Windows startup are available instead of running the program each time you log in.
- Add a shortcut to Kavita to your Startup Folder in Windows.
- Use the Non-Sucking Service Manager aka [NSSM](https://nssm.cc/) to make Kavita a Windows Service. A user has written a nice [guide](https://www.reddit.com/r/KavitaManga/comments/s6mans/tutorial_how_to_use_nmms_to_create_a_windows/) on Reddit that might be beneficial.

### 3. View Kavita

Browse to [http://localhost:5000](http://localhost:5000) to start using Kavita from any device inside your network. A Windows Firewall rule allowing incoming access to port 5000 may be required.

! `localhost` should be replaced with the IP address of the machine that is running Kavita when accessing from inside your network from a different device like a phone or tablet.
For more instructions on how to make Kavita accessible from outside your home network... see the [Reverse Proxy](https://wiki.kavitareader.com/install/reverse-proxy) page.

### 4. Updating
To update Kavita, stop the program/service from running and copy/paste all files EXCEPT `config/` to your Kavita install directory. If you replace `config/`, you will lose your data. 
