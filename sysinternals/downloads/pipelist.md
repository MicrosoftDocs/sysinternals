--- 
TOCTitle: Pipelist
Title: Pipelist
layout: LandingPage
ms:assetid: 'c379bcf5-754c-46b0-807d-1266658bd8be'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Dd581625(v=MSDN.10)'
---

PipeList v1.02
==============

Published: July 4, 2016

**[![](/media/landing/sysinternals/download_sm.png)
 Download
PipeList](https://download.sysinternals.com/files/pipelist.zip) (211
KB)**


## Introduction 

Did you know that the device driver that implements named pipes is
actually a file system driver" In fact, the driver's name is NPFS.SYS,
for "Named Pipe File System". What you might also find surprising is
that its possible to obtain a directory listing of the named pipes
defined on a system. This fact is not documented, nor is it possible to
do this using the Win32 API. Directly using NtQueryDirectoryFile, the
native function that the Win32 FindFile APIs rely on, makes it possible
to list the pipes. The directory listing NPFS returns also indicates the
maximum number of pipe instances set for each pipe and the number of
active instances.

 

[![No](/media/landing/sysinternals/download_sm.png "Download")
](https://download.sysinternals.com/files/pipelist.zip)

[**Download PipeList**  
](https://download.sysinternals.com/files/pipelist.zip)**(211 KB)**

 



<div class="RightAdRail">

<div>


## Download

  

[![No](/media/landing/sysinternals/download_sm.png "Download")
](https://download.sysinternals.com/files/pipelist.zip)

[**Download PipeList**  
](https://download.sysinternals.com/files/pipelist.zip)**(211 KB)**

**Runs on:**

-   Client: Windows Vista and higher
-   Server: Windows Server 2008 and higher
-   Nano Server: 2016 and higher



