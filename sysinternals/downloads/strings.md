--- 
TOCTitle: Strings
title: Strings
description: Search for ANSI and UNICODE strings in binary images.
ms:assetid: '516a3dc2-ae3c-48ea-9dd2-65d3635eee79'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897439(v=MSDN.10)'
ms.date: 07/04/2016
---

Strings v2.53
=============

**By Mark Russinovich**

Published: July 4, 2016

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/Strings.zip) [** Download Strings**](https://download.sysinternals.com/files/Strings.zip) **(150 KB)**


## Introduction

Working on NT and Win2K means that executables and object files will
many times have embedded UNICODE strings that you cannot easily see with
a standard ASCII strings or grep programs. So we decided to roll our
own. Strings just scans the file you pass it for UNICODE (or ASCII)
strings of a default length of 3 or more UNICODE (or ASCII) characters.
Note that it works under Windows 95 as well.

 

## Using Strings

**usage: strings \[-a\] \[-f offset\] \[-b bytes\] \[-n length\] \[-o\]
\[-q\] \[-s\] \[-u\] &lt;file or directory&gt;**

Strings takes wild-card expressions for file names, and additional
command line parameters are defined as follows:

|Parameter  |Description  |
|---------|---------|
|  **-a**  | Ascii-only search (Unicode and Ascii is default) |
|  **-b**  | Bytes of file to scan |
|  **-f**  | File offset at which to start scanning. |
|  **-o**  | Print offset in file string was located |
|  **-n**  | Minimum string length (default is 3) |
|  **-q**  | Quiet (no banner) |
|  **-s**  | Recurse subdirectories |
|  **-u**  | Unicode-only search (Unicode and Ascii is default) | 

To search one or more files for the presence of a particular string
using strings use a command like this:

**strings \* | findstr /i TextToSearchFor**

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/Strings.zip) [** Download Strings**](https://download.sysinternals.com/files/Strings.zip) **(150 KB)**

**Runs on:**

-   Client: Windows Vista and higher
-   Server: Windows Server 2008 and higher
-   Nano Server: 2016 and higher



