--- 
TOCTitle: LogonSessions
title: LogonSessions
description: List the active logon sessions on a system.
ms:assetid: 'b7415eea-e897-49ba-b304-dd6879718a74'
ms:mtpsurl: 'https://technet.microsoft.com/Bb896769(v=MSDN.10)'
ms.date: 07/04/2016
---

LogonSessions v1.4
==================

**By Mark Russinovich**

Published: July 4, 2016

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/logonSessions.zip) [**Download LogonSessions**](https://download.sysinternals.com/files/logonSessions.zip) **(237 KB)**


## Introduction

If you think that when you logon to a system there's only one active
logon session, this utility will surprise you. It lists the currently
active logon sessions and, if you specify the -p option, the processes
running in each session.

**Usage: logonsessions \[-c\[t\]\] \[-p\]**

 
|Parameter  |Description  |
|---------|---------|
|  **-c**   | Print output as CSV. |
|  **-ct**  | Print output as tab-delimited values. |
|  **-p**   | List processes running in logon session. |

## Example output
```Shell
C:\>logonsessions -p 

[13] Logon session 00000000:6a6d6160:
    User name:    NTDEV\markruss
    Auth package: Kerberos
    Logon type:   RemoteInteractive
    Session:      1
    Sid:          S-1-5-21-397955417-626881126-188441444-3615555
    Logon time:   7/2/2015 6:05:31 PM
    Logon server: NTDEV-99
    DNS Domain:   NTDEV.CORP.MICROSOFT.COM
    UPN:          markruss@ntdev.microsoft.com
    15368: ProcExp.exe
    17528: ProcExp64.exe
    13116: cmd.exe
    17100: conhost.exe
     6716: logonsessions.exe
```

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/logonSessions.zip) [**Download LogonSessions**](https://download.sysinternals.com/files/logonSessions.zip) **(237 KB)**

**Runs on:**

-   Client: Windows Vista (32-bit)and higher
-   Server: Windows Server 2008 and higher
-   Nano Server: 2016 and higher
