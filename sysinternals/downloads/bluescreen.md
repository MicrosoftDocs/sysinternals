--- 
TOCTitle: BlueScreen
title: BlueScreen - Windows Sysinternals | Microsoft Docs
description: This screen saver not only accurately simulates Blue Screens, but simulated reboots as well (complete with CHKDSK), and works on Windows NT 4, Windows 2000, Windows XP, Server 2003 and Windows 95 and 98.
ms:assetid: '2682b9a8-04c3-44ab-9a5c-71c8650b5a2e'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897558(v=MSDN.10)'
ms.date: 11/01/2006
---

BlueScreen Screen Saver v3.2
============================

**By Mark Russinovich**

Published: November 1, 2006

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/BlueScreen.zip) [**Download BlueScreen**](https://download.sysinternals.com/files/BlueScreen.zip) **(64 KB)**

## Introduction

One of the most feared colors in the NT world is blue. The infamous Blue
Screen of Death (BSOD) will pop up on an NT system whenever something
has gone terribly wrong. Bluescreen is a screen saver that not only
authentically mimics a BSOD, but will simulate startup screens seen
during a system boot.

-   On NT 4.0 installations it simulates chkdsk of disk drives with
    errors!
-   On Windows 2000, Windows 95, and Windows 98 it presents the Windows
    2000 startup splash screen, complete with rotating progress band and
    progress control updates!
-   On Windows XP and Windows Server 2003 it presents the XP/Server 2003
    startup splash screen with progress bar!  

Bluescreen cycles between different Blue Screens and simulated boots
every 15 seconds or so. Virtually all the information shown on
Bluescreen's BSOD and system start screen is obtained from your system
configuration - its accuracy will fool even advanced NT developers. For
example, the NT build number, processor revision, loaded drivers and
addresses, disk drive characteristics, and memory size are all taken
from the system Bluescreen is running on.

Use Bluescreen to amaze your friends and scare your enemies!  

## Installation and Use

Note: before you can run Bluescreen on Windows 95 or 98, you must copy
\\winnt\\system32\\ntoskrnl.exe from a Windows 2000 system to your
\\Windows directory. Simply copy Sysinternals BLUESCRN.SCR to your
\\system32 directory if on Windows NT/2K, or \\Windows\\System directory
if on Windows 95 or 98. Right click on the desktop to bring up the
Display settings dialog and then select the "Screen Saver" tab. Use the
pull down list to find "Sysinternals Bluescreen" and apply it as your
new screen saver. Select the "Settings" button to enable fake disk
activity, which adds an extra touch of realism!  

## More Information

You can find out how real Blue Screens are generated, and what the
information on the Blue Screen means in my December 1997 [*Windows ITPro
Magazine*](http://www.windowsitpro.com/) NT Internals column, *"Inside
the Blue Screen."*

**Note: Some virus scanners flag the Bluescreen screen saver as a virus.
If this is the case with your virus scanner, you may not be able to use
this screen saver.**

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/BlueScreen.zip) [**Download BlueScreen**](https://download.sysinternals.com/files/BlueScreen.zip) **(64 KB)**

**Runs on:**

-   Client: Windows Vista and higher.
-   Server: Windows Server 2008 and higher.



