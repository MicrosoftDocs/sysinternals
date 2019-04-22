--- 
TOCTitle: PsShutdown
title: PsShutdown
description: Shuts down and optionally reboots a computer.
ms:assetid: 'ba3665e1-fbac-45a1-b1c3-575d83832987'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897541(v=MSDN.10)'
ms.date: 12/04/2006
---

PsShutdown v2.52
================

**By Mark Russinovich**

Published: December 4, 2006

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**

## Introduction

*PsShutdown* is a command-line utility similar to the shutdown utility
from the Windows 2000 Resource Kit, but with the ability to do much
more. In addition to supporting the same options for shutting down or
rebooting the local or a remote computer, *PsShutdown* can logoff the
console user or lock the console (locking requires Windows 2000 or
higher). *PsShutdown* requires no manual installation of client
software.



## Installation

Just copy *PsShutdown* onto your executable path, and type psshutdown
with command-line options defined below.



## Using PsShutdown

See the February 2005 issue of Windows IT Pro Magazine for [Mark's
article](http://www.windowsitpro.com/article/articleid/44973/44973.html)
that covers advanced usage of *PsKill*.

You can use *PsShutdown* to initiate a shutdown of the local or a remote
computer, logoff a user, lock a system, or to abort an imminent
shutdown.

**Usage: psshutdown \[\[\\\\computer\[,computer\[,..\] | @file \[-u user
\[-p psswd\]\]\] -s|-r|-h|-d|-k|-a|-l|-o \[-f\] \[-c\] \[-t nn|h:m\]
\[-n s\] \[-v nn\] \[-e \[u|p\]:xx:yy\] \[-m "message"\]**


|       Parameter        |                                                                                                               Description                                                                                                               |
|------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         **-**          |                                                                                                     Displays the supported options.                                                                                                     |
|      **computer**      | Perform the command on the remote computer or computers specified. If you omit the computer name the command runs on the local system, and if you specify a wildcard (\\\\\*), the command runs on all computers in the current domain. |
| <strong>@file</strong> |                                                                                   Run the command on each computer listed in the text file specified.                                                                                   |
|         **-u**         |                                                                                       Specifies optional user name for login to remote computer.                                                                                        |
|         **-p**         |                                                              Specifies optional password for user name. If you omit this you will be prompted to enter a hidden password.                                                               |
|         **-a**         |                                                                                   Aborts a shutdown (only possible while a countdown is in progress).                                                                                   |
|         **-c**         |                                                                                       Allows the shutdown to be aborted by the interactive user.                                                                                        |
|         **-d**         |                                                                                                          Suspend the computer.                                                                                                          |
|         **-e**         |                                                                                                      Shutdown reason code.  <br />                                                                                                      |
|                        |                                                                          Specify 'u' for user reason codes and 'p' for planned shutdown reason codes.   <br />                                                                          |
|                        |                                                                                      xx is the major reason code (must be less than 256).   <br />                                                                                      |
|                        |                                                                                         yy is the minor reason code (must be less than 65536).                                                                                          |
|         **-f**         |                                                       Forces all running applications to exit during the shutdown instead of giving them a chance to gracefully save their data.                                                        |
|         **-h**         |                                                                                                         Hibernate the computer.                                                                                                         |
|         **-k**         |                                                                                      Poweroff the computer (reboot if poweroff is not supported).                                                                                       |
|         **-l**         |                                                                                                           Lock the computer.                                                                                                            |
|         **-m**         |                                                                This option lets you specify a message to display to logged-on users when a shutdown countdown commences.                                                                |
|         **-n**         |                                                                                      Specifies timeout in seconds connecting to remote computers.                                                                                       |
|         **-o**         |                                                                                                        Logoff the console user.                                                                                                         |
|         **-r**         |                                                                                                         Reboot after shutdown.                                                                                                          |
|         **-s**         |                                                                                                       Shutdown without power off.                                                                                                       |
|         **-t**         |                                                       Specifies the countdown in seconds until the shutdown (default: 20 seconds) or the time of shutdown (in 24 hour notation).                                                        |
|         **-v**         |                     Display message for the specified number of seconds before the shutdown. If you omit this parameter the shutdown notification dialog displays and specifying a value of 0 results in no dialog.                     |

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**

**PsTools**  
*PsShutdown* is part of a growing kit of Sysinternals command-line tools
that aid in the adminstration of local and remote systems named
*PsTools*.

**Runs on:**

-   Client: Windows Vista and higher.
-   Server: Windows Server 2008 and higher.



