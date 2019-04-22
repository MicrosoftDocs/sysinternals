--- 
TOCTitle: TCPView
title: TCPView for Windows
description: Active socket command-line viewer.
ms:assetid: '0797e73a-a0c2-4266-b821-50bc561da3a6'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897437(v=MSDN.10)'
ms.date: 07/25/2011
---

TCPView v3.05
=============

**By Mark Russinovich**

Published: July 25, 2011

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/TCPView.zip) [**Download TCPView**](https://download.sysinternals.com/files/TCPView.zip) **(285 KB)**  
**Run now** from [Sysinternals Live](https://live.sysinternals.com/Tcpview.exe).


## Introduction

TCPView is a Windows program that will show you detailed listings of all
TCP and UDP endpoints on your system, including the local and remote
addresses and state of TCP connections. On Windows Server 2008, Vista,
and XP, TCPView also reports the name of the process that owns the
endpoint. TCPView provides a more informative and conveniently presented
subset of the Netstat program that ships with Windows. The TCPView
download includes Tcpvcon, a command-line version with the same
functionality.

![TCP View screenshot](/media/landing/sysinternals/tcpview.jpg)

 

## Using TCPView

When you start TCPView it will enumerate all active TCP and UDP
endpoints, resolving all IP addresses to their domain name versions. You
can use a toolbar button or menu item to toggle the display of resolved
names. On Windows XP systems, TCPView shows the name of the process that
owns each endpoint.

By default, TCPView updates every second, but you can use the
**Options|Refresh Rate** menu item to change the rate. Endpoints that
change state from one update to the next are highlighted in yellow;
those that are deleted are shown in red, and new endpoints are shown in
green.

You can close established TCP/IP connections (those labeled with a state
of ESTABLISHED) by selecting **File|Close Connections**, or by
right-clicking on a connection and choosing **Close Connections** from
the resulting context menu.

You can save TCPView's output window to a file using the **Save** menu
item.  

 

## Using Tcpvcon

Tcpvcon usage is similar to that of the built-in Windows netstat
utility:

**Usage: tcpvcon \[-a\] \[-c\] \[-n\] \[process name or PID\]**

|Parameter  |Description  |
|---------|---------|
|  **-a**  | Show all endpoints (default is to show established TCP connections).|
|  **-c**  | Print output as CSV.|
|  **-n**  | Don't resolve addresses.|
 

## Microsoft TCPView KB Article

This Microsoft KB article references TCPView:

[816944: "Unexpected Error 0x8ffe2740 Occurred" Error Message When You
Try to Start a Web Site](http://support.microsoft.com/kb/816944)

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/TCPView.zip) [**Download TCPView**](https://download.sysinternals.com/files/TCPView.zip) **(285 KB)**

**Run now** from [Sysinternals Live](https://live.sysinternals.com/Tcpview.exe).

**Runs on:**

-   Client: Windows Vista and higher.
-   Server: Windows Server 2008 and higher.



