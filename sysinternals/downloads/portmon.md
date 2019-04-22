--- 
TOCTitle: Portmon
title: Portmon for Windows
description: Monitor serial and parallel port activity with this advanced monitoring tool. 
ms:assetid: 'f989ac38-afd3-4e14-ad47-85af3c4f8ded'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb896644(v=MSDN.10)'
ms.date: 01/12/2012
---

Portmon for Windows v3.03
=========================

**By Mark Russinovich**

Published: January 12, 2012

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PortMon.zip) [**Download Portmon**](https://download.sysinternals.com/files/PortMon.zip) **(226 KB)**  
**Run now** from [Sysinternals Live](https://live.sysinternals.com/portmon.exe).


## Introduction

*Portmon* is a utility that monitors and displays all serial and
parallel port activity on a system. It has advanced filtering and search
capabilities that make it a powerful tool for exploring the way Windows
works, seeing how applications use ports, or tracking down problems in
system or application configurations.  

## Portmon 3.x

Version 3.x of *Portmon* marks the introduction of a number of powerful
features.

- **Remote monitoring:** Capture kernel-mode and/or Win32 debug output
  from any computer accessible via TCP/IP - even across the Internet.
  You can monitor multiple remote computers simultaneously. *Portmon*
  will even install its client software itself if you are running it
  on a Windows NT/2K system and are capturing from another Windows
  NT/2K system in the same Network Neighborhood.
- **Most-recent-filter lists:**<em>Portmon</em> has been extended with
  powerful filtering capabilities and it remembers your most recent
  filter selections, with an interface that makes it easy to reselect
  them.
- **Clipboard copy:** Select multiple lines in the output window and
  copy their contents to the clipboard.
- **Highlighting:** Highlight debug output that matches your
  highlighting filter, and even customize the highlighting colors.
- **Log-to-file:** Write debug output to a file as its being captured.
- **Printing:** Print all or part of captured debug output to a
  printer.
- **One-file payload:**<em>Portmon</em> is now implemented as one file.

The on-line help-file describes all these features, and more, in detail.

![PortMon](/media/landing/sysinternals/PortMon.gif)  

## Installation and Use

Simply execute the *Portmon* program file (portmon.exe) and *Portmon*
will immediately start capturing debug output. To run *Portmon* on
Windows 95 you must get the [WinSock2
update](http://support.microsoft.com/kb/177719) from Microsoft. Note
that if you run *Portmon* on Windows NT/2K portmon.exe must be located
on a non-network drive and you must have administrative privilege.
Menus, hot-keys, or toolbar buttons can be used to clear the window,
save the monitored data to a file, search output, change the window
font, and more. The on-line help describes all of *Portmon's* features.

*Portmon* understands all serial and parallel port I/O control (IOCTLs)
commands and will display them along with interesting information
regarding their associated parameters. For read and write requests
*Portmon* displays the first several dozen bytes of the buffer, using
'.' to represent non-printable characters. The Show Hex menu option lets
you toggle between ASCII and raw hex output of buffer data.  
  

## How it Works: WinNT

The *Portmon* GUI is responsible for identifying serial and parallel
ports. It does so by enumerating the serial ports that are configured
under HKEY\_LOCAL\_MACHINE\\Hardware\\DeviceMap\\SerialComm and the
parallel ports defined under
HKEY\_LOCAL\_MACHINE\\Hardware\\DeviceMap\\Parallel Ports. These keys
contain the mappings between serial and parallel port device names and
the Win32-accessible names.

When you select a port to monitor, *Portmon* sends a request to its
device driver that includes the NT name (e.g. \\device\\serial0) that
you are interested in. The driver uses standard filtering APIs to attach
its own filter device object to the target device object. First, it uses
**ZwCreateFile** to open the target device. Then it translates the
handle it receives back from **ZwCreateFile** to a device object
pointer. After creating its own filter device object that matches the
characteristics of the target, the driver calls
**IoAttachDeviceByPointer** to establish the filter. From that point on
the *Portmon* driver will see all requests aimed at the target device.

*Portmon* has built-in knowledge of all standard serial and parallel
port IOCTLs, which are the primary way that applications and drivers
configure and read status information from ports. The IOCTLs are defined
in the DDK file \\ddk\\src\\comm\\inc\\ntddser.h and
\\ddk\\src\\comm\\inc\\ntddpar.h, and some are documented in the DDK.  
  

## How it Works: Windows 95 and 98

On Windows 95 and 98, the *Portmon* GUI relies on a dynamically loaded
VxD to capture serial and parallel activity. The Windows VCOMM (Virtual
Communications) device driver serves as the interface to parallel and
serial devices, so applications that access ports indirectly use its
services. The *Portmon* VxD uses standard VxD service hooking to
intercept all accesses to VCOMM's functions. Like its NT device driver,
*Portmon*'s VxD interprets requests to display them in a friendly
format. On Windows 95 and 98 *Portmon* monitors all ports so there is no
port selection like on NT.  
  
[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PortMon.zip) [**Download Portmon**](https://download.sysinternals.com/files/PortMon.zip) **(226 KB)** 

**Run now** from [Sysinternals Live](https://live.sysinternals.com/portmon.exe).