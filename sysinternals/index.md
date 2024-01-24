---
TOCTitle: 'Sysinternals: Documentation, downloads and additional resources'
title:  Sysinternals
description: Library, learning resources, downloads, support, and community. Evaluate and find out how to install, deploy, and maintain Windows with Sysinternals utilities.
no-loc: [Mark Russinovich]
ms:assetid: '2b0d74e3-5962-455a-b35a-248979737b61'
ms:mtpsurl: 'https://technet.microsoft.com/Bb545021(v=MSDN.10)'
ms.date: 01/23/2024
---

# ![Sysinternals icon](media/index/Sysinternals.png)<br>Sysinternals
The Sysinternals web site was created in 1996 by [Mark Russinovich](https://blogs.technet.microsoft.com/markrussinovich/) to host his advanced system utilities and technical information. Whether you’re an IT Pro or a developer, you’ll find Sysinternals utilities to help you manage, troubleshoot and diagnose your Windows and Linux systems and applications.  
  -   Read the official guide to the Sysinternals tools, [Troubleshooting with the Windows Sysinternals Tools](~/resources/troubleshooting-book.md)
-   Read the [Sysinternals Blog](https://techcommunity.microsoft.com/t5/Sysinternals-Blog/bg-p/Sysinternals-Blog) for a detailed change feed of tool updates
-   Watch Mark's [Sysinternals Update videos on YouTube](https://www.youtube.com/playlist?list=PLhFhDWFYccZ_GvdJ11NZwaBAhwDCWmni_)
-   Watch Mark’s top-rated [Case-of-the-Unexplained](~/resources/webcasts.md) troubleshooting presentations and other webcasts
-   Read [Mark’s Blog](https://techcommunity.microsoft.com/t5/Windows-Blog-Archive/bg-p/Windows-Blog-Archive/label-name/Mark%20Russinovich) which highlight use of the tools to solve real problems
-   Check out the Sysinternals [Learning Resources](~/resources/index.md) page
-   Post your questions in the [Sysinternals Forum](https://aka.ms/sysint-forums)

---
## Sysinternals Live

Sysinternals Live is a service that enables you to run Sysinternals tools directly from the Web without manually downloading them.

Enter a tool's Sysinternals Live path in Windows Explorer as `live.sysinternals.com/<toolname>` or `\\live.sysinternals.com\tools\<toolname>`.
In a command prompt use `\\live.sysinternals.com\tools\<toolname>`.

You can view the entire Sysinternals Live tools directory in a browser or Windows Explorer at [https://live.sysinternals.com/](https://live.sysinternals.com).

## What's New [![RSS icon](media/index/rss.gif)](https://techcommunity.microsoft.com/plugins/custom/microsoft/o365/custom-blog-rss?board=Sysinternals-Blog)

### What's New (January 23, 2024)

- [ProcDump 3.1 for Linux](https://github.com/Sysinternals/ProcDump-for-Linux/releases/tag/3.1.0)  
This update to ProcDump for Linux adds trigger support for multiple signals as well as the the -mc switch to control the size of the core dump file by choosing what is included.

### What's New (December 7, 2023)

- [ProcDump 3.0 for Linux](https://github.com/Sysinternals/ProcDump-for-Linux/releases/tag/3.0)  
This update to ProcDump for Linux adds memory leak tracking and reporting.

### What's New (November 9, 2023)

- [Sysmon v15.1](~/downloads/sysmon.md)  
This update to Sysmon improves file hash and delete performance, adds a summary message on events dropped due to high system load, fixes a crash during uninstall, and fixes a system hang.

- [ZoomIt v7.2](~/downloads/zoomit.md)  
This update to ZoomIt adds translucent highlighter and blur to draw mode, microphone selection for recording, and copies the recorded file to the clipboard.

### What's New (October 18, 2023)

- [VMMap v3.4](~/downloads/vmmap.md)  
This update to VMMap, a virtual and physical memory analysis utility, adds support for .NET 6 and higher, including .NET 8 preview.

### What's New (September 29, 2023)

- [ProcDump 2.2 for Linux](https://github.com/Sysinternals/ProcDump-for-Linux/releases/tag/2.2)  
This update to ProcDump for Linux adds support for Azure Linux and fixes a couple of memory leaks.

- [Sysmon 1.3 for Linux](https://github.com/Sysinternals/SysmonForLinux/releases/tag/1.3.0.0)
This update to Sysmon for Linux fixes a bug with rule case matching.

### What's New (July 26, 2023)

- [ZoomIt v7.1](~/downloads/zoomit.md)  
This update to ZoomIt adds audio capture to screen recording.

- [ProcDump 2.0 for Linux](https://github.com/Sysinternals/ProcDump-for-Linux)  
ProcDump for Linux, a flexible tool for manual and trigger-based process dump generation, receives two new .NET GC triggers (-gcm and -gcgen) and updates the existing memory trigger to allow for multiple thresholds.

### What's New (June 27, 2023)

- [Sysmon v15.0](~/downloads/sysmon.md)  
This update to Sysmon, an advanced host security monitoring tool, sets the service to run as a protected process, hardening it against tampering, adds a new event, `FileExecutableDetected`, for when new executable images are saved to files, and fixes a system hang occurring in certain situations due to an interaction between network and file system events.
