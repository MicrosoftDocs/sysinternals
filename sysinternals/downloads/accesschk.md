---
TOCTitle: AccessChk 
title: AccessChk
description: AccessChk is a command-line tool for viewing the effective permissions on files, registry keys, services, processes, kernel objects, and more.
ms:assetid: 'f15a6468-622f-4c89-98d7-94667c640675' 
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb664922(v=MSDN.10)' 
ms.date: 02/17/2017
---

AccessChk v6.12
===============

**By Mark Russinovich**

Published: November 19, 2017

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/AccessChk.zip)  [**Download AccessChk**](https://download.sysinternals.com/files/AccessChk.zip) **(369 KB)**  
**Run now** from [Sysinternals Live](https://live.sysinternals.com/accesschk.exe).

## Introduction

As a part of ensuring that they've created a secure environment Windows
administrators often need to know what kind of accesses specific users
or groups have to resources including files, directories, Registry keys,
global objects and Windows services. AccessChk quickly answers these
questions with an intuitive interface and output.

## Installation

AccessChk is a console program. Copy AccessChk onto your executable
path. Typing "accesschk" displays its usage syntax.

## Using AccessChk

**Usage: accesschk \[-s\]\[-e\]\[-u\]\[-r\]\[-w\]\[-n\]\[-v\]-\[f
&lt;account&gt;,...\]\[\[-a\]|\[-k\]|\[-p \[-f\] \[-t\]\]|\[-h\]\[-o
\[-t &lt;object type&gt;\]\]\[-c\]|\[-d\]\] \[\[-l
\[-i\]\]|\[username\]\] &lt;file, directory, registry key, process,
service, object&gt;**


|Parameter  |Description  |
|---------|---------|
|  **-a** |  Name is a Windows account right. Specify "\*" as the name to show all rights assigned to a user. Note that when you specify a specific right, only groups and accounts directly assigned to the right are displayed.|
|  **-c** |  Name is a Windows Service, e.g. ssdpsrv. Specify "\*" as the name to show all services and "scmanager" to check the security of the Service Control Manager.|
|  **-d** |  Only process directories or top-level keys|
|  **-e** |  Only show explicitly set-Integrity Levels (Windows Vista Vista and higher only)|
|  **-f** |  If following -p, shows full process token information including groups and privileges. Otherwise is a list of comma-separated accounts to filter from the output.|
|  **-h** |  Name is a file or printer share. Specify '\*' as the name to show all shares.|
|  **-i** |  Ignore objects with only inherited ACEs when dumping full access control lists.|
|  **-k** |  Name is a Registry key, e.g. hklm\\software|
|  **-l** |  Show full security descriptor. Add -i to ignore inherited ACEs.|
|  **-n** |  Show only objects that have no access|
|  **-o** |  Name is an object in the Object Manager namespace (default is root). To view the contents of a directory, specify the name with a trailing backslash or add -s. Add -t and an object type (e.g. section) to see only objects of a specific type.|
|  **-p** |  Name is a process name or PID, e.g. cmd.exe (specify "\*" as the name to show all processes). Add -f to show full process token information, including groups and privileges. Add -t to show threads.|
|  **-q** |  Omit Banner|
|  **-r** |  Show only objects that have read access|
|  **-s** |  Recurse|
|  **-t** |  Object type filter, e.g. "section"|
|  **-u** |  Suppress errors|
|  **-v** |  Verbose (includes Windows Vista Integrity Level)|
|  **-w** |  Show only objects that have write access|

If you specify a user or group name and path, AccessChk will report the
effective permissions for that account; otherwise it will show the
effective access for accounts referenced in the security descriptor.

By default, the path name is interpreted as a file system path (use the
"\\pipe\\" prefix to specify a named pipe path). For each object,
AccessChk prints R if the account has read access, W for write access,
and nothing if it has neither. The -v switch has AccessChk dump the
specific accesses granted to an account.

 
## Examples

The following command reports the accesses that the Power Users account
has to files and directories in \\Windows\\System32:

**accesschk "power users" c:\\windows\\system32**

This command shows which Windows services members of the Users group
have write access to:

**accesschk users -cw \\***

To see what Registry keys under HKLM\\CurrentUser a specific account has
no access to:

**accesschk -kns austin\\mruss hklm\\software**

To see the security on the HKLM\\Software key:

**accesschk -k hklm\\software**

To see all files under \\Users\\Mark on Vista that have an explicit
integrity level:

**accesschk -e -s c:\\users\\mark**

To see all global objects that Everyone can modify:

**accesschk -wuo everyone \\basednamedobjects**


[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/AccessChk.zip)  [**Download AccessChk**](https://download.sysinternals.com/files/AccessChk.zip) **(369 KB)**  
**Run now** from [Sysinternals Live](https://live.sysinternals.com/accesschk.exe).
