---
title: 'Windows Install'
---

## Installation

You can install Kavita on Windows either from [GitHub releases](#github-release) or using [Scoop](#scoop)

<hr style="border:2px solid #4ac694">

### GitHub Release

Go to [https://github.com/Kareadita/Kavita/releases/latest](https://github.com/Kareadita/Kavita/releases/latest) and scroll down untill you see the 'assets' section
Here there's a list of files that you can download

You should download the one that says `kavita-win-x??`.
- Download the x64 if you have a 64-bit system (usually the preferred version)
- Download the x86 if you have a 32-bit system (usually older devices)

Unzip the archive to a writable directory.

! **Important** Do not place it in `Program Files/` or `Program Files (x86)/`.

!!! **Note**: Kavita's releases are made to be used out of the box. This means there's no need to install extra requirements
They are compressed in a .tar.gz file. You can use free software like 7zip to extract the files

<hr style="border:2px solid #4ac694">

### Scoop

#### 1. Install Scoop (skip this if you've installed Scoop)
Go [here](https://github.com/ScoopInstaller/Install#installation) for latest Scoop installation instructions.

#### 2. Install Kavita
Run `scoop bucket add extras` and then run `scoop install kavita`.

<hr style="border:5px solid #4ac694">

## Updating Kavita
Kavita self-updating is down the road. Expected to be released in v0.5.6 per the [project page](https://github.com/Kareadita/Kavita/projects?type=classic)

Before updating Kavita, stop the program/service from running.

<hr style="border:2px solid #4ac694">

### Github Release
1. Download the latest version from the same link (always points to latest)
2. Extract all Files to a temp folder
3. Copy/paste all files __**EXCEPT**__ `config/` to your Kavita install directory.
!!! **Warning**: If you replace `config/`, you will lose your data. 

<hr style="border:2px solid #4ac694">

### Scoop
Run `scoop update kavita`

<hr style="border:5px solid #4ac694">

## Start Kavita
Run the Kavita executable. If you've installed Kavita using Scoop, you can search `Kavita` on you Windows Start Menu and then open it.

Alternate methods to run Kavita upon Windows startup are available instead of running the program each time you log in.
- Add a shortcut to Kavita to your Startup Folder in Windows.
- Use the Non-Sucking Service Manager aka [NSSM](https://nssm.cc/) to make Kavita a Windows Service. A user has written a nice [guide](https://www.reddit.com/r/KavitaManga/comments/s6mans/tutorial_how_to_use_nmms_to_create_a_windows/) on Reddit that might be beneficial.

<hr style="border:5px solid #4ac694">

## View Kavita

Open [http://localhost:5000](http://localhost:5000) and set up your [user accounts](https://wiki.kavitareader.com/guides/user-management) and [Libraries](https://wiki.kavitareader.com/guides/adding-a-library) in the UI.

If you want to start using Kavita from any device inside your network, a Windows Firewall rule allowing incoming access to port 5000 may be required.

! **Note**: `localhost` should be replaced with the IP address of the machine that is running Kavita when accessing from inside your network from a different device like a phone or tablet.
For more instructions on how to make Kavita accessible from outside your home network... see the [Reverse Proxy](https://wiki.kavitareader.com/install/reverse-proxy) page.

