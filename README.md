# Thinkpad T450(s) MacOS Tahoe Hackintosh 

<img width="627" height="442" alt="1000019702" src="https://github.com/user-attachments/assets/5de92574-1d08-4250-b941-0c48c6f81ce4" />



> [!WARNING]  
> This repo is still a work in progress and is not ready.



> [!CAUTION]
> MacOS Tahoe is still in the beta stage and is not stable

# Bios settings

- `Security -> Security Chip`: **Disabled**;
- `Memory Protection -> Execution Prevention`: **Enabled**;
- `Virtualization -> Intel Virtualization Technology`: **Disabled**;
- `Virtualization -> Vt-directed IO`: **Disabled**;
- `Internal Device Access -> Bottom Cover Tamper Detection`: must be **Disabled**;
- `Anti-Theft -> Computrace -> Current Setting`: **Disabled**;
- `Secure Boot -> Secure Boot`: **Disabled**;
- `UEFI/Legacy Boot`: **UEFI Only**;
- `Fingerprint Sensor`: **Disabled** `(Causes issues with wake from sleep)`;
- `CSM Support`: **Yes**.
- `Intel (R) Rapid Start Technology`: **Disabled**.

# Tutorial

**NOTE:** This tutorial should **ONLY** be used for the Tahoe developer beta, the tutorial will be updated when the stable version comes out.
1) Create an exFat partition called MacOS where we'll install the OS. (Call it MacOS)
2) [Download the Tahoe beta installassistant.pkg from Apple](https://swcdn.apple.com/content/downloads/05/26/082-89906-A_7DP8EBEVZJ/g3p7sya93v36h1ri0h940xxuxutt23igcw/InstallAssistant.pkg) or GibMacOS
3) Partiton a 16gb+ usb drive in 2 partitions:
   - A 500mb (or more) one formatted in Fat32 called Opencore
   - The rest of the drive formatted in exFat, call it Installer
4) [Download the UnPlugged script](https://github.com/corpnewt/UnPlugged/blob/main/UnPlugged.command) and place it into the Installer partition, along with the installassistant.pkg file.
5) [Download Monterey using macrecovery](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/windows-install.html#downloading-macos) and put it into the Opencore partition (com.apple.recovery.boot foler), along with the [Monterey EFI](https://example.com)
> [!NOTE]  
> Monterey is only used to install Tahoe, do not go forward with the Montrey installation
6) Boot in the Monterey recovery and format the exFat partition we previously created in APFS from Disk Utility 
7) Open the terminal (Utilities -> Terminal) and type `cd /Volumes/[your ExFAT volume name]` (in our case Installer)
8) Type `./UnPlugged.command`
9) Type 1 to choose the `Fully expand InstallAssistant.pkg` option
