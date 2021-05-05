--- 
TOCTitle: VolumeID
title: VolumeID
description: Set Volume ID of FAT or NTFS drives.
ms:assetid: '2073ab9a-ad2e-4c86-96b9-4b4d520b8a1d'
ms:mtpsurl: 'https://technet.microsoft.com/Bb897436(v=MSDN.10)'
ms.date: 07/04/2016
---

# VolumeID v2.1

**By Mark Russinovich**

Published: July 4, 2016

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/VolumeId.zip) [**Download VolumeID**](https://download.sysinternals.com/files/VolumeId.zip) **(194 KB)**

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

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/VolumeId.zip) [**Download VolumeID**](https://download.sysinternals.com/files/VolumeId.zip) **(194 KB)**

**Runs on:**

- Client: Windows Vista and higher
- Server: Windows Server 2008 and higher
- Nano Server: 2016 and higher
