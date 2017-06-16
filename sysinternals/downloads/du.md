---
TOCTitle: Disk Usage 
Title: Disk Usage 
ms:assetid: '428a14a6-d688-41bc-a769-5d5052ead7a0' 
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb896651(v=MSDN.10)' 
ms.date: 07/04/2016
---

Disk Usage v1.6
===============

**By Mark Russinovich**

Published: July 4, 2016

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/DU.zip)] [**Download Du**](https://download.sysinternals.com/files/DU.zip) **(174 KB)**

## Introduction

Du (disk usage) reports the disk space usage for the directory you
specify. By default it recurses directories to show the total size of a
directory and its subdirectories.

## Using Disk Usage (DU)

**Usage: du \[-c\[t\]\] \[-l &lt;levels&gt; | -n | -v\] \[-u\] \[-q\]
&lt;directory&gt;**

|Parameter  |Description  |
|---------|---------|
|  **-c** |  Print output as CSV. Use -ct for tab delimiting.|
|  **-l** |  Specify subdirectory depth of information (default is all levels).|
|  **-n** |  Do not recurse.|
|  **-v** |  Show size (in KB) of intermediate directories.|
|  **-u** |  Count each instance of a hardlinked file.|
|  **-q** |  Quiet (no banner).|

CSV output is formatted as:

Path, CurrentFileCount, CurrentFileSize, FileCount, DirectoryCount,
DirectorySize

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/DU.zip)] [**Download Du**](https://download.sysinternals.com/files/DU.zip) **(174 KB)**
