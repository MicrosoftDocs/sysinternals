--- 
TOCTitle: PsSuspend
title: PsSuspend
description: Suspend and resume processes.
ms:assetid: '148ead94-34cd-47f1-83e2-f3fb3486ef7d'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897540(v=MSDN.10)'
ms.date: 06/29/2016
---

PsSuspend v1.07
===============

**By Mark Russinovich**

Published: June 29, 2016

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**


## Introduction

*PsSuspend* lets you suspend processes on the local or a remote system,
which is desirable in cases where a process is consuming a resource
(e.g. network, CPU or disk) that you want to allow different processes
to use. Rather than kill the process that's consuming the resource,
suspending permits you to let it continue operation at some later point
in time.

 

## Installation

Copy *PsSuspend* onto your executable path and type "pssuspend" with
command-line options defined below.

 

## Using PsSuspend

Running *PsSuspend* with a process ID directs it to suspend or resume
the process of that ID on the local computer. If you specify a process
name *PsSuspend* will suspend or resume all processes that have that
name. Specify the -r switch to resume suspended processes.

**Usage: pssuspend \[- \] \[-r\] \[\\\\computer \[-u username\] \[-p
password\]\] &lt;process name | process id&gt;**

|Parameter  |Description  |
|---------|---------|
|  **-**             | Displays the supported options.|
|  **-r**            | Resumes the specified processes specified if they are suspended.|
|  **\\\\computer**  | Specifies the computer on which the process you want to suspend or resume is executing. The remote computer must be accessible via the NT network neighborhood.|
|  **-u username**   | If you want to suspend a process on a remote system and the account you are executing in does not have administrative privileges on the remote system then you must login as an administrator using this command-line option. If you do not include the password with the -p option then *PsSuspend* will prompt you for the password without echoing your input to the display.|
|  **-p password**   | This option lets you specify the login password on the command line so that you can use *PsSuspend* from batch files. If you specify an account name and omit the -p option *PsSuspend* prompts you interactively for a password.|
|  **process id**    | Specifies the process ID of the process you want to suspend or resume.|
|  **process name**  | Specifies the process name of the process or processes you want to suspend or resume.

*PsSuspend* is part of a growing kit of Sysinternals command-line tools
that aid in the adminstration of local and remote systems named
*PsTools*.

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**

**PsTools**

*PsSuspend* is part of a growing kit of Sysinternals command-line tools
that aid in the adminstration of local and remote systems named
*PsTools*.

**Runs on:**

-   Client: Windows Vista and higher.
-   Server: Windows Server 2008 and higher.



