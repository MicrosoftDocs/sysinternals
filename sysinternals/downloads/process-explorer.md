---
TOCTitle: Process Explorer
title: Process Explorer
description: Find out what files, registry keys and other objects processes have open, which DLLs they have loaded, and more.
ms:assetid: '32cbeee6-4335-44d5-b94b-160612b99738'
ms:mtpsurl: 'https://technet.microsoft.com/Bb896653(v=MSDN.10)'
ms.date: 05/28/2024
adobe-target: true
---

# Process Explorer v17.06

**By Mark Russinovich**

Published: May 28, 2024

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/ProcessExplorer.zip) [**Download Process Explorer**](https://download.sysinternals.com/files/ProcessExplorer.zip) **(3.3 MB)**  
**Run now** from [Sysinternals Live](https://live.sysinternals.com/procexp.exe).
<br><br>
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE5d5Rd?autoplay=true&loop=true&controls=false]
<sup><i>Created with [ZoomIt](zoomit.md)</i></sup>

## Introduction

Ever wondered which program has a particular file or directory open? Now
you can find out. *Process Explorer* shows you information about which
handles and DLLs processes have opened or loaded.

The *Process Explorer* display consists of two sub-windows. The top
window always shows a list of the currently active processes, including
the names of their owning accounts, whereas the information displayed in
the bottom window depends on the mode that *Process Explorer* is in: if
it is in handle mode you'll see the handles that the process selected in
the top window has opened; if *Process Explorer* is in DLL mode you'll
see the DLLs and memory-mapped files that the process has loaded.
*Process Explorer* also has a powerful search capability that will
quickly show you which processes have particular handles opened or DLLs
loaded.

The unique capabilities of *Process Explorer* make it useful for
tracking down DLL-version problems or handle leaks, and provide insight
into the way Windows and applications work.

## Related Links

- [Windows Internals Book](~/resources/windows-internals.md)
    The official updates and errata page for the definitive book on Windows internals, by Mark Russinovich and David Solomon.
- [Windows Sysinternals Administrator's Reference](~/resources/troubleshooting-book.md) The official guide to the Sysinternals utilities by Mark Russinovich and Aaron Margosis, including descriptions of all the tools, their features, how to use them for troubleshooting, and example real-world cases of their use.

## Download

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/ProcessExplorer.zip) [**Download Process Explorer**](https://download.sysinternals.com/files/ProcessExplorer.zip) **(3.3 MB)**  
**Run now** from [Sysinternals Live](https://live.sysinternals.com/procexp.exe).

**Runs on:**

- Client: Windows 10 and higher.
- Server: Windows Server 2016 and higher.

## Installation

Simply run *Process Explorer* (procexp.exe).

The help file describes *Process Explorer* operation and usage. If you have problems or questions, visit the [Process Explorer section on Microsoft Q&A](/answers/topics/windows-sysinternals-procexp.html).

## Note on use of symbols

When you configure the path to DBGHELP.DLL and the symbol path uses the symbol server, the location of DBGHELP.DLL also has to contain the SYMSRV.DLL supporting the server paths used. See [SymSrv documentation](/windows-hardware/drivers/debugger/symsrv) or more information on how to use symbol servers.

## Learn More

Here are some other handle and DLL viewing tools and information
available at Sysinternals:

- [The case of the Unexplained...](https://www.youtube.com/watch?v=PYHqrwQIoxc) In this video, Mark describes how he has solved seemingly unsolvable system and application problems on Windows.
- [Handle](handle.md) -  a command-line handle viewer
- [ListDLLs](listdlls.md) - a command-line DLL viewer
- [PsList](pslist.md) - local/remote command-line process lister
- [PsKill](pskill.md) - local/remote command-line process killer
- [Defrag Tools: \#2 - Process Explorer](/shows/defrag-tools/2-process-explorer)
    In this episode of Defrag Tools, Andrew Richards and Larry Larsen show how to use Process Explorer to view the details of processes, both at a point in time and historically.
- [Windows Sysinternals Primer: Process Explorer, Process Monitor and More](/shows/defrag-tools/2-process-explorer) Process Explorer gets a lot of attention in the first Sysinternals Primer delivered by Aaron Margosis and Tim Reckmeyer at TechEd 2010.
