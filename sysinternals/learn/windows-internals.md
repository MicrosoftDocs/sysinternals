--- 
TOCTitle: Windows Internals Book
title: Windows Internals Book
ms:assetid: '11dfe484-4785-45a8-9b2f-863cdbd83be6'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb963901(v=MSDN.10)'
ms.date: 02/07/2017
---

Windows Internals Book
======================

***Windows Internals, 6th edition*** covers the internals of the core
kernel components of the Windows 7 and Windows Server 2008 R2 operating
systems. This classic book will help you:
-   Understand how the core system and management mechanisms work—from
    the object manager to services to the registry
-   Explore internal system data structures using tools like the kernel
    debugger
-   Grasp the scheduler’s priority and CPU placement algorithms
-   Go inside the Windows security model to see how it authorizes access
    to data
-   Understand how Windows manages physical and virtual memory
-   Tour the Windows networking stack from top to bottom—including APIs,
    protocol drivers, and network adapter drivers
-   Troubleshoot file-system access problems and system boot problems
-   Learn how to analyze crashes

Sixth in the series, this edition was again written by Mark Russinovich,
a Technical Fellow in Microsoft’s Azure Group, [David
Solomon](http://www.solsem.com/), an operating systems expert and
Windows internals teacher, and Alex Ionescu, Chief Architect at
CrowdStrike and specializing in OS internals and security. Besides
updates for changes in Windows, there are many new experiments and
examples that highlight the use of both existing and new Sysinternals
tools.

## Table of Contents

**Part 1:**  
**Chapter 1** Concepts and Tools   
**Chapter 2** System Architecture   
**Chapter 3** System Mechanisms   
**Chapter 4** Management Mechanisms   
**Chapter 5** Processes, Threads, and Jobs   
**Chapter 6** Security   
**Chapter 7** Networking  
**Part 2:**  
**Chapter 8**  I/O System  
**Chapter 9**  Storage Management  
**Chapter 10** Memory Management  
**Chapter 11** Cache Manager  
**Chapter 12** File Systems  
**Chapter 13** Startup and Shutdown  
**Chapter 14** Crash Dump Analysis

## Sample Chapter

You can download a PDF that includes the full table of contents, Chapter 5 (Processes, Threads, and Jobs), and Chapter 6 (Security)
[here](https://download.microsoft.com/download/1/4/0/14045a9e-c978-47d1-954b-92b9fd877995/97807356648739_samplechapters.pdf).

## Ordering the Book

The book is available for purchase on the Microsoft Press site ([6th Edition Part 1](https://www.microsoftpressstore.com/store/windows-internals-part-1-9780735648739);
[6th Edition Part 2](https://www.microsoftpressstore.com/store/windows-internals-part-2-9780735665873),
or the [5th Edition](https://www.microsoftpressstore.com/store/windows-internals-9780735630277)).

## History of the Book 

This is the sixth edition of a book that was originally called *Inside
Windows NT* (Microsoft Press, 1992), written by Helen Custer (prior to
the initial release of Microsoft Windows NT 3.1). *Inside Windows
NT* was the first book ever published about Windows NT and provided key
insights into the architecture and design of the system. *Inside Windows
NT, Second Edition* (Microsoft Press, 1998) was written by David
Solomon. It updated the original book to cover Windows NT 4.0 and had a
greatly increased level of technical depth.

*Inside Windows 2000, Third Edition* (Microsoft Press, 2000) was
authored by David Solomon and Mark Russinovich. It added many new
topics, such as startup and shutdown, service internals, registry
internals, file-system drivers, and networking. It also covered kernel
changes in Windows 2000, such as the Windows Driver Model (WDM), Plug
and Play, power management, Windows Management Instrumentation (WMI),
encryption, the job object, and Terminal Services. *Windows Internals,
Fourth Edition* was the Windows XP and Windows Server 2003 update and
added more content focused on helping IT professionals make use of their
knowledge of Windows internals, such as using key tools from ([Windows
Sysinternals](~/index.md))
and analyzing crash dumps. *Windows Internals, Fifth Edition* was the
update for Windows Vista and Windows Server 2008. New content included
the image loader, user-mode debugging facility, and Hyper-V.

## Book Tools

Tools referenced in the book and hosted but not referenced on
Sysinternals include:

-   [Cpustres](https://download.sysinternals.com/files/CPUSTRES.zip):
    This tool is used in the Processes, Threads and Jobs chapter to
    demonstrate relative thread priorities and priority boosting. It has
    a UI thread and you can direct it to create up to four worker
    threads at a specified priority and activity level.
-   [NotMyFault](https://download.sysinternals.com/files/NotMyFault.zip):
    Use this executable and driver to crash your system in several
    different ways. Chapter 7 uses Notmyfault to demonstrate pool leak
    troubleshooting and Chapter 14 uses it for crash analysis examples.
    The download includes x86 (in the exe\\release directory) and x64
    versions (in the exe\\relamd directory) as well as full source.
-   [Testlimit](https://download.sysinternals.com/files/TestLimit.zip):
    Chapter 3 uses Testlimit to demonstrate the operating system's
    per-process limit on the number of concurrently opened handles, but
    the tool's command-line options also let you test limits of process
    and thread creation.
-   [Accvio](https://download.sysinternals.com/files/AccVio.zip): This
    executable generates a user mode access violation by trying to
    reference virtual address zero, which by default, is marked no
    access. Chapter 3 uses it to demonstrate the behavior of Windows
    when an application triggers an unhandled exception.
-   [Iopriority](https://download.sysinternals.com/files/iopriority.zip):
    This tool is used in Chapter 7 to demonstrate the preference the
    system gives to high priority I/O over low priority I/O. It does so
    by creating two threads and having one issue high and the other low
    priority I/O's. It was written by Jeffrey Richter
    of [Wintellect](http://wintellect.com/).