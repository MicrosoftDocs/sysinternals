--- 
TOCTitle: PsService
title: PsService
description: View and control services.
ms:assetid: 'b634454d-e5d3-410b-9fe1-f1b4b4dc14dd'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897542(v=MSDN.10)'
ms.date: 06/29/2016
---

PsService v2.25
===============

**By Mark Russinovich**

Published: June 29, 2016

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**


## Introduction

*PsService* is a service viewer and controller for Windows. Like the SC
utility that's included in the Windows NT and Windows 2000 Resource
Kits, *PsService* displays the status, configuration, and dependencies
of a service, and allows you to start, stop, pause, resume and restart
them. Unlike the SC utility, *PsService* enables you to logon to a
remote system using a different account, for cases when the account from
which you run it doesn't have required permissions on the remote system.
*PsService* includes a unique service-search capability, which
identifies active instances of a service on your network. You would use
the search feature if you wanted to locate systems running DHCP servers,
for instance.

Finally, *PsService* works on both NT 4, Windows 2000 and Windows Vista,
whereas the Windows 2000 Resource Kit version of SC requires Windows
2000, and *PsService* doesn't require you to manually enter a "resume
index" in order to obtain a complete listing of service information.&gt;

## Installation

Just copy *PsService* onto your executable path, and type "psservice".

 

## Using PsService

The default behavior of *PsService* is to display the configured
services (both running and stopped) on the local system. Entering a
command on the command-line invokes a particular feature, and some
commands accept options. Typing a command followed by "- " displays
information on the syntax for the command.

**Usage: psservice \[\\\\computer \[-u username\] \[-p password\]\]
&lt;command&gt; &lt;options&gt;**

|Parameter  |Description  |
|---------|---------|
|  **query**        |  Displays the status of a service.|
|  **config**       |  Displays the configuration of a service.|
|  **setconfig**    |  Sets the start type (disabled, auto, demand) of a service.|
|  **start**        |  Starts a service.|
|  **stop**         |  Stops a service.|
|  **restart**      |  Stops and then restarts a service.|
|  **pause**        |  Pauses a service|
|  **cont**         |  Resumes a paused service.|
|  **depend**       |  Lists the services dependent on the one specified.|
|  **security**     |  Dumps the service's security descriptor.|
|  **find**         |  Searches the network for the specified service.|
|  **\\\\computer** |  Targets the NT/Win2K system specified. Include the -u switch with a username and password to login to the remote system if your security credentials do not permit you to obtain performance counter information from the remote system. If you specify the -u option, but not a password with the -p option, *PsService* will prompt you to enter the password and will not echo it to the screen.|

## How it Works

*PsService* uses the Service Control Manager APIs that are documented in
the Platform SDK.

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**

**PsTools**

*PsService* is part of a growing kit of Sysinternals command-line tools
that aid in the adminstration of local and remote systems named
*PsTools*.

**Runs on:**

-   Client: Windows Vista and higher.
-   Server: Windows Server 2008 and higher.



