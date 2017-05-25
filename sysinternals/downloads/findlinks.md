--- 
TOCTitle: FindLinks
Title: FindLinks
ms:assetid: 'f3fb08e4-d0af-4191-b09d-08bf44694281'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Hh290814(v=MSDN.10)'
---

FindLinks v1.1
==============

**By Mark Russinovich**

Published: July 4, 2016

[![](/media/landing/sysinternals/download_sm.png)
 **Download FindLinks**  
](https://download.sysinternals.com/files/findlinks.zip)**(153 KB)**


## Introduction

FindLinks reports the file index and any hard links (alternate file
paths on the same volume) that exist for the specified file.  A file's
data remains allocated so long as at it has at least one file name
referencing it.

## Using FindLinks

**Usage: findlinks &lt;filename&gt;**

## Example

The following command reports the file paths that reference the same
file data as C:\\Windows\\Notepad.exe:

**C:\\&gt;findlinks c:\\windows\\notepad.exe  
  
FindLinks - Locate file hard links  
Copyright (C) 2011 Mark Russinovich  
Sysinternals -www.sysinternals.com  
  
c:\\windows\\notepad.exe  
        Index:  0x000057D9  
        Links:  3**

