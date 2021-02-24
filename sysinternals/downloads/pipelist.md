--- 
TOCTitle: Pipelist
title: Pipelist
description: Displays the named pipes on your system, including the number of maximum instances and active instances for each pipe.
ms:assetid: 'c379bcf5-754c-46b0-807d-1266658bd8be'
ms:mtpsurl: 'https://technet.microsoft.com/Dd581625(v=MSDN.10)'
ms.date: 09/17/2020
---

PipeList v1.02
==============

Published: July 4, 2016

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/PipeList.zip) [**Download PipeList**](https://download.sysinternals.com/files/PipeList.zip) **(496 KB)**


## Introduction 

Did you know that the device driver that implements named pipes is
actually a file system driver? In fact, the driver's name is NPFS.SYS,
for "Named Pipe File System". What you might also find surprising is
that its possible to obtain a directory listing of the named pipes
defined on a system. This fact is not documented, nor is it possible to
do this using the Win32 API. Directly using NtQueryDirectoryFile, the
native function that the Win32 FindFile APIs rely on, makes it possible
to list the pipes. The directory listing NPFS returns also indicates the
maximum number of pipe instances set for each pipe and the number of
active instances.

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/PipeList.zip) [**Download PipeList**](https://download.sysinternals.com/files/PipeList.zip) **(496 KB)**

**Runs on:**

-   Client: Windows Vista and higher
-   Server: Windows Server 2008 and higher
-   Nano Server: 2016 and higher
