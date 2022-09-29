---
title: macOS
---

### Introduction
! No one on the dev team owns a Mac. These instructions are suggested by our users. If you think you can improve them, please [edit this wiki](https://github.com/Kareadita/Wiki/edit/main/pages/02.install/04.macos/default.md) and submit a PR.

1. [Download Kavita for macOS](https://www.kavitareader.com/#downloads-v1-macos)
2. Unpack Kavita to your User Folder or folder of choice.
3. Make Kavita executable.
    * In Terminal: `sudo chmod +x ~/Kavita/Kavita`
4. Disable Gatekeeper for Kavita's folder so that Kavita and all .dll and .dylib files can be opened
    * In Terminal: `xattr -r -d com.apple.quarantine ~/Kavita/Kavita`
5. Help Kavita find sqlite
    * In Terminal: `export alias sqlite=sqlite3`
6. Start Kavita with right-click -> Open (or in Terminal: `~/Kavita/Kavita` )
7. Open a browser window, at address: http://localhost:5000/

### Troubleshooting
8. Change the port number if there's a clash, e.g. this error reported to the Terminal or log file (`config/logs/kavita.log`):
   `Unhandled exception. System.IO.IOException: Failed to bind to address http://[::]:5000: address already in use.`
    * Edit the file `config/appsettings.json` and change the value near the end to 
      `"Port": 5555`
7. Open a browser window, at address: http://localhost:5555/

> [!NOTE]
> After this, you can refer to the Linux section for running Kavita as a service. 
