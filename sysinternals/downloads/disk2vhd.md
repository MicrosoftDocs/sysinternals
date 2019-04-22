--- 
TOCTitle: Disk2vhd
title: Disk2vhd
description: Disk2vhd simplifies the migration of physical systems into virtual machines.
ms:assetid: 'd2c9597c-1927-4ddc-9ec1-9e0f33166f90'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Ee656415(v=MSDN.10)'
ms.date: 01/21/2014
---

Disk2vhd v2.01
==============

**By Mark Russinovich**

Published: January 21, 2014

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/Disk2vhd.zip) [**Download Disk2vhd**](https://download.sysinternals.com/files/Disk2vhd.zip) **(879 KB)**  
**Run now** from [Sysinternals Live](https://live.sysinternals.com/disk2vhd.exe).


## Introduction

Disk2vhd is a utility that creates VHD (Virtual Hard Disk - Microsoft's
Virtual Machine disk format) versions of physical disks for use in
Microsoft Virtual PC or Microsoft Hyper-V virtual machines (VMs). The
difference between Disk2vhd and other physical-to-virtual tools is that
you can run Disk2vhd on a system that’s online. Disk2vhd uses Windows'
Volume Snapshot capability, introduced in Windows XP, to create
consistent point-in-time snapshots of the volumes you want to include in
a conversion. You can even have Disk2vhd create the VHDs on local
volumes, even ones being converted (though performance is better when
the VHD is on a disk different than ones being converted).

The Disk2vhd user interface lists the volumes present on the system:

![Disk2vhd](/media/landing/sysinternals/20131218_Disk2vhd_v2.0.png "Disk2vhd")

It will create one VHD for each disk on which selected volumes reside.
It preserves the partitioning information of the disk, but only copies
the data contents for volumes on the disk that are selected. This
enables you to capture just system volumes and exclude data volumes, for
example.

> Virtual PC supports a maximum virtual disk size of 127GB. If
> you create a VHD from a larger disk it will not be accessible from a
> Virtual PC VM.

To use VHDs produced by Disk2vhd, create a VM with the desired
characteristics and add the VHDs to the VM's configuration as IDE disks.
On first boot, a VM booting a captured copy of Windows will detect the
VM's hardware and automatically install drivers, if present in the
image. If the required drivers are not present, install them via the
Virtual PC or Hyper-V integration components. You can also attach to
VHDs using the Windows 7 or Windows Server 2008 R2 Disk Management or
Diskpart utilities.

> Do not attach to VHDs on the same system on which you created
> them if you plan on booting from them. If you do so, Windows will
> assign the VHD a new disk signature to avoid a collision with the
> signature of the VHD’s source disk. Windows references disks in the
> boot configuration database (BCD) by disk signature, so when that
> happens Windows booted in a VM will fail to locate the boot disk.
> 
> Disk2vhd does not support the conversion of volumes with Bitlocker enabled. If you wish to create a VHD for such a volume, turn off Bitlocker and wait for the volume to be fully decrypted first. 


Disk2vhd runs on Windows Vista, Windows Server 2008, and higher,
including x64 systems.

Here's a screenshot of a copy of a Windows Server 2008 R2 Hyper-V system
running in a virtual machine on top of the system it was made from:

[![Windows Server 2008 R2 Hyper-V](/media/landing/sysinternals/Disk2vhd_02_sm.png)](/media/landing/sysinternals/disk2vhd_02.jpg)  
*(click image to zoom)*

## Command Line Usage

Disk2vhd includes command-line options that enable you to script the
creation of VHDs. Specify the volumes you want included in a snapshot by
drive letter (e.g. c:) or use "\*" to include all volumes.

Usage: **disk2vhd &lt;\[drive: \[drive:\]...\]|\[\*\]&gt;
&lt;vhdfile&gt;**  
Example: **disk2vhd \* c:\\vhd\\snapshot.vhd**

> Physical-to-virtual hard drive migration of a Windows
> installation is a valid function for customers with Software Assurance
> and full retail copies of Windows XP, Windows Vista, and Windows 7.
> Software Assurance provides users valuable benefits—please contact
> Microsoft Corporation for further information. Windows XP, Windows
> Vista and Windows 7 installed by Original Equipment Manufacturers
> (OEM) using OEM versions of these products may not be transferred to a
> virtual hard drive in accordance with Microsoft licensing terms.

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/Disk2vhd.zip) [**Download Disk2vhd**](https://download.sysinternals.com/files/Disk2vhd.zip) **(879 KB)**

**Run now** from [Sysinternals Live](https://live.sysinternals.com/disk2vhd.exe).

