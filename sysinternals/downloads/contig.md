--- 
TOCTitle: Contig
title: Contig
description: Use Contig to optimize individual files, or to create new files that are contiguous.
ms:assetid: '33371252-c217-4fc7-8d74-f9f0e20e0597'
ms:mtpsurl: 'https://technet.microsoft.com/Bb897428(v=MSDN.10)'
ms.date: 03/09/2023
---

# Contig v1.83

**By Mark Russinovich**

Published: March 9, 2023

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/Contig.zip) [ **Download Contig**](https://download.sysinternals.com/files/Contig.zip) **(366 KB)**

## Introduction

There are a number of NT disk defraggers on the market, including
Winternals *Defrag Manager*. These tools are useful for performing a
general defragmentation of disks, but while most files are defragmented
on drives processed by these utilities, some files may not be. In
addition, it is difficult to ensure that particular files that are
frequently used are defragmented - they may remain fragmented for
reasons that are specific to the defragmentation algorithms used by the
defragging product that has been applied. Finally, even if all files
have been defragmented, subsequent changes to critical files could cause
them to become fragmented. Only by running an entire defrag operation
can one hope that they might be defragmented again.

*Contig* is a single-file defragmenter that attempts to make files
contiguous on disk. Its perfect for quickly optimizing files that are
continuously becoming fragmented, or that you want to ensure are in as
few fragments as possible.  

## Using Contig

*Contig* is a utility that defragments a specified file or files. Use it
to optimize execution of your frequently used files.

**Usage:**

```cmd
Contig.exe [-a] [-s] [-q] [-v] [existing file]
Contig.exe [-f] [-q] [-v] [drive:]
Contig.exe [-v] [-l] -n [new file] [new file length]
```

|Parameter  |Description  |
|---------|---------|
|  **-a** |  Analyze fragmentation|
|  **-f** |  Analyze free space fragmentation|
|  **-l** |  Set valid data length for quick file creation (requires administrator rights)|
|  **-q** |  Quiet mode|
|  **-s** |  Recurse subdirectories|
|  **-v** |  Verbose|

*Contig* can also analyze and defragment the following NTFS metadata
files:

- \$Mft
- \$LogFile
- \$Volume
- \$AttrDef
- \$Bitmap
- \$Boot
- \$BadClus
- \$Secure
- \$UpCase
- \$Extend

## How it Works

*Contig* uses the native Windows NT defragmentation support that was
introduced with NT 4.0 (see my documentation of the defrag APIs for more
information). It first scans the disk collecting the locations and sizes
of free areas. Then it determines where the file in question is located.
Next, *Contig* decides whether the file can be optimized, based on free
areas and the number of fragments the file currently consists of. If the
file can be optimized, it is moved into the free spaces of the disk.  

## More Information

Helen Custer's *Inside Windows NT* provides a good overview of the
Object Manager name space, and Mark's October 1997 Windows NT Magazine
column,*"Inside the Object Manager",* is (of course) an excellent
overview.

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/Contig.zip) [ **Download Contig**](https://download.sysinternals.com/files/Contig.zip) **(366 KB)**

**Runs on:**

- Client: Windows 8.1 and higher.
- Server: Windows Server 2012 and higher.
- Nano Server: 2016 and higher.
