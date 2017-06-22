--- 
TOCTitle: PsList
Title: PsList
ms:assetid: '3922c630-462d-4c3a-8b02-532865f37df4'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb896682(v=MSDN.10)'
ms.date: 06/29/2016
---

PsList v1.4
===========

**By Mark Russinovich**

Published: June 29, 2016

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**


## Introduction

 
|Parameter  |Description  |
|---------|---------|
|  **pslist exp**   |  would show statistics for all the processes that start with "exp", which would include Explorer.|
|  **-d**           |  Show thread detail.|
|  **-m**           |  Show memory detail.|
|  **-x**           |  Show processes, memory information and threads.|
|  **-t**           |  Show process tree.|
|  **-s \[n\]**     |  Run in task-manager mode, for optional seconds specified. Press Escape to abort.|
|  **-r n**         |  Task-manager mode refresh rate in seconds (default is 1).|
|  **\\\\computer** |  Instead of showing process information for the local system, *PsList* will show information for the NT/Win2K system specified. Include the -u switch with a username and password to login to the remote system if your security credentials do not permit you to obtain performance counter information from the remote system.|
|  **-u**           |  username If you want to kill a process on a remote system and the account you are executing in does not have administrative privileges on the remote system then you must login as an administrator using this command-line option. If you do not include the password with the -p option then *PsList* will prompt you for the password without echoing your input to the display.|
|  **-p**           |  password This option lets you specify the login password on the command line so that you can use *PsList* from batch files. If you specify an account name and omit the -p option *PsList* prompts you interactively for a password.|
|  **name**         |  Show information about processes that begin with the name specified.|
|  **-e**           |  Exact match the process name.|
|  **pid**          |  Instead of listing all the running processes in the system, this parameter narrows *PsList's* scan to the process that has the specified PID. Thus:  <br />
                     **pslist 53**  <br />
                     would dump statistics for the process with the PID 53. |

## How it Works

Like Windows NT/2K's built-in PerfMon monitoring tool, *PsList* uses the
Windows NT/2K performance counters to obtain the information it
displays. You can find documentation for Windows NT/2K performance
counters, including the source code to Windows NT's built-in performance
monitor, PerfMon, in MSDN.

## Memory Abbreviation Key

All memory values are displayed in KB.

-   **Pri**: Priority
-   **Thd**: Number of Threads
-   **Hnd**: Number of Handles
-   **VM**: Virtual Memory
-   **WS**: Working Set
-   **Priv**: Private Virtual Memory
-   **Priv Pk**: Private Virtual Memory Peak
-   **Faults**: Page Faults
-   **NonP**: Non-Paged Pool
-   **Page**: Paged Pool
-   **Cswtch**: Context Switches  

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**

**PsTools**

*PsList* is part of a growing kit of Sysinternals command-line tools
that aid in the adminstration of local and remote systems named
*PsTools*.

**Runs on:**

-   Client: Windows Vista and higher.
-   Server: Windows Server 2008 and higher.



