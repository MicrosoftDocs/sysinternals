--- 
TOCTitle: PsKill
title: PsKill
description: Terminate local or remote processes.
ms:assetid: '12798522-e5f1-494c-8824-38db3162eea7'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb896683(v=MSDN.10)'
ms.date: 06/29/2016
---

PsKill v1.16
============

**By Mark Russinovich**

Published: June 29, 2016

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**


## Introduction

Windows NT/2000 does not come with a command-line 'kill' utility. You
can get one in the Windows NT or Win2K Resource Kit, but the kit's
utility can only terminate processes on the local computer. *PsKill* is
a kill utility that not only does what the Resource Kit's version does,
but can also kill processes on remote systems. You don't even have to
install a client on the target computer to use *PsKill* to terminate a
remote process.  

## Installation

Just copy *PsKill* onto your executable path, and type pskill with
command-line options defined below.  

## Using PsKill

See the September 2004 issue of Windows IT Pro Magazine for [Mark's
article](http://windowsitpro.com/search/results/mark%27s%20article?filters=ss_type:article)
that covers advanced usage of *PsKill*.

Running *PsKill* with a process ID directs it to kill the process of
that ID on the local computer. If you specify a process name *PsKill*
will kill all processes that have that name.

**Usage: pskill \[- \] \[-t\] \[\\\\computer \[-u username\] \[-p
password\]\] &lt;process name | process id&gt;**

|Parameter  |Description  |
|---------|---------|
|  **-**             | Displays the supported options.|
|  **-t**            | Kill the process and its descendants.|
|  **\\\\computer**  | Specifies the computer on which the process you want to terminate is executing. The remote computer must be accessible via the NT network neighborhood.|
|  **-u username**   | If you want to kill a process on a remote system and the account you are executing in does not have administrative privileges on the remote system then you must login as an administrator using this command-line option. If you do not include the password with the -p option then *PsKill* will prompt you for the password without echoing your input to the display.|
|  **-p password**   | This option lets you specify the login password on the command line so that you can use PsList from batch files. If you specify an account name and omit the -p option PsList prompts you interactively for a password.|
|  **process id**    | Specifies the process ID of the process you want to kill.|
|  **process name**  | Specifies the process name of the process or processes you want to kill.|

## PsKill Microsoft KB Article

This Microsoft KB article references *PsKill*:

[810596: PSVR2002: "There Is No Information to Display in This View"
Error Message When You Try to Access a Project
View](http://support.microsoft.com/kb/810596)

  
[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**

**PsTools**

*PsKill* is part of a growing kit of Sysinternals command-line tools
that aid in the adminstration of local and remote systems named
*PsTools*.

 

**Runs on:**

-   Client: Windows Vista and higher.
-   Server: Windows Server 2008 and higher.



