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
The asset files are compressed in a .tar.gz file. You can use free software like [7zip](https://www.7-zip.org/download.html) to extract the files. Once the files are extracted to a location, you just need to run `Kavita.exe` to launch the server. 

<hr style="border:2px solid #4ac694">

### Scoop

#### 1. Install Scoop (skip this if you've installed Scoop)
Go [here](https://github.com/ScoopInstaller/Install#installation) for latest Scoop installation instructions.

#### 2. Install Kavita
Run `scoop bucket add extras` and then run `scoop install kavita`.

<hr style="border:5px solid #4ac694">

## Updating Kavita

>>>**IMPORTANT**: If you are updating from a really old version you need to upgrade every 2 versions at a time. Doing otherwise you risk to having to restart with a fresh db.

Before updating Kavita, stop the program/service from running.

<hr style="border:2px solid #4ac694">

### Github Release
1. Download the latest version from the same link in the [installation section](#github-release) (always points to latest)
2. Extract all Files to a temp folder
3. Copy/paste all files __**EXCEPT**__ `config/` to your Kavita install directory. When prompted, overwrite the files with the new copies.

!! **Warning**: If you replace `config/`, you will lose your data. 

<hr style="border:2px solid #4ac694">

### Scoop
Run `scoop update kavita`

<hr style="border:5px solid #4ac694">

## Start Kavita
Run the Kavita executable. If you've installed Kavita using Scoop, you can search `Kavita` on you Windows Start Menu and then open it.

Alternate methods to run Kavita upon Windows startup are available instead of running the program each time you log in.
- Add a shortcut to Kavita to your Startup Folder in Windows.
- Use the Non-Sucking Service Manager aka [NSSM](https://nssm.cc/) to make Kavita a Windows Service. A user has written a nice [guide](https://www.reddit.com/r/KavitaManga/comments/s6mans/tutorial_how_to_use_nmms_to_create_a_windows/) on Reddit that might be beneficial.
- [Shawl](https://github.com/mtkennerly/shawl) is a more updated option to run programs as a service on windows. 

<hr style="border:5px solid #4ac694">

## View Kavita

! **Note**: `localhost` should be replaced with the IP address of the machine that is running Kavita when accessing from inside your network from a different device like a phone or tablet.
For more instructions on how to make Kavita accessible from outside your home network... see the [Reverse Proxy](https://wiki.kavitareader.com/install/access-kavita-from-network#reverse-proxy) page.

Open [http://localhost:5000](http://localhost:5000) and set up your [user accounts](https://wiki.kavitareader.com/guides/user-management) and [Libraries](https://wiki.kavitareader.com/guides/adding-a-library) in the UI.

To get your machines IP address you can use the powershell command:
```powershell
Get-NetIPAddress | Format-Table
```
It will likely list a lot of different adapters but your IP should be within the list. Most likely one that starts with 192.168.*.* or 10.*.*.*

If you want to start using Kavita from any device inside your network, a Windows Firewall rule allowing incoming access to port 5000 may be required.
The first time you run `kavita.exe` it will prompt you to allow connections. If you missed the prompt or it's not working, you can use this powershell command to open port 5000:

```powershell
New-NetFirewallRule -DisplayName 'Kavita' -Profile @('Private') -Direction Inbound -Action Allow -Protocol TCP -LocalPort @('5000')
```


