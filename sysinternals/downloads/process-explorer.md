--- 
TOCTitle: Process Explorer
title: Process Explorer
description: Find out what files, registry keys and other objects processes have open, which DLLs they have loaded, and more.
ms:assetid: '32cbeee6-4335-44d5-b94b-160612b99738'
ms:mtpsurl: 'https://technet.microsoft.com/Bb896653(v=MSDN.10)'
ms.date: 09/17/2020
---

Process Explorer v16.32
=======================

**By Mark Russinovich**

Published: April 28, 2020

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/ProcessExplorer.zip) [**Download Process Explorer**](https://download.sysinternals.com/files/ProcessExplorer.zip) **(2.5 MB)**  
**Run now** from [Sysinternals Live](https://live.sysinternals.com/procexp.exe).

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

![Process Explorer screenshot](/media/landing/sysinternals/processexplorer.jpg)  

![System Information screenshot](/media/landing/sysinternals/processexplorer2.jpg)  

## Related Links

-   [Windows Internals
    Book](~/resources/windows-internals.md)  
    The official updates and errata page for the definitive book on
    Windows internals, by Mark Russinovich and David Solomon.
-   [Windows Sysinternals Administrator's
    Reference](~/resources/troubleshooting-book.md)  
    The official guide to the Sysinternals utilities by Mark Russinovich
    and Aaron Margosis, including descriptions of all the tools, their
    features, how to use them for troubleshooting, and example
    real-world cases of their use.

## Download 

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/ProcessExplorer.zip) [**Download Process Explorer**](https://download.sysinternals.com/files/ProcessExplorer.zip) **(2.5 MB)**  
**Run now** from [Sysinternals Live](https://live.sysinternals.com/procexp.exe).

**Runs on:**
-   Client: Windows Vista and higher (Including IA64).
-   Server: Windows Server 2008 and higher (Including IA64).

## Installation

Simply run *Process Explorer* (procexp.exe).

The help file describes *Process Explorer* operation and usage. If you
have problems or questions please visit the [Process Explorer forum on Technet](https://social.technet.microsoft.com/Forums/home?forum=procexplorer).  

## Note on use of symbols:
When you configure the path to DBGHELP.DLL and the symbol path uses the symbol server, the location of DBGHELP.DLL also has to contain the SYMSRV.DLL supporting the server paths used. See [SymSrv documentation](https://docs.microsoft.com/windows-hardware/drivers/debugger/symsrv) or more information on how to use symbol servers.

## Learn More

Here are some other handle and DLL viewing tools and information
available at Sysinternals:

-   [The case of the
    Unexplained...](https://channel9.msdn.com/events/teched/northamerica/2010/wcl315)  
    In this video, Mark describes how he has solved seemingly unsolvable
    system and application problems on Windows.
-   [Handle](handle.md) -
    a command-line handle viewer
-   [ListDLLs](listdlls.md) -
    a command-line DLL viewer
-   [PsList](pslist.md) -
    local/remote command-line process lister
-   [PsKill](pskill.md) -
    local/remote command-line process killer
-   [Defrag Tools: \#2 - Process
    Explorer](https://channel9.msdn.com/shows/defrag-tools/defrag-tools-2-process-explorer)  
    In this episode of Defrag Tools, Andrew Richards and Larry Larsen
    show how to use Process Explorer to view the details of processes,
    both at a point in time and historically.
-   [Windows Sysinternals Primer: Process Explorer, Process Monitor and
    More](https://channel9.msdn.com/events/teched/northamerica/2010/wcl314)  
    Process Explorer gets a lot of attention in the first Sysinternals
    Primer delivered by Aaron Margosis and Tim Reckmeyer at TechEd 2010.
