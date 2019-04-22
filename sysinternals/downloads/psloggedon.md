--- 
TOCTitle: PsLoggedOn
title: PsLoggedOn
description: Show users logged on to a system.
ms:assetid: '05a9b41e-e4c2-457c-b46e-d6156fe069a1'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897545(v=MSDN.10)'
ms.date: 06/29/2016
---

PsLoggedOn v1.35
================

**By Mark Russinovich**

Published: June 29, 2016

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**


## Introduction

You can determine who is using resources on your local computer with the
"net" command ("net session"), however, there is no built-in way to
determine who is using the resources of a remote computer. In addition,
NT comes with no tools to see who is logged onto a computer, either
locally or remotely. *PsLoggedOn* is an applet that displays both the
locally logged on users and users logged on via resources for either the
local computer, or a remote one. If you specify a user name instead of a
computer, *PsLoggedOn* searches the computers in the network
neighborhood and tells you if the user is currently logged on.

*PsLoggedOn*'s definition of a locally logged on user is one that has
their profile loaded into the Registry, so *PsLoggedOn* determines who
is logged on by scanning the keys under the HKEY\_USERS key. For each
key that has a name that is a user SID (security Identifier),
*PsLoggedOn* looks up the corresponding user name and displays it. To
determine who is logged onto a computer via resource shares,
*PsLoggedOn* uses the *NetSessionEnum* API. Note that *PsLoggedOn* will
show you as logged on via resource share to remote computers that you
query because a logon is required for *PsLoggedOn* to access the
Registry of a remote system.  

 

## Installation

Just copy *PsLoggedOn* onto your executable path, and type
"psloggedon".  

 

## Using PsLoggedOn

**Usage: psloggedon \[- \] \[-l\] \[-x\] \[\\\\computername |
username\]**
 
|Parameter  |Description  |
|---------|---------|
|  **-**                 | Displays the supported options and the units of measurement used for output values.|
|  **-l**                | Shows only local logons instead of both local and network resource logons.|
|  **-x**                | Don't show logon times.|
|  **\\\\computername**  | Specifies the name of the computer for which to list logon information.|
|  **username**          | If you specify a user name *PsLoggedOn* searches the network for computers to which that user is logged on. This is useful if you want to ensure that a particular user is not logged on when you are about to change their user profile configuration.|

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**

**PsTools**  
*PsLoggedOn* is part of a growing kit of Sysinternals command-line tools
that aid in the adminstration of local and remote systems named
*PsTools*.

**Runs on:**

-   Client: Windows Vista and higher.
-   Server: Windows Server 2008 and higher.



