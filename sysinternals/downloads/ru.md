--- 
TOCTitle: Registry Usage
Title: Registry Usage
ms:assetid: 'a0d594d7-9653-4dc3-8a32-d1ab452d04e7'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Dn194428(v=MSDN.10)'
---

Registry Usage (RU) v1.2
========================

**By Mark Russinovich**

Published: July 4, 2016

[![](/media/landing/sysinternals/download_sm.png)
 **Download RU**  
](https://download.sysinternals.com/files/ru.zip)**(156 KB)**


## Introduction

Ru (registry usage) reports the registry space usage for the registry
key you specify. By default it recurses subkeys to show the total size
of a key and its subkeys.

## Using Registry Usage (RU)

**usage: ru \[-c\[t\]\] \[-l &lt;levels&gt; | -n | -v\] \[-q\]
&lt;absolute path&gt;**

**usage: ru \[-c\[t\]\] \[-l &lt;levels&gt; | -n | -v\] \[-q\] -h
&lt;hive file&gt; \[relative path\]**

 
-------- 
---------------------------------------------------------------------------------------------
  **-c**   Print output as CSV. Specify -ct for tab delimiting.
  **-h**   Load the specified hive file, perform the size calculation, then unload it and compress it.
  **-l**   Specify subkey depth of information (default is one level).
  **-n**   Do not recurse.
  **-q**   Quiet (no banner).
  **-v**   Show size of all subkeys.
 
-------- 
---------------------------------------------------------------------------------------------

 

CSV output is formatted as:

Path,CurrentValueCount,CurrentValueSize,ValueCount,KeyCount,KeySize,WriteTime

[![Download](/media/landing/sysinternals/download_sm.png "Download")
](https://download.sysinternals.com/files/ru.zip)

[**Download RU**  
](https://download.sysinternals.com/files/ru.zip)**(156 KB)**

