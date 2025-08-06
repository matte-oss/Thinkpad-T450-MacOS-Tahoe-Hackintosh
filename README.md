# Thinkpad-T450-MacOS-Tahoe-Hackintosh

<img width="627" height="442" alt="1000019702" src="https://github.com/user-attachments/assets/5de92574-1d08-4250-b941-0c48c6f81ce4" />


⚠️ This is a work in progress and is not ready ⚠️

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

1) [Download the Tahoe beta installassistant.pkg from Apple](https://swcdn.apple.com/content/downloads/05/26/082-89906-A_7DP8EBEVZJ/g3p7sya93v36h1ri0h940xxuxutt23igcw/InstallAssistant.pkg)
2) Partiton a 16gb+ usb drive in 2 partitions:
   - A 500mb (or more) one formatted in Fat32 called Opencore
   - The rest of the drive formatted in exFat, call it Installer
3) [Download the UnPlugged script](https://github.com/corpnewt/UnPlugged/blob/main/UnPlugged.command) and place it into the Installer partition, along with the installassistant.pkg file.

