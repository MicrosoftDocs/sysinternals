---
TOCTitle: 'Windows Sysinternals: Documentation, downloads and additional resources'
title:  Windows Sysinternals | Microsoft Docs
description: Library, learning resources, downloads, support, and community. Evaluate and find out how to install, deploy, and maintain Windows with Sysinternals utilities.
ms:assetid: '2b0d74e3-5962-455a-b35a-248979737b61'
ms:mtpsurl: 'https://technet.microsoft.com/Bb545021(v=MSDN.10)'
ms.date: 12/11/2019
---

# ![Windows icon](/media/landing/sysinternals/Windows_logo_46x50px.png) Windows Sysinternals
The Sysinternals web site was created in 1996 by [Mark Russinovich](https://blogs.technet.microsoft.com/markrussinovich/) to host his advanced system utilities and technical information. Whether you’re an IT Pro or a developer, you’ll find Sysinternals utilities to help you manage, troubleshoot and diagnose your Windows systems and applications.
-   Read the official guide to the Sysinternals tools, [Troubleshooting with the Windows Sysinternals Tools](~/learn/troubleshooting-book.md)
-   Read the [Sysinternals Blog](https://techcommunity.microsoft.com/t5/Sysinternals-Blog/bg-p/Sysinternals-Blog) for a detailed change feed of tool updates
-   Watch Mark’s top-rated [Case-of-the-Unexplained](~/learn/webcasts.md) troubleshooting presentations and other webcasts
-   Read [Mark’s Blog](https://techcommunity.microsoft.com/t5/Windows-Blog-Archive/bg-p/Windows-Blog-Archive/label-name/Mark%20Russinovich) which highlight use of the tools to solve real problems
-   Check out the Sysinternals [Learning Resources](~/learn/index.md) page
-   Post your questions in the [Sysinternals Forum](https://social.technet.microsoft.com/Forums/home?category=sysinternals&amp;filter=alltypes&amp;sort=lastpostdesc)

---
## Sysinternals Live ##
Sysinternals Live is a service that enables you to execute Sysinternals tools directly from the Web without hunting for and manually downloading them. Simply enter a tool's Sysinternals Live path into Windows Explorer or a command prompt as live.sysinternals.com/&lt;toolname&gt; or  \\\\live.sysinternals.com\tools\\&lt;toolname&gt;.

You can view the entire Sysinternals Live tools directory in a browser at [https://live.sysinternals.com/](https://live.sysinternals.com).

## What's New [![RSS](/media/landing/sysinternals/rss.gif)](https://blogs.technet.microsoft.com/sysinternals/feed/) ##

### What's New (April 22, 2020) ###
  - [Sysmon v11.0](~/downloads/sysmon.md)  
  This update to Sysmon addresses a number of bugs and adds file delete monitoring

  - [LiveKD v5.63](~/downloads/livekd.md)  
  This update to LiveKD resolves issues with enumerating and dumping Hyper-V partitions
  
  - [Coreinfo v3.5](~/downloads/coreinfo.md)  
  Adds support for restricted guest virtualization

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
     
### What's New (December 18, 2018) ###
  - [Sysmon v8.04](~/downloads/sysmon.md)  
     This release reverted the filtering change made in 8.02 as this broke a number of configuration files. We are planning to revisit and enhance the filtering in the new year. It also fixed a BSOD in legacy named pipe filter used on Windows 7 and earlier, and a kernel memory leak that occurred when the configuration is reloaded.
     
### What's New (October 17, 2018) ###
  - [Sigcheck v2.7](~/downloads/sigcheck.md)  
     Windows WinVerifyTrust function reports signed MSI files that have malware appended to them as signed, so Sigcheck now indicates when appended conent is present. 

### What's New (September 17, 2018) ###
  - [TLS 1.1 deprecation](~/Announce/TLSDeprecation.md)  

### What's New (July 5, 2018) ###
  - [Sysmon v8.0](~/downloads/sysmon.md)  
    Sysmon now includes the ability to tag rules so that event log entries include the rule tag that generated them, as well as several bug fixes.  
    
  - [Autoruns v13.90](~/downloads/autoruns.md)  
    Autoruns now includes Runonce\*\Depend entries, adds GPO logon and logoff locations, and fixes a bug in WMI path parsing.    
    
### What's New (February 13, 2018) ###
  - [Autoruns v13.82](~/downloads/autoruns.md)  
    This Autoruns release shows Onenote addins and fixes several bugs. 

  - [Process Monitor v3.50](~/downloads/procmon.md)  
    Process Monitor now includes a /runtime switch to control headless capture duration, correctly shows picoprocesses, displays details for file system APIs introduced in Windows 10, and includes numerous minor improvements and bug fixes. 

### What's New (January 2, 2018) ###
  - [Sysmon v7.0](~/downloads/sysmon.md)  
    Sysmon now logs file version information, and the option to dump the configuration schema adds the ability to dump an older schema or dump all historical schemas. 
    
### What's New (November 19, 2017) ###
  - [Sysmon v6.20](~/downloads/sysmon.md)  
    This Sysmon release adds the ability to change the Sysmon service and driver names to foil malware that use them to detect its presence. 
    
  - [Whois v1.20](~/downloads/whois.md)  
    Whois, a command-line utility that reports domain registration information for the specified domain, works with new whois registry server redirects.  

### What's New (September 11, 2017) ###
  - [Sysmon v6.10](~/downloads/sysmon.md)  
    This update to Sysmon, a background monitor that records activity to the event log for use in security incident detection and forensics, adds monitoring of WMI filters and consumers, an autostart mechanism commonly used by malware, and fixes a bug in image load filtering. 

  - [Process Monitor v3.40](~/downloads/procmon.md)  
    Process Monitor, a file system registry, process and network real-time monitor, now includes a /runtime switch for terminating monitoring after a specified amount of time, when in hexadecimal mode shows process tree process IDs in hexadecimal, and fixes a bug in automated boot log conversion. 
    
  - [Autoruns v13.80](~/downloads/autoruns.md)  
    This release of Autoruns, a utility for viewing and managing autostart execution points (ASEPs), adds additional autostart entry points, has asynchronous file saving, fixes a bug parsing 32-bit paths on 64-bit Windows, shows the display name for drivers and services, and fixes a bug in offline Virus Total scanning. 

### What's New (May 16, 2017) ###
  - [ProcDump v9.0](~/downloads/procdump.md)  
    This major update to ProcDump, a utility that enables process dump capture based on a variety of triggers, introduces the ability to take capture multiple dumps sizes. This is particularly useful when capturing crash dumps of applications susceptible to termination due to unresponsiveness (e.g. IIS Ping killing w3wp.exe). This release also adds support for an associated Kernel Dump of the process that includes the kernel stacks of the process.</li>

### What's New (February 17, 2017) ###
  - [Sysmon v6](~/downloads/sysmon.md)  
    This release of Sysmon, a background monitor that records activity to the event log for use in security incident detection and forensics, introduces an option that displays event schema, adds an event for Sysmon configuration changes, interprets and displays registry paths in their common format, and adds named pipe create and connection events (thanks to Giulia Biagini for the contribution). Check out the related presentation from Mark’s RSA Conference, “[How to Go From Responding to Hunting with Sysinternals Sysmon](https://www.rsaconference.com/events/us17/agenda/sessions/7516-How-to-Go-from-Responding-to-Hunting-with-Sysinternals-Sysmon).”
  - [Autoruns v13.7](~/downloads/autoruns.md)  
    Autoruns, an autostart entry point management utility, now reports print providers, registrations in the WMI\Default namespace, fixes a KnownDLLs enumeration bug, and has improved toolbar usability on high-DPI displays.
  - [AccessChk v6.1](~/downloads/accesschk.md)  
    This update to AccessChk, a command-line utility that shows effective and actual permissions for file, registry, service, process object manager, and event logs, now reports Windows 10 process trust access control entries and token security attributes.
