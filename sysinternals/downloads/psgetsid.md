--- 
TOCTitle: PsGetSid
title: PsGetSid
ms:assetid: 'f7eefa28-72dd-4dc7-a41e-02e7ac7e35ae'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897417(v=MSDN.10)'
ms.date: 06/29/2016
---

PsGetSid v1.45
==============

**By Mark Russinovich**

Published: June 29, 2016

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**


## Introduction

PsGetsid allows you to translate SIDs to their display name and vice
versa. It works on builtin accounts, domain accounts, and local
accounts.

## Installation

Just copy *PsGetSid* onto your executable path, and type "psgetsid".

## Usage

<strong>Usage: psgetsid \[\\\\computer\[,computer\[,...\] | @file\] \[-u
username \[-p password\]\]\] \[account|SID\]</strong>

 
|       Parameter        |                                                                                                                                 Description                                                                                                                                  |
|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         **-u**         |                                                                                                          Specifies optional user name for login to remote computer.                                                                                                          |
|         **-p**         |                                                                                 Specifies optional password for user name. If you omit this you will be prompted to enter a hidden password.                                                                                 |
|      **Account**       |                                                                                            PsGetSid will report the SID for the specified user account rather than the computer.                                                                                             |
|        **SID**         |                                                                                                           PsGetSid will report the account for the specified SID.                                                                                                            |
|      **Computer**      | Direct PsGetSid to perform the command on the remote computer or computers specified. If you omit the computer name PsGetSid runs the command on the local system, and if you specify a wildcard (\\\\\*), PsGetSid runs the command on all computers in the current domain. |
| <strong>@file</strong> |                                                                                                PsGetSid will execute the command on each of the computers listed in the file.                                                                                                |

If you want to see a computer's SID just pass the computer's name as a
command-line argument. If you want to see a user's SID, name the account
(e.g. "administrator") on the command-line and an optional computer
name.

Specify a user name if the account you are running from doesn't have
administrative privileges on the computer you want to query. If you
don't specify a password as an option, *PsGetSid* will prompt you for
one so that you can type it in without having it echoed to the display.

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**
 

**PsTools**

*PsGetSid* is part of a growing kit of Sysinternals command-line tools
that aid in the adminstration of local and remote systems named
*PsTools*.

 

**Runs on:**

-   Client: Windows Vista and higher.
-   Server: Windows Server 2008 and higher.



