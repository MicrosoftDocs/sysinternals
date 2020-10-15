---
TOCTitle: 'Windows Sysinternals: Documentation, downloads and additional resources'
title:  Windows Sysinternals | Microsoft Docs
description: Library, learning resources, downloads, support, and community. Evaluate and find out how to install, deploy, and maintain Windows with Sysinternals utilities.
ms:assetid: '2b0d74e3-5962-455a-b35a-248979737b61'
ms:mtpsurl: 'https://technet.microsoft.com/Bb545021(v=MSDN.10)'
ms.date: 10/15/2020
---

# ![Windows icon](/media/landing/sysinternals/Windows_logo_46x50px.png) Windows Sysinternals
The Sysinternals web site was created in 1996 by [Mark Russinovich](https://blogs.technet.microsoft.com/markrussinovich/) to host his advanced system utilities and technical information. Whether you’re an IT Pro or a developer, you’ll find Sysinternals utilities to help you manage, troubleshoot and diagnose your Windows systems and applications.
-   Read the official guide to the Sysinternals tools, [Troubleshooting with the Windows Sysinternals Tools](~/resources/troubleshooting-book.md)
-   Read the [Sysinternals Blog](https://techcommunity.microsoft.com/t5/Sysinternals-Blog/bg-p/Sysinternals-Blog) for a detailed change feed of tool updates
-   Watch Mark's [Sysinternals Update videos on YouTube](https://www.youtube.com/playlist?list=PLhFhDWFYccZ_GvdJ11NZwaBAhwDCWmni_)
-   Watch Mark’s top-rated [Case-of-the-Unexplained](~/resources/webcasts.md) troubleshooting presentations and other webcasts
-   Read [Mark’s Blog](https://techcommunity.microsoft.com/t5/Windows-Blog-Archive/bg-p/Windows-Blog-Archive/label-name/Mark%20Russinovich) which highlight use of the tools to solve real problems
-   Check out the Sysinternals [Learning Resources](~/resources/index.md) page
-   Post your questions in the [Sysinternals Forum](https://social.technet.microsoft.com/Forums/en-US/home?category=sysinternals&sort=lastpostdesc)

---
## Sysinternals Live ##
Sysinternals Live is a service that enables you to execute Sysinternals tools directly from the Web without hunting for and manually downloading them. Simply enter a tool's Sysinternals Live path into Windows Explorer or a command prompt as live.sysinternals.com/&lt;toolname&gt; or  \\\\live.sysinternals.com\tools\\&lt;toolname&gt;.

You can view the entire Sysinternals Live tools directory in a browser at [https://live.sysinternals.com/](https://live.sysinternals.com).

## What's New [![RSS icon](/media/landing/sysinternals/rss.gif)](https://blogs.technet.microsoft.com/sysinternals/feed/) ##

### What's New (October 15, 2020)

- [VMMap v3.30](~/downloads/vmmap.md)
This update to VMMap, a utility that reports the virtual memory layout of a process, identifies .NET Core 3.0 managed heaps.

- [RAMMap v1.60](~/downloads/rammap.md)
This release to RAMMap, a utility that analyzes and displays physical memory usage, adds customizable map colors and a new command line option, -e, to empty the different types of system working sets.

### What's New (September 17, 2020)

- [Sysmon v12.0](~/downloads/sysmon.md)  
In addition to several bug fixes, this major update to Sysmon adds support for capturing clipboard operations to help incident responders retrieve attacker RDP file and command drops, including originating remote machine IP addresses.

- [Process Monitor v3.60](~/downloads/procmon.md)  
This update to Process Monitor, a utility that logs process file, network and registry activity, adds support for multiple filter item selection, as well as decoding for new file system control operations and error status codes.

- [Procdump v10.0](~/downloads/procdump.md)  
This release of Procdump, a flexible tool for manual and trigger-based process dump generation, adds support for dump cancellation and CoreCLR processes.

- [ARM64 ports](https://download.sysinternals.com/files/SysinternalsSuite-ARM64.zip)  
In addition, several tools have been newly ported to and are now available for ARM64. These include: AdInsight v1.2, AutoLogon v3.1, Autoruns v13.98, ClockRes v2.1, DebugView v4.9, DiskExt v1.2, FindLinks v1.1, Handle v4.22, Hex2Dec v1.1, Junction v1.07, PendMoves v1.02, PipeList v1.02, Procdump v10.0, Process Explorer v16.32, RegDelNull v1.11, RU v1.2, Sigcheck v2.8, Streams v1.6, Sync v2.2, VMMap v3.26, WhoIs v1.21 and ZoomIt v4.52. Download all ARM64 tools in a single download with the [Sysinternals Suite for ARM64](https://download.sysinternals.com/files/SysinternalsSuite-ARM64.zip).

### What's New (June 24, 2020) ###
  - [Sysmon v11.10](~/downloads/sysmon.md)  
This update to Sysmon now captures stream content for alternate data streams into logged events, which is useful for investigating downloads tagged with ‘Mark of the Web’ (MOTW) streams, introduces an ‘is-any’ filter condition, and fixes several bugs. 

  - [Sigcheck v2.80](~/downloads/sigcheck.md)  
Sigcheck, a flexible tool for showing file versions, file signatures, and certificate stores, introduces a -p option for specifying a trust GUID for signature verification, and it now shows certificate signing chains even when a certificate in the chain is untrusted. 

- [Sysinternals June 24 Update Video](https://youtu.be/HCZlJDKUqn0)  
Mark Russinovich covers what’s new in this update, with demos of Sysmon’s alternate data stream content capture and new features in Sigcheck.

### What's New (April 28, 2020) ###
  - [Sysmon v11.0](~/downloads/sysmon.md)  
This major update to Sysmon includes file delete monitoring and archive to help responders capture attacker tools, adds an option to disable reverse DNS lookup, replaces empty fields with ‘-‘ to work around a WEF bug, fixes an issue that caused some ProcessAccess events to drop, and doesn’t hash main data streams that are marked as being stored in the cloud. 

  - [Sysinternals April 27 Update Video](https://www.youtube.com/watch?v=_MUP4tgdM7s)  
    Mark Russinovich covers what’s new in this update, with a demo of Sysmon’s new file delete monitoring and capture capability.

### What's New (December 20, 2019) ###
- [Scheduled livesite maintenance](~/Announce/SiteUpgradeDec2019.md) 

### What's New (December 11, 2019) ###
  - [Sysmon v10.42](~/downloads/sysmon.md)  
  This update to Sysmon addresses a number of memory leaks, introduces the "Excludes Any" and "Excludes All" filtering conditions and resolves a number of bugs.

  - [Zoomit v4.52](~/downloads/zoomit.md)  
  This update to Zoomit resolves a number of dual-monitor related issues.
  
  - [Whois v1.21](~/downloads/whois.md)  
  This refresh of Whois contains various bug fixes.
  

### What's New (September 16, 2019) ###
  - [Sysmon v10.41](~/downloads/sysmon.md)  
  Resolves a config parsing issue with 10.4.

### What's New (September 05, 2019) ###
  - [Sysmon v10.4](~/downloads/sysmon.md)  
    This major update to Sysmon, a security event monitoring service, adds nested rule support to rule groups and “contains any” and “contains all” rule conditions for more flexible filtering, as well as several bug fixes.

  - [Process Explorer v16.30](~/downloads/process-explorer.md)  
    This update to Process Explorer adds a Shared Commit column to the process view, fixes a bug that caused it to terminate when it is configured to run at logon and the system went to battery, and fixes bugs that prevented the system CPU graph from correctly showing multiple sockets.

### What's New (June 20, 2019) ###
  - [SHA1 deprecation](~/Announce/SHA1Deprecation.md)  

### What's New (June 11, 2019) ###
  - [Sysmon v10.0](~/downloads/sysmon.md)  
     This release of Sysmon adds DNS query logging, reports OriginalFileName in process create and load image events, adds ImageName to named pipe events, logs pico process creates and terminates, and fixes several bugs. 
  - [Autoruns v13.95](~/downloads/autoruns.md)  
     This Autoruns updates adds support for redirected user Shell folders. 
     
### What's New (February 18, 2019) ###
  - [Sysmon v9.0](~/downloads/sysmon.md)  
     Sysmon v9.0 introduces rule groups that enable the specification of AND or OR matching logic across a set of rules. It also fixes a memory leak in signature verification. 
     
