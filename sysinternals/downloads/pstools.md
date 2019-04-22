--- 
TOCTitle: PsTools
title: PsTools
description: Command-line utilities for listing the processes running on local or remote computers, running processes, rebooting computers, and more.
ms:assetid: '559ea946-3d7d-47bb-821c-b47fd078dfb7'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb896649(v=MSDN.10)'
ms.date: 07/04/2016
---

PsTools
=======

**By Mark Russinovich**

Published: July 4, 2016

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools Suite**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**


## Introduction

The Windows NT and Windows 2000 Resource Kits come with a number of
command-line tools that help you administer your Windows NT/2K systems.
Over time, I've grown a collection of similar tools, including some not
included in the Resource Kits. What sets these tools apart is that they
all allow you to manage remote systems as well as the local one. The
first tool in the suite was PsList, a tool that lets you view detailed
information about processes, and the suite is continually growing. The
"Ps" prefix in PsList relates to the fact that the standard UNIX process
listing command-line tool is named "ps", so I've adopted this prefix for
all the tools in order to tie them together into a suite of tools named
*PsTools*.

> Some anti-virus scanners report that one or more of the tools are infected with a "remote admin" virus. None of the PsTools contain viruses, but they have been used by viruses, which is why they trigger virus notifications.*

The tools included in the *PsTools* suite, which are downloadable as a
package, are:

-   [*PsExec*](psexec.md) -
    execute processes remotely
-   [*PsFile*](psfile.md) -
    shows files opened remotely
-   [*PsGetSid*](psgetsid.md) -
    display the SID of a computer or a user
-   [*PsInfo*](psinfo.md) -
    list information about a system
-   [*PsPing*](psping.md) -
    measure network performance
-   [*PsKill*](pskill.md) -
    kill processes by name or process ID
-   [*PsList*](pslist.md) -
    list detailed information about processes
-   [*PsLoggedOn*](psloggedon.md) -
    see who's logged on locally and via resource sharing (full source is
    included)
-   [*PsLogList*](psloglist.md) -
    dump event log records
-   [*PsPasswd*](pspasswd.md) -
    changes account passwords
-   [*PsService*](psservice.md) -
    view and control services
-   [*PsShutdown*](psshutdown.md) -
    shuts down and optionally reboots a computer
-   [*PsSuspend*](pssuspend.md) -
    suspends processes
-   *PsUptime* - shows you how long a system has been running since its
    last reboot (PsUptime's functionality has been incorporated into
    [*PsInfo*](psinfo.md)

The *PsTools* download package includes an HTML help file with complete
usage information for all the tools.

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools Suite**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**

**Runs on:**  
  - Client: Windows Vista and higher
  - Server: Windows Server 2008 and higher
  - Nano Server: 2016 and higher

### Installation
None of the tools requires any special installation. You don't even need to install any client software on the remote computers at which you target them. Run them by typing their name and any command-line options you want. To show complete usage information, specify the "-? " command-line option.
If you have questions or problems, please visit the [Sysinternals PsTools Forum](http://forum.sysinternals.com/forum_topics.asp?FID=8).

### Related Links
[Introduction to the PsTools](https://technet.microsoft.com/en-us/library/2007.03.desktopfiles.aspx): Wes Miller gives a high-level overview of the Sysinternals PsTools in the March column of his TechNet Magazine column.
