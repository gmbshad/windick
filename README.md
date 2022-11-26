#     ■■■■■■■■■■■■■■■■■■■■■■■■■■
#   $-h-@-Z-Z-@-m!
A native command shell Windows image deployment tool.
#     ■■■■■■■■■■■■■■■■■■■■■■■■■■
# Administrate · Develop · Build · Dismantle · Backup · Test · Customize
From boot to deploy, the one and only complete Windows image container-based deployment recovery solution.
- Windows-To-Go (USB) / Windows-To-Stay (SSD)
- 
- Autopilot: Automatically reboot to a customizable scripted recovery environment triggered by host OS events
![Alt text](/png/AutoPilot.png "AutoPilot")
- NEW FEATURE: Autopilot scripted recovery-failover / boot-shuffler. AutoPilot.cmd must be in the main program folder or the operation will fail. Allows for condition based offline VHDX-backup/restore/swap/testing. The only condition to trigger this when enabled, is a reboot.
- NEW FEATURE: Toggle between Recovery / VHDX-Boot priority from within recovery or live in Windows
- 
- Package Creator (.$PK) · Driver · Scripted · Storage · Approve/Deny ·
- List-Base Extract System (.MST) - Generate list-base from · WIM · VHDX · Live ·
- Advanced List Sorting System (.LST) - Create lists to · Enable · Disable · Add · Delete ·
-      · AppX · Drivers · Features · Components · Packages · Services · Tasks · Updates
- Mount, deploy and administrate virtual hard disk images (VHDX) and WIM's from within recovery or live in Windows
- 10 Native VHDX-Boot slots are enabled in Slot-Mode for redundancy.
- Simplified 2 partition system. EFI / Data only. No MSR, no WinRE, no B.S. - Windows is contained in a single VHDX file
- No dependencies or external applications, just $haZZam.cmd and Windows installation source
- Customize Windows images with an endless number of packs/lists. Import/Export Drivers
- Express image forensics of WIM/VHDX/LIVE - Inspect your images with a single button. Generate a list of registry startup items, services, tasks, appX, features and components
- Clean-room developed. Evolution & culmination of my personal deployment scripts, 7+ years in the making
![Alt text](/png/0-0.png "Help Section")
To get started: Place $haZZam.cmd in a folder. Mount a Windows ISO, or insert a windows disc, then open $haZZam.cmd.
#     ■■■■■■■■■■■■■■■■■■■■■■■■■■
Boot Creator (via Diskpart+DISM)
#     ■■■■■■■■■■■■■■■■■■■■■■■■■■
Provided with a Windows installation source, $haZZam can create a simple yet robust bootable WinPE recovery/testing environment.
- The basic environment is absent of explorer shell, start-menu, or other luxuries.
- However since $haZZam uses live off the land commands, you can survive this outback without 3rd-party apps.
- All is not lost, there are some handy macros located on the main menu and some basic functionalities to help get by.
![Alt text](/png/RamDisk.png "WinPE Ramdisk Mode")
The recovery environment you never knew you needed!
- In Name-Mode, 1 VHDX-Boot slot is generated in the BCDSTORE and uses the name of the VHDX as the BCD description.
- In Slot-Mode, 10 VHDX-Boot slots are generated in the BCDSTORE and are available for use.
- In Slot-Mode, any VHDX's named between 0-9.VHDX located in the home folder are bootable and can be swapped if not currently active.
- If you need redundancy I suggest starting with slot 5 first, giving you room to move in either direction.
- Tutorial: https://social.technet.microsoft.com/wiki/contents/articles/54560.windows-1011-how-to-implement-a-bootable-windows-pe-recovery-deployment-environment-in-command-shell.aspx
![Alt text](/png/5-3.png "Boot Creator")
Boot Creator
![Alt text](/png/21H2.png "Native VHDX Boot")
Native VHDX-Boot W11 22H2
#     ■■■■■■■■■■■■■■■■■■■■■■■■■■
Disk Managment (via DiskPart) with basic support for:
-      inspect · format · mount · create · delete · wipe · change UID · lock partition · USB unplug
![Alt text](/png/5-1.png "Disk Managment")
- Toggle between Recovery & VHDX-Boot
#     ■■■■■■■■■■■■■■■■■■■■■■■■■■
File Managment (via CMD's) with basic support for:
-      open · duplicate · copy · rename · move · delete · take ownership+grant perm · symbolic link creation
![Alt text](/png/4-1.png "File Managment")
#     ■■■■■■■■■■■■■■■■■■■■■■■■■■
Image Processing (via DISM)  · Backup · Restore · Convert · Isolate  · for archive or active use, with support for:
-      WIM · VHDX 
![Alt text](/png/2-1.png "Image Processing")
#     ■■■■■■■■■■■■■■■■■■■■■■■■■■
Image Managment (via DISM)
#     ■■■■■■■■■■■■■■■■■■■■■■■■■■
![Alt text](/png/1-1.png "Image Managment")
- Express Image Forensics of:
-      VHDX · WIM · LIVE
- Create lists to · Enable · Disable · Add · Delete
-     AppX · Features · Components · Services · Tasks · Updates
![Alt text](/png/1-5.png "Image Managment")
![Alt text](/png/1-6.png "Image Managment")
- Create lists to Install:
-      MSU · CAB · $PK
![Alt text](/png/1-2.png "Image Managment")
- Apply these batch lists to :
-      WIM · VHDX · LIVE
![Alt text](/png/1-8.png "List-of-Lists")
- A List-of-Lists to combine multiple batch actions
![Alt text](/png/1-7.png "List-of-Lists")
#     ■■■■■■■■■■■■■■■■■■■■■■■■■■
Package Creator (via DISM) 
#     ■■■■■■■■■■■■■■■■■■■■■■■■■■
- Create $PK packages · All $PK packages are WIM based, with an additional compartment for the package manifest.
- The package manifest determines how the package is treated. It contains the type of package, and optional install conditions.
- Scripted Packages · integration of REG/MSI/EXE/XYZ
- Driver Packages · export/import with a button.
- Storage - Not the best compression ratio, but the option is there.
![Alt text](/png/3-2.png "Package Creator")
- Create optional $PK package installation conditions. (basic approval/denial)
- For now, the condition system is registry query based only. There is a demo example included.
![Alt text](/png/3-1.png "Package Creator")
- A few of the built-in package examples to get you started:
-      · Strict LSA Rules · UAC Always · Store/OneDrive/Cloud/Wakelocks/Pagefile Disable ·
-      · User/Admin Account Creation · Import/Export Firewall Rules · Unattend.XML · General MSI/Setup.exe examples
![Alt text](/png/3-3.png "Package Creator")
- Package installation timing granularity for different use cases:
- ImageApply        ·  Setup Phase 0  ·  Apply directly to image, no user accounts exist, changes are applied to DefaultUser instead.
- SetupComplete     ·  Setup Phase 1  ·  1st boot, machine credentials, installations not requiring an active user.
- RunOnce·Async     ·  Setup Phase 2  ·  1st user logon, user credentials, installations requiring an active user.
#     ■■■■■■■■■■■■■■■■■■■■■■■■■■
$haZZam command-line parameters 
#     ■■■■■■■■■■■■■■■■■■■■■■■■■■
-     $haZZam.cmd -help                                                    (This Menu)
·         (Image Management List Installer)
-      $haZZam.cmd -listmgr -install -list xyz.lst                         (Live-Install Package-List)
#     ■■■■■■■■■■■■■■■■■■■■■■■■■■
·         (Image Processing)
- WIM/VHDX Source Images must be placed in their respective folders or the operation will fail.
-     $haZZam.cmd -imageproc -wim {ABC.WIM} -index {INDEX} -vhdx {123.VHDX} -size {MB}
-     $haZZam.cmd -imageproc -wim  {ABC.WIM} -index {INDEX} -wim {ABC.WIM} -xlvl {FAST/MAX}
-     $haZZam.cmd -imageproc -vhdx {123.VHDX} -index {INDEX} -wim {ABC.WIM} -xlvl {FAST/MAX}
·        Examples:
-     $haZZam.cmd -imageproc -wim ABC.WIM -index 1 -vhdx 123.VHDX -size 25600
-     $haZZam.cmd -imageproc -wim ABC.WIM -index 1 -wim ABC.WIM -xlvl fast
-     $haZZam.cmd -imageproc -vhdx 123.VHDX -index 1 -wim ABC.WIM -xlvl fast
·         (Disk Manager)
- You can address disks by static disk-UID or by DISK #,  since both are parsed together internally.
-     $haZZam.cmd -diskmgr -list                                           (Condensed list of Disks)
-     $haZZam.cmd -diskmgr -getdisk -disk {#} /or/ -diskid {ID}            (Query Disk # / Disk ID)
-     $haZZam.cmd -diskmgr -inspect -disk {#} /or/ -diskid {ID}            (Full DiskPart Inquiry on Specified Disk)
-     $haZZam.cmd -diskmgr -erase -disk {#} /or/ -diskid {ID}              (Delete All Partitions on Specified Disk)
-     $haZZam.cmd -diskmgr -changeid -disk {#} /or/ -diskid {ID} {NEW ID}  (Change Disk ID of Specified Disk)
-     $haZZam.cmd -diskmgr -create -disk {#} /or/ -diskid {ID} -size {MB}  (Create NTFS Partition on Specified Disk)
-     $haZZam.cmd -diskmgr -format -disk {#} /or/ -diskid {ID} -part {#}   (Format Partition w/NTFS on Specified Disk)
-     $haZZam.cmd -diskmgr -delete -disk {#} /or/ -diskid {ID} -part {#}   (Delete Partition on Specified Disk)
-     $haZZam.cmd -diskmgr -lock -disk {#} /or/ -diskid {ID} -part {#}     (Mark Partition GUID as "Do Not Mount")
-     $haZZam.cmd -diskmgr -unmount -letter {LTR}                          (Remove Drive Letter)
-     $haZZam.cmd -diskmgr -mount -disk {#} /or/ -diskid {ID} -part {#} -letter {LTR}    (Assign Drive Letter + unlock)
·        Examples:
-     $haZZam.cmd -diskmgr -create -disk 0 -size 25600
-     $haZZam.cmd -diskmgr -mount -disk 0 -part 1 -letter e
-     $haZZam.cmd -diskmgr -mount -diskid 12345678-1234-1234-1234-123456781234 -part 1 -letter e
#     ■■■■■■■■■■■■■■■■■■■■■■■■■■
·         (Boot Environment Creator)
-     The specified boot-media and VHDX must be in the main program folder or the operation will fail.
-     $haZZam.cmd -bootmaker -create -disk 0 -src BOOT.WIM -vhdx 123.VHDX
-     $haZZam.cmd -bootmaker -create -diskid 12345678-1234-1234-1234-123456781234 -src BOOT-MEDIA.SAV -vhdx 123.VHDX
![Alt text](/png/0-2.png "Boot Creator")
#     ■■■■■■■■■■■■■■■■■■■■■■■■■■
- Customize with classic ascii themes straight from the 1970's, RGB or even the cha-cha!
- All imaging operations occur inside of a Virtual Hard Disk Image,  leaving no garbage folders/files behind.
- No dependencies, Just $haZZam.cmd and a Windows installation source.
- Recommended to use builds 22000+. Always use official sources, unless you're trying to analyze malware. (vhdx-boot w/host-partition-lock is a great way to do this...)
- Currently $haZZam is made of 100% batch, no embedded scripts of any kind. That means no embedded:
-      · powershell · visualbasic · java · any type of encoding or obfuscation. 
- This program should always be in its raw and readable form, a .CMD file.  Which can be easily viewed and edited in notepad.
- The possibility exists for malacious entities to modify this program into something truly nightmarish.
- So don't be dumb. Download only from github.com/joshuacline. Or be part of a botnet or worse, that's on you.
#     ■■■■■■■■■■■■■■■■■■■■■■■■■■
