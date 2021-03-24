--- 
TOCTitle: NotMyFault
title: NotMyFault
description: Notmyfault is a tool that you can use to crash, hang, and cause kernel memory leaks on your Windows system.
ms:assetid: 'fc881ee6-6e6a-480f-95d2-83458e2d09b7'
ms:mtpsurl: 'https://technet.microsoft.com/Mt742033(v=MSDN.10)'
ms.date: 06/14/2019
---

# NotMyFault v4.20

**By Mark Russinovich**

Published: June 14, 2019

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/NotMyFault.zip) [**Download NotMyFault**](https://download.sysinternals.com/files/NotMyFault.zip) **(1 MB)**

## Introduction

Notmyfault is a tool that you can use to crash, hang, and cause kernel
memory leaks on your Windows system. It’s useful for learning how to
identify and diagnose device driver and hardware problems, and you can
also use it to generate blue screen dump files on misbehaving systems.
The download file includes 32-bit and 64-bit versions, as well as a
command-line version that works on Nano Server. Chapter 7 in Windows
Internals uses Notmyfault to demonstrate pool leak troubleshooting and
Chapter 14 uses it for crash analysis examples.


## Screenshots

![NotMyFault screenshot](media/notmyfault/notmyfault.png "NotMyFault")

## Usage

You can use the GUI versions or the command-line version. Notmyfault
requires administrative privileges.

Usage:

**notmyfaultc.exe crash crash\_type\_num**

```Shell
    crash type:
      0x01: High IRQL fault (Kernel-mode)
      0x02: Buffer overflow
      0x03: Code overwrite
      0x04: Stack trash
      0x05: High IRQL fault (User-mode)
      0x06: Stack overflow
      0x07: Hardcoded breakpoint
      0x08: Double Free
```

Or  **notmyfaultc.exe hang hang\_type\_num**

```Shell
    hang type:
      0x01: Hang with IRP
      0x02: Hang with DPC
```

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/NotMyFault.zip) [**Download NotMyFault**](https://download.sysinternals.com/files/NotMyFault.zip) **(1 MB)**
