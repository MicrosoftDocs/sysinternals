--- 
TOCTitle: PsList
title: PsList
description: Show information about processes and threads.
ms:assetid: '3922c630-462d-4c3a-8b02-532865f37df4'
ms:mtpsurl: 'https://technet.microsoft.com/Bb896682(v=MSDN.10)'
ms.date: 03/30/2023
---

# PsList v1.41

**By Mark Russinovich**

Published: March 30, 2023

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(5 MB)**

## Introduction

You can simply run **pslist** to get the current list of processes and statistical information about each one, or filter to show only processes that start with a specific name for example **pslist exp** will only show processes that start with "exp", which would include Explorer for instance.

|Parameter  |Description  |
|---------|---------|
|  **-d**           |  Show thread detail.|
|  **-m**           |  Show memory detail.|
|  **-x**           |  Show processes, memory information and threads.|
|  **-t**           |  Show process tree.|
|  **-s \[n\]**     |  Run in task-manager mode, for optional seconds specified. Press Escape to abort.|
|  **-r n**         |  Task-manager mode refresh rate in seconds (default is 1).|
|  **\\\\computer** |  Instead of showing process information for the local system, *PsList* will show information for the system specified. Include the -u switch with a username and password to login to the remote system if your security credentials do not permit you to obtain performance counter information from the remote system.|
|  **-u**           |  Specifies optional user name for login to remote computer.|
|  **-p**           |  This option lets you specify the login password on the command line so that you can use *PsList* from batch files. If you specify an account name and omit the -p option *PsList* prompts you interactively for a password.|
|  **name**         |  Show information about processes that begin with the name specified.|
|  **-e**           |  Exact match the process name.|
|  **pid**          |  Instead of listing all the running processes in the system, this parameter narrows *PsList's* scan to the process that has the specified PID. Thus:  <br />**pslist 53**  <br /> would dump statistics for the process with the PID 53. |

## How it Works

Like Windows's built-in PerfMon monitoring tool, *PsList* uses the
Windows performance counters to obtain the information it
displays. You can find documentation for Windows performance
counters, in the [Win32 Docs](/windows/win32/).

## Statistics Abbreviations Legend

All memory values are displayed in KB.

- **Pri**: Priority
- **Thd**: Number of Threads
- **Hnd**: Number of Handles
- **VM**: Virtual Memory
- **WS**: Working Set
- **Priv**: Private Virtual Memory
- **Priv Pk**: Private Virtual Memory Peak
- **Faults**: Page Faults
- **NonP**: Non-Paged Pool
- **Page**: Paged Pool
- **Cswtch**: Context Switches  

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(5 MB)**

**PsTools**

*PsList* is part of a growing kit of Sysinternals command-line tools
that aid in the administration of local and remote systems named
*PsTools*.

**Runs on:**

- Client: Windows 8.1 and higher.
- Server: Windows Server 2012 and higher.
