--- 
TOCTitle: PsInfo
title: PsInfo
description: Obtain information about a system.
ms:assetid: '5b454ec8-9d69-44bb-b3fe-c7c252929439'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897550(v=MSDN.10)'
ms.date: 06/29/2016
---

PsInfo v1.78
============

**By Mark Russinovich**

Published: June 29, 2016

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**


## Introduction

*PsInfo* is a command-line tool that gathers key information about the
local or remote Windows NT/2000 system, including the type of
installation, kernel build, registered organization and owner, number of
processors and their type, amount of physical memory, the install date
of the system, and if its a trial version, the expiration date.  

## Installation

Just copy *PsInfo* onto your executable path, and type "psinfo".  

## Using PsInfo

By default *PsInfo* shows information for the local system. Specify a
remote computer name to obtain information from the remote system. Since
*PsInfo* relies on remote Registry access to obtain its data, the remote
system must be running the Remote Registry service and the account from
which you run *PsInfo* must have access to the HKLM\\System portion of
the remote Registry.

In order to aid in automated Service Pack updates, *PsInfo* returns as a
value the Service Pack number of system (e.g. 0 for no service pack, 1
for SP 1, etc).

**Usage: psinfo \[\[\\\\computer\[,computer\[,..\] | @file \[-u user  
\[-p psswd\]\]\] \[-h\] \[-s\] \[-d\] \[-c \[-t delimiter\]\]
\[filter\]**


|       Parameter        |                                                                                                               Description                                                                                                               |
|------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    **\\\\computer**    | Perform the command on the remote computer or computers specified. If you omit the computer name the command runs on the local system, and if you specify a wildcard (\\\\\*), the command runs on all computers in the current domain. |
| <strong>@file</strong> |                                                                                   Run the command on each computer listed in the text file specified.                                                                                   |
|         **-u**         |                                                                                       Specifies optional user name for login to remote computer.                                                                                        |
|         **-p**         |                                                              Specifies optional password for user name. If you omit this you will be prompted to enter a hidden password.                                                               |
|         **-h**         |                                                                                                    Show list of installed hotfixes.                                                                                                     |
|         **-s**         |                                                                                                  Show list of installed applications.                                                                                                   |
|         **-d**         |                                                                                                      Show disk volume information.                                                                                                      |
|         **-c**         |                                                                                                          Print in CSV format.                                                                                                           |
|         **-t**         |                                                                 The default delimiter for the -c option is a comma, but can be overriden with the specified character.                                                                  |
|       **filter**       |                                                         Psinfo will only show data for the field matching the filter. e.g. "psinfo service" lists only the service pack field.                                                          |

## Example Output

```Shell
c:&gt; psinfo \\\\development -h -d  

PsInfo v1.6 - local and remote system information viewer  
Copyright (C) 2001-2004 Mark Russinovich  
Sysinternals - www.sysinternals.com  

    System information for \\\\DEVELOPMENT:  
    Uptime: 28 days, 0 hours, 15 minutes, 12 seconds  
    Kernel version: Microsoft Windows XP, Multiprocessor Free  
    Product type Professional  
    Product version: 5.1  
    Service pack: 0  
    Kernel build number: 2600  
    Registered organization: Sysinternals  
    Registered owner: Mark Russinovich  
    Install date: 1/2/2002, 5:29:21 PM  
    Activation status: Activated  
    IE version: 6.0000  
    System root: C:\\WINDOWS  
    Processors: 2  
    Processor speed: 1.0 GHz  
    Processor type: Intel Pentium III  
    Physical memory: 1024 MB  
    Volume Type Format Label Size Free Free  
    A: Removable 0%  
    C: Fixed NTFS WINXP 7.8 GB 1.3 GB 16%  
    D: Fixed NTFS DEV 10.7 GB 809.7 MB 7%  
    E: Fixed NTFS SRC 4.5 GB 1.8 GB 41%  
    F: Fixed NTFS MSDN 2.4 GB 587.5 MB 24%  
    G: Fixed NTFS GAMES 8.0 GB 1.0 GB 13%  
    H: CD-ROM CDFS JEDIOUTCAST 633.6 MB 0%  
    I: CD-ROM 0% Q: Remote 0%  
    T: Fixed NTFS Test 502.0 MB 496.7 MB 99%  
    OS Hot Fix Installed  
    Q147222 1/2/2002  
    Q309521 1/4/2002  
    Q311889 1/4/2002  
    Q313484 1/4/2002  
    Q314147 3/6/2002  
    Q314862 3/13/2002  
    Q315000 1/8/2002  
    Q315403 3/13/2002  
    Q317277 3/20/2002
```


## How it Works

*PsInfo* uses the Remote Registry API to read system information from a
system's Registry, and WMI to determine whether Windows XP installations
have been activated.


[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**
