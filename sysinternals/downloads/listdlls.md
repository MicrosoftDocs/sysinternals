--- 
TOCTitle: ListDLLs
Title: ListDLLs
ms:assetid: 'b4a511a2-c7d8-4fda-9319-8048718a09eb'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb896656(v=MSDN.10)'
---

ListDLLs v3.2
=============

**By Mark Russinovich**

Published: July 4, 2016

![](/media/landing/sysinternals/download_sm.png)[**Download
ListDLLs**  
](https://download.sysinternals.com/files/listdlls.zip)**(307 KB)**


## Introduction

ListDLLs is a utility that reports the DLLs loaded into processes. You
can use it to list all DLLs loaded into all processes, into a specific
process, or to list the processes that have a particular DLL loaded.
ListDLLs can also display full version information for DLLs, including
their digital signature, and can be used to scan processes for unsigned
DLLs.

## Usage

**listdlls \[-r\] \[-v | -u\] \[processname|pid\]  
listdlls \[-r\] \[-v\] \[-d dllname\]**

 
----------------- 
-----------------------------------------------------------------------------
  **processname**   Dump DLLs loaded by process (partial name accepted).
  **pid**           Dump DLLs associated with the specified process id.
  **dllname**       Show only processes that have loaded the specified DLL.
  **-r**            Flag DLLs that relocated because they are not loaded at their base address.
  **-u**            Only list unsigned DLLs.
  **-v**            Show DLL version information.
 
----------------- 
-----------------------------------------------------------------------------

Examples
--------

List the DLLs loaded into Outlook.exe, including their version
information:

**listdlls -v outlook**

List any unsigned DLLs loaded into any process:

**listdlls -u**

Show processes that have loaded MSO.DLL:

**listdlls -d mso.dll**

 


![](/media/landing/sysinternals/download_sm.png)

[**Download ListDLLs**  
](https://download.sysinternals.com/files/listdlls.zip)**(307 KB)**

<div class="RightAdRail">

<div>


## Download

![](/media/landing/sysinternals/download_sm.png)

[  
**Download
ListDLLs**](https://download.sysinternals.com/files/listdlls.zip)  
**(307 KB)**

  
**Runs on:**

-   Client: Windows Vista and higher
-   Server: Windows Server 2008 and higher
-   Nano Server: 2016 and higher



