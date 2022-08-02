---
title: macOS
---

### Introduction
! No one on the dev team owns a Mac. These instructions are suggested by our users. If you think you can improve them, please submit a PR.

1. [Download Kavita for macOS](https://www.kavitareader.com/#downloads-v1-macos)
2. Unpack Kavita to your User Folder or folder of choice.
3. Make Kavita executable.
    * In Terminal: `sudo chmod +x ~/Kavita/Kavita`
4. Disable Gatekeeper for Kavita's folder so that Kavita and all .dll and .dylib files can be opened
    * In Terminal: `attrx -r -d com.apple.quarantine ~/Downloads/Kavita`
5. Start Kavita with right-click -> Open (or in Terminal: `~/Kavita/Kavita` )

After this, you can refer to the Linux section for running Kavita as a service. 
