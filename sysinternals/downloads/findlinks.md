--- 
TOCTitle: FindLinks
title: FindLinks
description: FindLinks reports the file index and any hard links (alternate file paths on the same volume) that exist for the specified file.
ms:assetid: 'f3fb08e4-d0af-4191-b09d-08bf44694281'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Hh290814(v=MSDN.10)'
ms.date: 07/04/2016
---

FindLinks v1.1
==============

**By Mark Russinovich**

Published: July 4, 2016

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/FindLinks.zip) [**Download FindLinks**](https://download.sysinternals.com/files/FindLinks.zip) **(153 KB)**  
**Run now** from [Sysinternals Live](https://live.sysinternals.com/FindLinks.exe).


## Introduction

FindLinks reports the file index and any hard links (alternate file
paths on the same volume) that exist for the specified file.  A file's
data remains allocated so long as at it has at least one file name
referencing it.

## Using FindLinks

**Usage: findlinks &lt;filename&gt;**

## Example

The following command reports the file paths that reference the same
file data as C:\\Windows\\Notepad.exe:

**C:\\&gt;findlinks c:\\windows\\notepad.exe  

```Shell
FindLinks - Locate file hard links  
Copyright (C) 2011 Mark Russinovich  
Sysinternals -www.sysinternals.com  

c:\\windows\\notepad.exe  
        Index:  0x000057D9  
        Links:  3**

Linking files:
C:\Windows\winsxs\amd64_microsoft-windows-notepadwin_31bf3856ad364e35_6.1.7600.16385_none_9ebebe8614be1470\notepad.exe
C:\Windows\winsxs\amd64_microsoft-windows-notepad_31bf3856ad364e35_6.1.7600.16385_none_cb0f7f2289b0c21a\notepad.exe
C:\Windows\System32\notepad.exe
```

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/FindLinks.zip) [**Download FindLinks**](https://download.sysinternals.com/files/FindLinks.zip) **(153 KB)**

**Run now** from [Sysinternals Live](https://live.sysinternals.com/FindLinks.exe).

**Runs on:**

  - Client: Windows Vista and higher
  - Server: Windows Server 2008 and higher
  - Nano Server: 2016 and higher