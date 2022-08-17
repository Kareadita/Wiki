---
title: 'Windows Install'
---

You can install Kavita on Windows either from [Github releases](#github-release) or using [Scoop](#scoop)

## Installation

### Github Release

#### 1. Download Kavita

Download the Windows Installer with the following link. Download [here](https://github.com/Kareadita/Kavita/releases).

#### 2. Install Kavita

Unzip the archive to a writable directory. Do not place it in `Program Files/` or `Program Files (x86)/`.

### Scoop

#### 1. Install Scoop (skip this if you've installed Scoop)
Go [here](https://github.com/ScoopInstaller/Install#installation) for latest Scoop installation instructions.

#### 2. Install Kavita
Run `scoop bucket add extras` and then run `scoop install kavita`.

## Start Kavita
Run the Kavita executable. If you've installed Kavita using Scoop, you can can search `Kavita` on you Windows Start Menu and then open it.

Alternate methods to run Kavita upon Windows startup are available instead of running the program each time you log in.
- Add a shortcut to Kavita to your Startup Folder in Windows.
- Use the Non-Sucking Service Manager aka [NSSM](https://nssm.cc/) to make Kavita a Windows Service. A user has written a nice [guide](https://www.reddit.com/r/KavitaManga/comments/s6mans/tutorial_how_to_use_nmms_to_create_a_windows/) on Reddit that might be beneficial.

## View Kavita

Open [http://localhost:5000](http://localhost:5000) and set up your [user accounts](https://wiki.kavitareader.com/guides/user-management) and [Libraries](https://wiki.kavitareader.com/guides/adding-a-library) in the UI.

If you want to start using Kavita from any device inside your network, a Windows Firewall rule allowing incoming access to port 5000 may be required.

! `localhost` should be replaced with the IP address of the machine that is running Kavita when accessing from inside your network from a different device like a phone or tablet.
For more instructions on how to make Kavita accessible from outside your home network... see the [Reverse Proxy](https://wiki.kavitareader.com/install/reverse-proxy) page.

## Updating Kavita
Before updating Kavita, stop the program/service from running.

### Github Release
Copy/paste all files EXCEPT `config/` to your Kavita install directory. If you replace `config/`, you will lose your data. 

### Scoop
Run `scoop update kavita`.
