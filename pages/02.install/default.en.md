---
title: 'Installation Guides'
---

## Installation Guides

These are the guides for the supported systems

* [Windows](https://wiki.kavitareader.com/install/windows-install) 
* [Linux](https://wiki.kavitareader.com/install/linux-install)
* [Docker](https://wiki.kavitareader.com/install/docker-install)
* [macOS](https://wiki.kavitareader.com/install/macos)
* Various NAS devices like [Unraid](https://wiki.kavitareader.com/install/unraid), [TrueNAS Scale](https://wiki.kavitareader.com/en/install/truenas-scale), or [OpenMediaVault](https://www.openmediavault.org/)
* [Synology](https://wiki.kavitareader.com/en/install/synology)

>>> There's an article that explains how to restore a backup if needed in [this page](backup.en.md) 

## Accessing Kavita from external network

### Operating Systems supported by Kavita

### Windows

| OS                                    | Version            | Architectures   | Lifecycle                                  |
|---------------------------------------|--------------------|-----------------|--------------------------------------------|
| [Windows Client][Windows-client]      | 7 SP1(**\***), 8.1 | x64, x86        | [Windows][Windows-lifecycle]               |
| [Windows 10 Client][Windows-client]   | Version 1607+      | x64, x86, Arm64 | [Windows][Windows-lifecycle]               |
| [Windows Server][Windows-Server]      | 2012 R2+           | x64, x86        | [Windows Server][Windows-Server-lifecycle] |
| [Windows Server Core][Windows-Server] | 2012 R2+           | x64, x86        | [Windows Server][Windows-Server-lifecycle] |
| [Nano Server][Nano-Server]            | Version 1809+      | x64             | [Windows Server][Windows-Server-lifecycle] |

**\*** Windows 7 SP1 is supported with [Extended Security Updates](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq) installed.

[Windows-client]: https://www.microsoft.com/windows/
[Windows-lifecycle]: https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet
[win-client-docker]: https://hub.docker.com/_/microsoft-windows
[Windows-Server-lifecycle]: https://docs.microsoft.com/windows-server/get-started/windows-server-release-info
[Nano-Server]: https://docs.microsoft.com/windows-server/get-started/getting-started-with-nano-server
[Windows-Server]: https://docs.microsoft.com/windows-server/

### Linux

| OS                                   | Version                           | Architectures     | Lifecycle                          |
|--------------------------------------|-----------------------------------|-------------------|------------------------------------|
| [Alpine Linux][Alpine]               | 3.11+                             | x64, Arm64        | [Alpine][Alpine-lifecycle]         |
| [CentOS][CentOS]                     | 7+                                | x64               | [CentOS][CentOS-lifecycle]         |
| [Debian][Debian]                     | 9+                                | x64, Arm32, Arm64 | [Debian][Debian-lifecycle]         |
| [Fedora][Fedora]                     | 32+                               | x64               | [Fedora][Fedora-lifecycle]         |
| [Linux Mint][Linux-Mint]             | 18+                               | x64               | [Linux Mint][Linux-Mint-lifecycle] |
| [openSUSE][OpenSUSE]                 | 15+                               | x64               | [OpenSUSE][OpenSUSE-lifecycle]     |
| [Red Hat Enterprise Linux][RHEL]     | 7+                                | x64               | [Red Hat][RHEL-lifecycle]          |
| [SUSE Enterprise Linux (SLES)][SLES] | 12 SP2+                           | x64               | [SUSE][SLES-lifecycle]             |
| [Ubuntu][Ubuntu]                     | 21.04, 20.10, 20.04, 18.04, 16.04 | x64, Arm32, Arm64 | [Ubuntu][Ubuntu-lifecycle]         |

[Alpine]: https://alpinelinux.org/
[Alpine-lifecycle]: https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases
[CentOS]: https://www.centos.org/
[CentOS-lifecycle]:https://wiki.centos.org/FAQ/General
[CentOS-docker]: https://hub.docker.com/_/centos
[CentOS-pm]: https://docs.microsoft.com/dotnet/core/install/linux-package-manager-centos8
[Debian]: https://www.debian.org/
[Debian-lifecycle]: https://wiki.debian.org/DebianReleases
[Debian-pm]: https://docs.microsoft.com/dotnet/core/install/linux-package-manager-debian10
[Fedora]: https://getfedora.org/
[Fedora-lifecycle]: https://fedoraproject.org/wiki/End_of_life
[Fedora-docker]: https://hub.docker.com/_/fedora
[Fedora-msft-pm]: https://docs.microsoft.com/dotnet/core/install/linux-package-manager-fedora32
[Fedora-pm]: https://fedoraproject.org/wiki/DotNet
[Linux-Mint]: https://linuxmint.com/
[Linux-Mint-lifecycle]: https://forums.linuxmint.com/viewforum.php?f=143
[OpenSUSE]: https://opensuse.org/
[OpenSUSE-lifecycle]: https://en.opensuse.org/Lifetime
[OpenSUSE-docker]: https://hub.docker.com/r/opensuse/leap
[OpenSUSE-pm]: https://docs.microsoft.com/dotnet/core/install/linux-package-manager-opensuse15
[RHEL]: https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux
[RHEL-lifecycle]: https://access.redhat.com/support/policy/updates/errata/
[RHEL-msft-pm]: https://docs.microsoft.com/dotnet/core/install/linux-package-manager-rhel8
[RHEL-pm]: https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/developing_.net_applications_in_rhel_8/using-net-core-on-rhel_gsg#installing-net-core_gsg
[SLES]: https://www.suse.com/products/server/
[SLES-lifecycle]: https://www.suse.com/lifecycle/
[SLES-pm]: https://docs.microsoft.com/dotnet/core/install/linux-package-manager-sles15
[Ubuntu]: https://ubuntu.com/
[Ubuntu-lifecycle]: https://wiki.ubuntu.com/Releases
[Ubuntu-pm]: https://docs.microsoft.com/dotnet/core/install/linux-package-manager-ubuntu-2004

### macOS

| OS             | Version | Architectures |
|----------------|---------|---------------|
| [macOS][macOS] | 10.13+  | x64           |

[macOS]: https://support.apple.com/macos

## Backup
If you need to restore a backup, do not fret. It is incredibly easy. 

There are two ways to approach a backup. 

First, if you are seeing errors on an update to a new version, you can get an old version of your database from `config/temp/version/kavita.db` This is a quick backup that occurs when database migrations are needed on an upgrade. You can just copy and paste this over your database in config/ and retry. 

If you however have some bad data and need to restore, then check `config/backups` for a zip of all user data. The scheduled backup (server settings) will save your database, appsettings.json, covers, themes, and bookmarks. You just need to copy and paste these over the config folder and restart. 
