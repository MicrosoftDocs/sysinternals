--- 
TOCTitle: Process Monitor
title: Process Monitor
description: Monitor file system, Registry, process, thread and DLL activity in real-time.
no-loc: [Mark Russinovich, David Solomon, Aaron Margosis]
ms:assetid: '37225635-4ad0-4b08-aa5e-4bba665b1d89'
ms:mtpsurl: 'https://technet.microsoft.com/Bb896645(v=MSDN.10)'
ms.date: 03/09/2023
---

# Process Monitor v3.96

**By Mark Russinovich**

Published: September 29, 2023

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/ProcessMonitor.zip) [**Download Process Monitor**](https://download.sysinternals.com/files/ProcessMonitor.zip) **(3.3 MB)**  

[**Download Procmon for Linux (GitHub)**](https://github.com/Sysinternals/Procmon-for-Linux)

**Run now** from [Sysinternals Live](https://live.sysinternals.com/Procmon.exe).

## Introduction

*Process Monitor* is an advanced monitoring tool for Windows that shows
real-time file system, Registry and process/thread activity. It combines
the features of two legacy Sysinternals utilities, *Filemon* and
*Regmon*, and adds an extensive list of enhancements including rich and
non-destructive filtering, comprehensive event properties such as session
IDs and user names, reliable process information, full thread stacks
with integrated symbol support for each operation, simultaneous logging
to a file, and much more. Its uniquely powerful features will make
Process Monitor a core utility in your system troubleshooting and
malware hunting toolkit.  

## Overview of Process Monitor Capabilities

Process Monitor includes powerful monitoring and filtering capabilities,
including:

- More data captured for operation input and output parameters
- Non-destructive filters allow you to set filters without losing data
- Capture of thread stacks for each operation make it possible in many
    cases to identify the root cause of an operation
- Reliable capture of process details, including image path, command
    line, user and session ID
- Configurable and moveable columns for any event property
- Filters can be set for any data field, including fields not
    configured as columns
- Advanced logging architecture scales to tens of millions of captured
    events and gigabytes of log data
- Process tree tool shows relationship of all processes referenced in
    a trace
- Native log format preserves all data for loading in a different
    Process Monitor instance
- Process tooltip for easy viewing of process image information
- Detail tooltip allows convenient access to formatted data that
    doesn't fit in the column
- Cancellable search
- Boot time logging of all operations

The best way to become familiar with Process Monitor's features is to
read through the help file and then visit each of its menu items and
options on a live system.  

## Screenshots

![Process Monitor screenshot](media/procmon/procmon-main.png)  

![Event Properties screenshot](media/procmon/procmon-proc.png)  

## Related Links

- [**Windows Internals Book**  
  ](~/resources/windows-internals.md)The
  official updates and errata page for the definitive book on Windows
  internals, by Mark Russinovich and David Solomon.
- [**Windows Sysinternals Administrator's Reference**  
  ](~/resources/troubleshooting-book.md)The
  official guide to the Sysinternals utilities by Mark Russinovich and
  Aaron Margosis, including descriptions of all the tools, their
  features, how to use them for troubleshooting, and example
  real-world cases of their use.

## Download

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/ProcessMonitor.zip) [**Download Process Monitor**](https://download.sysinternals.com/files/ProcessMonitor.zip) **(3.3 MB)**

**Run now** from [Sysinternals Live](https://live.sysinternals.com/Procmon.exe).

**Runs on:**

- Client: Windows 10 and higher.
- Server: Windows Server 2012 and higher.
