--- 
TOCTitle: Sync
Title: Sync
layout: LandingPage
ms:assetid: 'c37d73b0-a75b-40ff-9b31-0d0dae62849e'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897438(v=MSDN.10)'
---

Sync v2.2
=========

**By Mark Russinovich**

Published: July 4, 2016

[![](/media/landing/sysinternals/download_sm.png)
 **Download Sync (145
KB)**](https://download.sysinternals.com/files/sync.zip)


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

 
-------- 
--------------------------
  **-r**   Flush removable drives.
  **-e**   Ejects removable drives.
 
-------- 
--------------------------

Specifying specific drives (e.g. "c e") will result in Sync only
flushing those drives.

 

[![Download](/media/landing/sysinternals/download_sm.png "Download")
](https://download.sysinternals.com/files/sync.zip)

[**Download Sync**  
](https://download.sysinternals.com/files/sync.zip)**(145 KB)**


<div class="RightAdRail">

<div>


## Download

  

[![Download](/media/landing/sysinternals/download_sm.png "Download")
](https://download.sysinternals.com/files/sync.zip)

[**Download Sync**  
](https://download.sysinternals.com/files/sync.zip)**(145 KB)**

 

**Runs on:**

-   Client: Windows Vista and higher
-   Server: Windows Server 2008 and higher
-   Nano Server: 2016 and higher



