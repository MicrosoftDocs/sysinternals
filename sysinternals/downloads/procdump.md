--- 
TOCTitle: ProcDump
title: ProcDump
description: This command-line utility is aimed at capturing process dumps of otherwise difficult to isolate and reproduce CPU spikes.
ms:assetid: 'f4201936-3609-4255-8d1e-93601e34aa34'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Dd996900(v=MSDN.10)'
ms.date: 16/05/2017
---

 

ProcDump v9.0
=============

**By Mark Russinovich**

Published: May 16, 2017

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/Procdump.zip) [**Download ProcDump**](https://download.sysinternals.com/files/Procdump.zip) **(439 KB)**


## Introduction

ProcDump is a command-line utility whose primary purpose is monitoring
an application for CPU spikes and generating crash dumps during a spike
that an administrator or developer can use to determine the cause of the
spike. ProcDump also includes hung window monitoring (using the same
definition of a window hang that Windows and Task Manager use),
unhandled exception monitoring and can generate dumps based on the
values of system performance counters. It also can serve as a general
process dump utility that you can embed in other scripts.

## Using ProcDump

**usage: procdump \[-a\] \[\[-c|-cl CPU usage\] \[-u\] \[-s seconds\]\]
\[-n exceeds\] \[-e \[1 \[-b\]\] \[-f &lt;filter,...&gt;\] \[-g\] \[-h\]
\[-l\] \[-m|-ml commit usage\] \[-ma | -mp\] \[-o\] \[-p|-pl counter
threshold\] \[-r\] \[-t\] \[-d &lt;callback DLL&gt;\] \[-64\] &lt;\[-w\]
&lt;process name or service name or PID&gt; \[dump file\] | -i &lt;dump
file&gt; | -u | -x &lt;dump file&gt; &lt;image file&gt; \[arguments\]
&gt;\] \[-? \[ -e\]**

  
|Parameter  |Description  |
|---------|---------|
| **-a** | Avoid outage. Requires -r. If the trigger will cause the target to suspend for a prolonged time due to an exceeded concurrent dump   limit, the trigger will be skipped. |
| **-b** | Treat debug breakpoints as exceptions (otherwise ignore them). |
| **-c** | CPU threshold at which to create a dump of the process. |
| **-cl** | CPU threshold below which to create a dump of the process. |
| **-d** | Invoke the minidump callback routine named MiniDumpCallbackRoutine of the specified DLL. |
| **-e** | Write a dump when the process encounters an unhandled exception. Include the 1 to create dump on first chance exceptions. |
| **-f** | Filter the first chance exceptions. Wildcards (\*) are supported. To just display the   names without dumping, use a blank ("") filter. |
| **-g** | Run as a native debugger in a managed process (no interop). |
| **-h** | Write dump if process has a hung window (does not respond to window messages for at least 5 seconds). |
| **-i** | Install ProcDump as the AeDebug postmortem debugger. Only -ma, -mp, -d and -r are supported as  additional options. |
| **-l** | Display the debug logging of the process. |
| **-m** | Memory commit threshold in MB at which to create a dump. |
| **-ma** | Write a dump file with all process memory. The default dump format only includes thread and  handle information. |
| **-ml** | Trigger when memory commit drops below specified MB value. |
| **-mp** | Write a dump file with thread and handle information, and all read/write process memory. To minimize dump size, memory areas larger than 512MB are searched   for, and if found, the largest area is excluded. A memory area  is the collection of same sized  memory allocation areas. The removal of this (cache) memory reduces Exchange and SQL Server  dumps by over 90%. |
| **-n** | Number of dumps to write before  exiting. |
| **-o** | Overwrite an existing dump file.  |
| **-p** | Trigger on the specified performance counter when the threshold is exceeded. Note: to  specify a process counter when   there are multiple instances of  the process running, use the     process ID with the following syntax: "\\Process(&lt;name&gt;\_&lt;pid&gt;)\\counter" |
| **-pl** | Trigger when performance counter falls below the specified value.  |
| **-r** | Dump using a clone. Concurrent limit is optional (default 1, max 5).<br />CAUTION: a high concurrency value may impact system performance.<br />-   Windows 7   : Uses Reflection. OS doesn't support -e.<br />-   Windows 8.0 : Uses Reflection. OS doesn't support -e.<br />-   Windows 8.1+: Uses PSS. All trigger types are supported.  |
| **-s** | Consecutive seconds before dump  is written (default is 10). |
| **-t** | Write a dump when the process terminates. |
| **-u** | Treat CPU usage relative to a single core (used with -c).<br />As the only option, Uninstalls ProcDump as the postmortem debugger. |
| **-w** | Wait for the specified process to launch if it's not running. |
| **-x** | Launch the specified image with  optional arguments. If it is a Store Application or Package, ProcDump will start on the next  activation (only). |
| **-64** | By default ProcDump will capture a 32-bit dump of a 32-bit process when running on 64-bit Windows.  This option overrides to create a 64-bit dump. Only use for WOW64  subsystem debugging. |
| **-?** | Use -? -e to see example command lines. |

If you omit the dump file name, it defaults to
&lt;processname&gt;\_&lt;datetime&gt;.dmp.

Use the -accepteula command line option to automatically accept the
Sysinternals license agreement.



## Examples

Write a mini dump of a process named 'notepad' (only one match can
exist):

**C:\\&gt;procdump notepad**

  
Write a full dump of a process with PID '4572':

**C:\\&gt;procdump -ma 4572**

  
Write 3 mini dumps 5 seconds apart of a process named 'notepad':

**C:\\&gt;procdump -s 5 -n 3 notepad**

  
Write up to 3 mini dumps of a process named 'consume' when it exceeds
20% CPU usage for five seconds:

**C:\\&gt;procdump -c 20 -s 5 -n 3 consume**

  
Write a mini dump for a process named 'hang.exe' when one of it's
Windows is unresponsive for more than 5 seconds:

**C:\\&gt;procdump -h hang.exe hungwindow.dmp**

  
Write a mini dump of a process named 'outlook' when total system CPU
usage exceeds 20% for 10 seconds:

**C:\\&gt;procdump outlook -p "\\Processor(\_Total)\\% Processor Time" 20**

  
Write a full dump of a process named 'outlook' when Outlook's handle
count exceeds 10,000:

**C:\\&gt;procdump -ma outlook -p "\\Process(Outlook)\\Handle Count" 10000**

  
Write a MiniPlus dump of the Microsoft Exchange Information Store when
it has an unhandled exception:

**C:\\&gt;procdump -mp -e store.exe**

  
Display without writing a dump, the exception codes/names of w3wp.exe:

**C:\\&gt;procdump -e 1 -f "" w3wp.exe**

  
Write a mini dump of w3wp.exe if an exception's code/name contains
'NotFound':

**C:\\&gt;procdump -e 1 -f NotFound w3wp.exe**

  
Launch a process and then monitor it for exceptions:

**C:\\&gt;procdump -e 1 -f "" -x c:\\dumps consume.exe**

  
Register for launch, and attempt to activate, a modern 'application'. A
new ProcDump instance will start when it activated to monitor for
exceptions:

**C:\\&gt;procdump -e 1 -f "" -x c:\\dumpsMicrosoft.BingMaps\_8wekyb3d8bbwe!AppexMaps**

  
Register for launch of a modern 'package'. A new ProcDump instance will
start when it is (manually) activated to monitor for exceptions:

**C:\\&gt;procdump -e 1 -f "" -x c:\\dumps Microsoft.BingMaps\_1.2.0.136\_x64\_\_8wekyb3d8bbwe**

  
Register as the Just-in-Time (AeDebug) debugger. Makes full dumps in
c:\\dumps.

**C:\\&gt;procdump -ma -i c:\\dumps**

See a list of example command lines (the examples are listed above):

**C:\\&gt;procdump -? -e**



## Related Links

-   **[Windows Internals Book**](~/learn/windows-internals.md)  
    The official updates and errata page for the definitive book on
    Windows internals, by Mark Russinovich and David Solomon.
-   [**Windows Sysinternals Administrator's Reference**](~/learn/troubleshooting-book.md)  
    The official guide to the Sysinternals utilities by Mark Russinovich and
    Aaron Margosis, including descriptions of all the tools, their
    features, how to use them for troubleshooting, and example
    real-world cases of their use.



[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/Procdump.zip) [**Download ProcDump**](https://download.sysinternals.com/files/Procdump.zip) **(439 KB)**
  
**Runs on:**

-   Client: Windows Vista and higher.
-   Server: Windows Server 2008 and higher.



## Learn More

-   [Defrag Tools: \#9 -
    ProcDump](http://channel9.msdn.com/shows/defrag-tools/defrag-tools-9-procdump)  
    This episode of Defrag Tools covers what the tool captures and
    expected outage durations
-   [Defrag Tools: \#10 - ProcDump -
    Triggers](http://channel9.msdn.com/shows/defrag-tools/defrag-tools-10-procdump-triggers)  
    This episode covers trigger options in particular 1st & 2nd chance
    exceptions
-   [Defrag Tools: \#11 - ProcDump - Windows 8 & Process
    Monitor](http://channel9.msdn.com/shows/defrag-tools/defrag-tools-11-procdump-windows-8--process-monitor)  
    This episode covers modern application support and Process Monitor
    logging support



