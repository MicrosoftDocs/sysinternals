---
TOCTitle: Disk Usage 
title: Disk Usage 
description: View disk usage by directory.
ms:assetid: '428a14a6-d688-41bc-a769-5d5052ead7a0' 
ms:mtpsurl: 'https://technet.microsoft.com/Bb896651(v=MSDN.10)' 
ms.date: 11/04/2020
---

# Disk Usage v1.62

**By Mark Russinovich**

Published: November 04, 2020

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/DU.zip)] [**Download Du**](https://download.sysinternals.com/files/DU.zip) **(1.62 MB)**

## Introduction

Du (disk usage) reports the disk space usage for the directory you
specify. By default it recurses directories to show the total size of a
directory and its subdirectories.

## Using Disk Usage (DU)

**Usage: du \[-c\[t\]\] \[-l &lt;levels&gt; | -n | -v\] \[-u\] \[-q\]
&lt;directory&gt;**

|Parameter  |Description  |
|---------|---------|
|  **-nobanner ** | Do not display the startup banner and copyright message.|
|  **-c** |  Print output as CSV. Use -ct for tab delimiting.|
|  **-l** |  Specify subdirectory depth of information (default is all levels).|
|  **-n** |  Do not recurse.|
|  **-v** |  Show size (in KB) of intermediate directories.|
|  **-u** |  Count each instance of a hardlinked file.|
|  **-q** |  Quiet - Do not display alert  ( message box ) or initial execution|

CSV output is formatted as:

Path, CurrentFileCount, CurrentFileSize, FileCount, DirectoryCount,
DirectorySize

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/DU.zip) [**Download Du**](https://download.sysinternals.com/files/DU.zip) **(1.62 MB)**
