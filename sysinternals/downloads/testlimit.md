--- 
TOCTitle: Testlimit
title: Testlimit
description: Windows Stress test utility.
ms:assetid: '2a241f34-ffa4-4102-88f4-8fcfdfc28e09'
ms.date: 09/09/2020
---

Testlimit v5.24
==============

**By Mark Russinovich**

Published: November 17, 2016

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/Testlimit.zip) [**Download Testlimit**](https://download.sysinternals.com/files/Testlimit.zip) **(234 KB)**


## Introduction

Testlimit is a command-line utility that can be used to stress-test 
your PC and/or applications by simulating low resource conditions for 
memory, handles, processes, threads and other system objects. 


**usage: Testlimit
 [[-h [-u]] | [-p [-n]] | [-t [-n [KB]]] | [-u [-i]] | [-g [object size]] | [-a|-d|-l|-m|-r|-s|-v [MB]] | [-w]] [-c [count]] [-e [seconds]]**


|Parameter  |Description  |
|---------|---------|
|  **-a**      |       Leak Address Windowing Extensions (AWE) memory in specified MBs (default is 1)|
|  **-c**      |       Count of number of objects to allocate (default is as many as possible). This must be the last option specified|
|  **-d**      |       Leak and touch memory in specified MBs (default is 1)|
|  **-e**      |       Seconds elapsed between allocations (default is 0)|
|  **-g**      |       Create GDI handles of specified size (default 1 byte). Specify a size of 0 to cause GDI object exhaustion|
|  **-h**      |       Create handles. Specify -u to also allocate file objects|
|  **-i**      |       Exhaust USER desktop heap|
|  **-l**      |       Allocate the specified amount of large pages (rounded to large size multiple)|
|  **-m**      |       Leak memory in specified MBs (default is 1)|
|  **-p**      |       Create processes - add -n to set min working set. Add -n to set min working set of processes to smallest|
|  **-r**      |       Reserve memory in specified MBs (default is 1)|
|  **-s**      |       Leak shared memory in specified MBs (default is 1)|
|  **-t**      |       Create threads - add -n to specify minimum stack reserve (in KB)|
|  **-u**      |       Create USER handles to menus|
|  **-v**      |       VirtualLock memory in specified MBs (default is 1)|
|  **-w**      |       Reset working set minimum to highest possible value|

**Runs on:**

-   Client: Windows Vista and higher
-   Server: Windows Server 2003 and higher
-   Nano Server: 2016 and higher

## Related Links

-   [**Windows Internals Book**](~/resources/windows-internals.md)  The official updates and errata page for the definitive book on
    Windows internals, by Mark Russinovich and David Solomon.
-   [**Windows Sysinternals Administrator's Reference**](~/resources/troubleshooting-book.md)  The
    official guide to the Sysinternals utilities by Mark Russinovich and
    Aaron Margosis, including descriptions of all the tools, their
    features, how to use them for troubleshooting, and example
    real-world cases of their use.

## Download

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/TestLimit.zip)[**Download Testlimit**](https://download.sysinternals.com/files/Testlimit.zip) **(234 KB)**  
**Run now** from [Sysinternals Live](https://live.sysinternals.com/Testlimit.exe).




