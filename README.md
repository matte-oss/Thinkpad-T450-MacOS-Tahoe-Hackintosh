# Thinkpad T450(s) MacOS Tahoe Hackintosh 

<img width="627" height="442" alt="1000019702" src="https://github.com/user-attachments/assets/5de92574-1d08-4250-b941-0c48c6f81ce4" />



> [!WARNING]  
> This repo is still a work in progress and is not ready.
> The EFI is not yet relased



> [!CAUTION]
> MacOS Tahoe is still in the beta stage and is not stable


> [!IMPORTANT]
> 
>Your warranty is now void. 
I am not responsible for bricked devices, dead SD cards, thermonuclear war, or you getting fired because the alarm app failed. YOU are choosing to make these modifications, and if you point the finger at me for messing up your device, I will laugh at you.

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
- `CSM Support`: **Yes**;
- `Intel (R) Rapid Start Technology`: **Disabled**.

# Tutorial

**NOTE:** This tutorial should **ONLY** be used for the Tahoe developer beta, the tutorial will be updated when the stable version comes out.

1) Create an exFat partition called MacOS where we'll install the OS. (Call it MacOS)
2) Download the Tahoe beta installassistant.pkg using [Gibmacos](https://github.com/corpnewt/gibMacOS) (If you don't see the Tahoe beta change the version to 26)
4) Partiton a 16gb+ usb drive in 2 partitions:
   - A 500mb (or more) one formatted in Fat32 called Opencore
   - The rest of the drive formatted in exFat, call it Installer
5) [Download the UnPlugged script](https://github.com/corpnewt/UnPlugged/blob/main/UnPlugged.command) and place it into the Installer partition, along with the installassistant.pkg file.
6) [Download Monterey using macrecovery](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/windows-install.html#downloading-macos) and put it into the Opencore partition (com.apple.recovery.boot foler), along with the Monterey EFI from this repo
> [!NOTE]  
> Monterey is only used to install Tahoe, do not go forward with the Montrey installation
6) Boot in the Monterey recovery and format the exFat partition we previously created in APFS from Disk Utility 
7) Open the terminal (Utilities -> Terminal) and type `cd /Volumes/[your ExFAT volume name]` (in our case Installer)
8) Type `./UnPlugged.command`
9) Type 1 to choose the `Fully expand InstallAssistant.pkg` option
10) Choose the MacOS drive as the target one
11) Wait for it to finish and dont close the terminal
12) Go ahead with the Tahoe installation and choose the MacOS Drive
13) Boot back into a working OS (Linux/Windows) and mount the MacOS efi (on Windows you need to use [WinEFIMounter](https://github.com/franzageek/WinEFIMounter) )
14) Copy the Tahoe EFI in the MacOS EFI and boot

# Post-install

Once booted into MacOS you'll notice the GPU acceleration is not working.
Opencore legacy Patcher does NOT yet support Tahoe, so we'll be using an **unofficial** fork called [oclp-mod](https://github.com/laobamac/OCLP-Mod):


> [!CAUTION]
> This method is not officialy supported by the Opencore Legacy Patcher team and may break your system.
> 
1) [Download the oclp-mod Tahoe pre-relase](https://github.com/laobamac/OCLP-Mod/releases/download/push-0605e43c8e50be012ef0bf322b1f28b26bae39b5/OCLP-Mod.pkg)
