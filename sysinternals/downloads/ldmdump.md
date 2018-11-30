--- 
TOCTitle: LDMDump
title: LDMDump
description: Dump the contents of the Logical Disk Manager's on-disk database, which describes the partitioning of Windows 2000 Dynamic disks.
ms:assetid: '2767f738-9f1d-4eb0-8c75-4287b7ca0e13'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897413(v=MSDN.10)'
ms.date: 11/01/2016
---

LDMDump v1.02
=============

**By Mark Russinovich**

Published: November 1, 2006

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/LdmDump.zip) [**Download LDMDump**](https://download.sysinternals.com/files/LdmDump.zip) **(43 KB)**


## Introduction

Windows 2000 introduces a new type of disk partitioning scheme that is
managed by a component called the Logical Disk Manager (LDM). Basic
disks implement standard DOS-style partition tables, whereas Dynamic
disks use LDM partitioning. LDM partitioning offers several advantages
over DOS partitioing including replication across disks, on-disk storage
of advanced volume configuration (spanned volume, mirrored volumes,
striped volumes and RAID-5 volumes). My March/April two-part series on
Windows NT/2000 storage management in *Windows 2000 Magazine* describes
the details of each partitioning scheme.

Other than the Disk Management MMC-snapin and a tool called dmdiag in
the Windows 2000 Resource Kit, there are no tools for investigating the
internals of the LDM on-disk database that describes a system's
partitioning layout. *LDMDump* is a utility that lets you examine
exactly what is stored in a disk's copy of the system LDM database.
*LDMDump* shows you the contents of the LDM database private header,
table-of-contents, and object database (where partition, component and
volume definitions are stored), and then summarizes its finding with
partition table and volume listings.  

## Installing and Using LDMDump

To use *LDMDump* simply pass it the identifier of a disk.

**Usage: ldmdump \[- \] \[-d\#\]**

|Parameter  |Description  |
|---------|---------|
|  **-**  |    Displays the supported options and the units of measurement used for output values.|
|  **-d\#** |  Specifies the number of the disk for *LDMDump* to examine. For example, "ldmdump /d0" has *LDMDump* show the LDM database information stored on disk 0.|

## How it Works

There are no published APIs available for obtiaining detailed
information about a disk's LDM partitioning, and the LDM database format
is completely undocumented. *LDMDump* was developed based on study of
LDM database contents on a variety of different systems and under
changing conditions.

 

## More Information

For more information on the LDM on-disk structure, see:

-   *Inside Storage Management, Part 2*, by Mark Russinovich, Windows
    2000 Magazine, April 2000.


[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/LdmDump.zip) [**Download LDMDump**](https://download.sysinternals.com/files/LdmDump.zip) **(43 KB)**

**Runs on:**

-   Client: Windows Vista and higher.
-   Server: Windows Server 2008 and higher.



