--- 
TOCTitle: PsPasswd
title: PsPasswd
description: Changes account passwords.
ms:assetid: '0e454df6-b63b-404d-854c-e2f355630912'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897543(v=MSDN.10)'
ms.date: 06/29/2016
---

PsPasswd v1.24
==============

**By Mark Russinovich**

Published: June 29, 2016

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**


## Introduction

Systems administrators that manage local administrative accounts on
multiple computers regularly need to change the account password as part
of standard security practices. *PsPasswd* is a tool that lets you
change an account password on the local or remote systems, enabling
administrators to create batch files that run *PsPasswd* against the
computers they manage in order to perform a mass change of the
administrator password.

PsPasswd uses Windows password reset APIs, so does not send passwords
over the network in the clear.



## Installation

Just copy *PsPasswd* onto your executable path, and type "pspasswd" with
the command-line syntax shown below..



## Using PsPasswd

You can use *PsPasswd* to change the password of a local or domain
account on the local or a remote computer.

**usage: pspasswd \[\[\\\\computer\[,computer\[,..\] | @file \[-u user
\[-p psswd\]\]\] Username \[NewPassword\]**


|       Parameter        |                                                                                                               Description                                                                                                               |
|------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      **computer**      | Perform the command on the remote computer or computers specified. If you omit the computer name the command runs on the local system, and if you specify a wildcard (\\\\\*), the command runs on all computers in the current domain. |
| <strong>@file</strong> |                                                                                   Run the command on each computer listed in the text file specified.                                                                                   |
|         **-u**         |                                                                                       Specifies optional user name for login to remote computer.                                                                                        |
|         **-p**         |                                                              Specifies optional password for user name. If you omit this you will be prompted to enter a hidden password.                                                               |
|      **Username**      |                                                                                             Specifies name of account for password change.                                                                                              |
|    **NewPassword**     |                                                                                          New password. If ommitted a NULL password is applied.                                                                                          |

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**

**PsTools**  
*PsPasswd* is part of a growing kit of Sysinternals command-line tools
that aid in the adminstration of local and remote systems named
*PsTools*.

**Runs on:**

-   Client: Windows Vista and higher.
-   Server: Windows Server 2008 and higher.



