--- 
TOCTitle: PageDefrag
title: PageDefrag
description: Defragment your paging files and Registry hives.
ms:assetid: '104b3934-81cc-4c7e-b874-6fd19127ed99'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897426(v=MSDN.10)'
ms.date: 11/01/2006
---

PageDefrag v2.32
================

**By Mark Russinovich**

Published: November 1, 2006

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PageDefrag.zip) [**Download PageDefrag**](https://download.sysinternals.com/files/PageDefrag.zip) **(70 KB)**  
**Run now** from [Sysinternals Live](https://live.sysinternals.com/pagedfrg.exe).


## Introduction

One of the limitations of the Windows NT/2000 defragmentation interface
is that it is not possible to defragment files that are open for
exclusive access. Thus, standard defragmentation programs can neither
show you how fragmented your paging files or Registry hives are, nor
defragment them. Paging and Registry file fragmentation can be one of
the leading causes of performance degradation related to file
fragmentation in a system.

*PageDefrag* uses advanced techniques to provide you what commercial
defragmenters cannot: the ability for you to see how fragmented your
paging files and Registry hives are, and to defragment them. In
addition, it defragments event log files and Windows 2000/XP hibernation
files (where system memory is saved when you hibernate a laptop).

 

## Installing and Using PageDefrag

When you run *PageDefrag* (pagedfrg.exe) you will be presented a listbox
that tells you how many clusters make up your paging files, event log
files, and Registry hives (SAM, SYSTEM, SYSTEM.ALT, SECURITY, SOFTWARE,
.DEFAULT), as well as how many fragments those files are in. If you feel
that these files are fragmented enough to warrant a shot at
defragmenting them, or if you want to defragment them at every boot,
select the appropriate radio button choice and click OK.

![PageDefrag](/media/landing/sysinternals/PageDefrag.gif)  

When you direct *PageDefrag* to defragment, the next time the system
boots it will attempt to do so. Immediately after CHKDSK examines your
hard drives *PageDefrag* uses the standard file defragmentation APIs
(see my [Inside Windows NT Disk
Defragmenting](https://technet.microsoft.com/ea0299d6-a987-4a57-8927-0225e4ec350a)
page for documentation of these APIs) to defragment the files. As it
processes each file *PageDefrag* will print on the boot-time startup
screen the file name and its success at defragmenting it. If it is
successful at reducing the fragmentation it will tell you the number of
clusters the file started with and the number it consists of after the
defragmentation.

In some cases *PageDefrag* may be unable to reduce fragmentation on one
or more of the files, and it will indicate so on the boot-time Blue
Screen. This can happen either because there is not enough space on the
drive for defragmentation, or the free space itself is highly
fragmented. For the best results you should use *PageDefrag* in
conjunction with a commercial defragmentation utility or my free [Contig
defragmenter](contig.md).

 

## Command-Line Options

You can run *PageDefrag* non-interactively by specifying a command-line
option for the setting you want:

**Usage: pagedfrg \[-e | -o | -n\] \[-t &lt;seconds&gt;\]**

|Parameter  |Description  |
|---------|---------|
|  **-e** |  Defrag every boot.|
|  **-o** |  Defrag once.|
|  **-n** |  Never defrag.|
|  **-t** |  Set countdown to specified number of seconds.|


[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PageDefrag.zip) [**Download PageDefrag**](https://download.sysinternals.com/files/PageDefrag.zip) **(70 KB)**

**Run now** from [Sysinternals Live](https://live.sysinternals.com/pagedfrg.exe).
