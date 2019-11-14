--- 
TOCTitle: Ctrl2cap
title: Ctrl2cap
description: This is a kernel-mode driver that demonstrates keyboard input filtering in order to turn caps-locks into control keys. 
ms:assetid: 'e0dcb713-f196-4e45-a2f8-e7bf3f692ac9'
ms:mtpsurl: 'https://technet.microsoft.com/Bb897578(v=MSDN.10)'
ms.date: 11/01/2006
---

Ctrl2Cap v2.0
=============

**By Mark Russinovich**

Published: November 1, 2006

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/Ctrl2Cap.zip) [**Download Ctrl2Cap**](https://download.sysinternals.com/files/Ctrl2Cap.zip)  **(48 KB)**


## Introduction

Ctrl2cap is a kernel-mode device driver that filters the system's
keyboard class driver in order to convert caps-lock characters into
control characters. People like myself that migrated to NT from UNIX are
used to having the control key located where the caps-lock key is on the
standard PC keyboard, so a utility like this is essential for our
editing well-being.

  

## Installation and Use

Install Ctrl2cap running the command "ctrl2cap /install" from the
directory into which you've unzipped the Ctrl2cap files. To uninstall
type "ctrl2cap /uninstall".  

  

## How Ctrl2cap Works

On NT 4 Ctrlcap is actually quite trivial. It simply attaches itself to
the keyboard class driver so that it will catch keyboard read requests.
For each request, it posts an I/O completion callback, at which point it
takes a peek at the scancode that is being returned. If it happens to be
a caps-lock, ctrl2cap changes it into a left-control.

On Win2K Ctrl2cap is a WDM filter driver that layers in the keyboard
class device's stack above the keyboard class device. This is in
contrast to the Win2K DDK's kbfiltr example that layers itself between
the i8042 port device and the keyboard class device. I chose to layer on
top of the keyboard class device for several reasons:

-   It means that the Ctrl2cap IRP\_MJ\_READ interception and
    manipulation code is shared between the NT 4 and Win2K versions.
-   I don't need to supply an INF file and have the user go through the
    Device Manager to install Ctrl2cap - I simply modify the appropriate
    Registry value (the keyboard class devices's
    HKLM\\System\\CurrentControlSet\\Control\\Class UpperFilters value).

The disadvantage of my approach is (and this an advantage or
disadvantage depending on your point of view):

-   Because I don't install with an INF file via the Device Manager, the
    user is not warned that the Ctrl2cap driver file is not digitally
    signed by Microsoft.

In this particular case, I felt that the advantages outweigh the
disadvantages. However, before you model a Win2K keyboard filter on
Ctrl2cap I strongly suggest that you study the kbfiltr example from the
Win2K DDK. Kbfiltr's interception point in the key input sequence makes
it very easy for kbfiltr to inject keystrokes into the input stream.  
  

## More Information

For more information on writing filter drivers (drivers that attach
themselves to other drivers so that they can see their input and/or
output), here are sources to check out:

-   The Windows NT and Windows 2000 DDK sample
    \\src\\storage\\filter\\diskperf
-   The Windows 2000 DDK sample \\src\\input\\kbfiltr
-   *"Examining the Windows NT File System,"* By Mark Russinovich, *Dr.
    Dobb's Journal*, February 1997
-   The accompanying file system filter driver,
    [Filemon](filemon.md)

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/Ctrl2Cap.zip) [**Download Ctrl2Cap**](https://download.sysinternals.com/files/Ctrl2Cap.zip)  **(48 KB)**

**Runs on:**

-   Client: Windows Vista and higher.
-   Server: Windows Server 2008 and higher.
