--- 
TOCTitle: LiveKd
title: LiveKd
description: Use Microsoft kernel debuggers to examine a live system.
ms:assetid: '9b0d30e0-be2b-41f0-a6b6-cee2ffb5f283'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897415(v=MSDN.10)'
ms.date: 05/16/2017
---

LiveKd v5.62
============

**By Mark Russinovich and Ken Johnson**

Published: May 16, 2017

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/LiveKD.zip) [**Download LiveKd**](https://download.sysinternals.com/files/LiveKD.zip) **(494 KB)**


## Introduction

*LiveKD*, a utility I wrote for the CD included with *Inside Windows
2000, 3rd Edition*, is now freely available. *LiveKD* allows you to run
the Kd and Windbg Microsoft kernel debuggers, which are part of the
[Debugging Tools for Windows
package](http://www.microsoft.com/whdc/devtools/debugging/default.mspx),
locally on a live system. Execute all the debugger commands that work on
crash dump files to look deep inside the system. See the Debugging Tools
for Windows documentation and our book for information on how to explore
a system with the kernel debuggers.

While the latest versions of Windbg and Kd have a similar capability on
Windows Vista and Server 2008, LiveKD enables more functionality, such
as viewing thread stacks with the !thread command, than Windbg and Kd's
own live kernel debugging facility.

 

## Installation

First download and install the Debugging Tools for Windows package from
Microsoft's web site:

[http://msdn.microsoft.com/library/windows/hardware/ff551063(v=vs.85).aspx](http://msdn.microsoft.com/en-us/library/windows/hardware/ff551063(v=vs.85).aspx)

If you install the tools to their default directory of \\Program
Files\\Microsoft\\Debugging Tools for Windows, you can run *LiveKD* from
any directory; otherwise you should copy LiveKD to the directory in
which the tools are installed.

If you haven't installed symbols for the system on which you run
*LiveKD*, *LiveKD* will ask if you want it to automatically configure
the system to use Microsoft's symbol server (see the Debugging Tools for
Windows documentation for information on symbol files and the Microsoft
symbol server).

*NOTE:* The Microsoft debugger will complain that it can't find symbols
for LIVEKDD.SYS. This is expected, since I have not made symbols for
LIVEKDD.SYS available, and does not affect the behavior of the debugger.

 

## Using LiveKd

**usage:**

**  liveKd \[\[-w\]|\[-k &lt;debugger&gt;\]|\[-o filename\]\] \[-vsym\]
\[-m\[flags\] \[\[-mp process\]|\[pid\]\]\]\[debugger options\]  
  liveKd \[\[-w\]|\[-k &lt;debugger&gt;\]|\[-o filename\]\] -ml
\[debugger options\]  
  liveKd \[\[-w\]|\[-k &lt;debugger&gt;\]|\[-o filename\]\]
\[\[-hl\]|\[-hv &lt;VM name&gt; \[\[-p\]|\[-hvd\]\]\]\] \[debugger
options\]**

|Parameter  |Description  |
|---------|---------|
|  **-hv** | Specifies the name or GUID of the Hyper-V VM to debug. |
|  **-hvd** | Includes hypervisor pages (Windows 8.1 and above only). |
|  **-hvl** | Lists the names and GUIDs of running Hyper-V VMs. |
|  **-k**  | Specifies complete path and filename of debugger image to execute |
|  **-m**  | Creates a mirror dump, which is a consistent view of kernel memory.<br /> Only kernel mode memory will be available, and this option may need significant amounts of available physical memory.  A flags mask that specifies which regions to include may optionally be provided (drawn from the following table, default 0x18F8):<br />0001 - process private, 0002 - mapped file,<br />0004 - shared section,  0008 - page table pages,<br />0010 - paged pool, 0020 - non-paged pool,<br />0040 - system PTEs, 0080 - session pages,<br />0100 - metadata files,  0200 - AWE user pages,<br />0400 - driver pages,    0800 - kernel stacks,<br />1000 - WS metadata,     2000 - large pages<br /> The default captures most kernel memory contents and is  recommended.<br /> This option may be used with -o to save faster, consistent dumps.<br /> Mirror dumps require Windows Vista or Windows Server 2008 or above.<br /> Sysinternals RamMap provides a graphical summary of the distribution of the available memory regions that can be selected for inclusion. |
|  **-ml**  | Generate live dump using native support (Windows 8.1 and above only).|
|  **-mp**  | Specifies a single process whose user mode memory contents should be included in a mirror dump. Only effective with the -m option.|
|  **-o** | Saves a memory.dmp to disk instead of launching the debugger.|
|  **-p** | Pauses the target Hyper-V VM while LiveKd is active (recommended for use with -o). Specifies the name or GUID of the Hyper-V VM to debug. |
|  **-hvl** | Lists the names and GUIDs of running Hyper-V VMs. |
|  **-vsym** | Displays verbose debugging information about symbol load operations. |
|  **-w**  | Runs windbg instead of kd |


  
All other options are passed through to the debugger.

**Note**: Use Ctrl-Break to terminate and restart the debugger if it
hangs.

By default LiveKd runs kd.exe.

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/LiveKD.zip) [**Download LiveKd**](https://download.sysinternals.com/files/LiveKD.zip) **(494 KB)**

**Runs on:**

-   Client: Windows Vista and higher.
-   Server: Windows Server 2008 and higher.



