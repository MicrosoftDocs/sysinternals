--- 
TOCTitle: RegDelNull
title: RegDelNull
description: Scan for and delete Registry keys that contain embedded null-characters that are otherwise undeleteable by standard Registry-editing tools.
ms:assetid: '8f4db30a-523f-4482-91d6-f6a68a11126c'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897448(v=MSDN.10)'
ms.date: 07/04/2016
---

RegDelNull v1.11
================

**By Mark Russinovich**

Published: July 4, 2016

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/Regdelnull.zip) [**Download RegDelNull**](https://download.sysinternals.com/files/Regdelnull.zip) **(152 KB)**


## Introduction

This command-line utility searches for and allows you to delete Registry
keys that contain embedded-null characters and that are otherwise
undeleteable using standard Registry-editing tools. Note: deleting
Registry keys may cause the applications they are associated with to
fail.

 

## Using RegDelNull

**Usage: regdelnull &lt;path&gt; \[-s\]**  
 
|Parameter  |Description  |
|---------|---------|
|  **-s** |  Recurse into subkeys. |


  
Here's an example of RegDelNull when used on a system on which the
[RegHide](reghide.md) sample
program has created a null-embedded key:

```Shell
C:\>regdelnull hklm -sRegDelNull v1.10 - Delete Registry keys with embedded Nulls 

Copyright (C) 2005-2006 Mark Russinovich
Sysinternals - www.sysinternals.com
Null-embedded key (Nulls are replaced by '*'):
HKLM\SOFTWARE\Systems Internals\Can't touch me!*
Delete (y/n) y
Scan complete.
```

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/Regdelnull.zip) [**Download RegDelNull**](https://download.sysinternals.com/files/Regdelnull.zip) **(152 KB)**

**Runs on:**

-   Client: Windows Vista (32-bit) and higher
-   Server: Windows Server 2008 (32-bit) and higher
-   Nano Server: 2016 and higher



