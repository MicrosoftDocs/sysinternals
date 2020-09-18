--- 
TOCTitle: Sync
title: Sync
description: Flush cached data to disk.
ms:assetid: 'c37d73b0-a75b-40ff-9b31-0d0dae62849e'
ms:mtpsurl: 'https://technet.microsoft.com/Bb897438(v=MSDN.10)'
ms.date: 09/17/2020
---

Sync v2.2
=========

**By Mark Russinovich**

Published: July 4, 2016

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/Sync.zip) [**Download Sync**](https://download.sysinternals.com/files/Sync.zip)  **(500 KB)**


## Introduction

UNIX provides a standard utility called Sync, which can be used to
direct the operating system to flush all file system data to disk in
order to insure that it is stable and won't be lost in case of a system
failure. Otherwise, any modified data present in the cache would be
lost. Here is an equivalent that I wrote, called Sync, that works on all
versions of Windows. Use it whenever you want to know that modified file
data is safely stored on your hard drives. Unfortunately, Sync requires
administrative privileges to run. This version also lets you flush
removable drives such as ZIP drives.

## Using Sync

**Usage: sync \[-r\] \[-e\] \[drive letter list\]**

|Parameter  |Description  |
|---------|---------|
|  **-r** |  Flush removable drives. |
|  **-e** |  Ejects removable drives. |


Specifying specific drives (e.g. "c e") will result in Sync only
flushing those drives.

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/Sync.zip) [**Download Sync**](https://download.sysinternals.com/files/Sync.zip)  **(500 KB)**

**Runs on:**

-   Client: Windows Vista and higher
-   Server: Windows Server 2008 and higher
-   Nano Server: 2016 and higher
