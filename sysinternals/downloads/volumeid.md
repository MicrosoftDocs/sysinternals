--- 
TOCTitle: VolumeID
Title: VolumeID
ms:assetid: '2073ab9a-ad2e-4c86-96b9-4b4d520b8a1d'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897436(v=MSDN.10)'
---

VolumeID v2.1
=============

**By Mark Russinovich**

Published: July 4, 2016

[![](/media/landing/sysinternals/download_sm.png)
 **Download VolumeID (194
KB)**](https://download.sysinternals.com/files/volumeid.zip)


## Introduction

While Windows NT/2000 and Windows 95 and 98's built-in Label utility
lets you change the labels of disk volumes, it does not provide any
means for changing volume ids. This utiltity, VolumeID, allows you to
change the ids of FAT and NTFS disks (floppies or hard drives).

**Usage: volumeid &lt;driveletter:&gt; xxxx-xxxx**

*This is a command-line program that you must run from a command-prompt
window.*

Note that changes on NTFS volumes won't be visible until the next
reboot. In addition, you should shut down any applications you have
running before changing a volume id. NT may become confused and think
that the media (disk) has changed after a FAT volume id has changed and
pop up messages indicating that you should reinsert the original disk
(!). It may then fail the disk requests of applications using those
drives.

 

[![Download](/media/landing/sysinternals/download_sm.png "Download")
](https://download.sysinternals.com/files/volumeid.zip)

[**Download VolumeID**  
](https://download.sysinternals.com/files/volumeid.zip)**(194 KB)**


<div class="RightAdRail">

<div>


## Download

  

[![Download](/media/landing/sysinternals/download_sm.png "Download")
](https://download.sysinternals.com/files/volumeid.zip)

[**Download VolumeID**  
](https://download.sysinternals.com/files/volumeid.zip)**(194 KB)**

 

**Runs on:**

-   Client: Windows Vista and higher
-   Server: Windows Server 2008 and higher
-   Nano Server: 2016 and higher



