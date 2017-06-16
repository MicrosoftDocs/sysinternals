--- 
TOCTitle: NTFSInfo
Title: NTFSInfo
ms:assetid: 'a0e927ac-8cca-409b-bb5c-f93567b65ea7'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897424(v=MSDN.10)'
ms.date: 07/04/2016
---

NTFSInfo v1.2
=============

**By Mark Russinovich**

Published: July 4, 2016

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/NTFSInfo.zip) [**Download NTFSInfo**](https://download.sysinternals.com/files/NTFSInfo.zip) **(143 KB)**

## Introduction

*NTFSInfo* is a little applet that shows you information about NTFS
volumes. Its dump includes the size of a drive's allocation units, where
key NTFS files are located, and the sizes of the NTFS metadata files on
the volume. This information is typically of little more than curiosity
value, but *NTFSInfo* does show some interesting things. For example,
you've probably heard about the NTFS equivalent of the FAT file system's
File Allocation Table. Its called the Master File Table (MFT), and it is
made up of constant sized records that describe the location of all the
files and directories on the drive. What's surprising about the MFT is
that it is managed as a file, just like any other. *NTFSInfo* will show
you where on the disk (in terms of clusters) the MFT is located and how
large it is, in addition to specifying how large the volume's clusters
and MFT records are. In order to protect the MFT from fragmentation,
NTFS reserves a portion of the disk around the MFT that it will not
allocate to other files unless disk space runs low. This area is known
as the MFT-Zone and *NTFSInfo* will tell you where on the disk the
MFT-Zone is located and what percentage of the drive is reserved for it.

You might also be surprised to know that like the MFT, all NTFS
meta-data are managed in files. For instance, there is a file called
\$Boot that is mapped to cover the drive's boot sector. The volume's
cluster map is maintained in another file named \$Bitmap. These files
reside right in the NTFS root directory, but you can't see them unless
you know they are there. Try typing "dir /ah \$boot" at the root
directory of an NTFS volume and you'll actually see the \$boot file.
*NTFSInfo* performs the equivalent of the "dir /ah" to show you the
names and sizes of all of NTFS (3.51 and 4.0) meta-data files.

*NTFSInfo* is intended to accompany my January 1998 *Windows NT
Magazine* "NT Internals" column, which describes NTFS internal data
structures.

## Installation and Usage

*NTFSInfo* works on all versions of NTFS, but NTFS for Windows NT 5.0
has different meta-data files that *NTFSInfo* has not been programmed
for yet. In order for *NTFSInfo* to work you must have administrative
privilege.

**Usage: NTFSInfo x**

|Parameter  |Description  |
|---------|---------|
|  **x**  | The drive letter of the NTFS volume that you want to examine.|

## How It Works

*NTFSInfo* uses an undocumented File System Control (FSCTL) call to
obtain information from NTFS about a volume. It prints this information
along with a directory dump of NTFS meta-data files.

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/NTFSInfo.zip) [**Download NTFSInfo**](https://download.sysinternals.com/files/NTFSInfo.zip) **(143 KB)**

**Runs on:**

-   Client: Windows Vista and higher
-   Server: Windows Server 2008 and higher
-   Nano Server: 2016 and higher



