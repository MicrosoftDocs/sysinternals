--- 
TOCTitle: Streams
title: Streams
description: Reveal NTFS alternate streams.
ms:assetid: '5e6c8d3a-0865-4e4d-9f23-bd4c431a27c3'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897440(v=MSDN.10)'
ms.date: 07/04/2016
---

Streams v1.6
============

**By Mark Russinovich**

Published: July 4, 2016

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/Streams.zip) [**Download Streams**](https://download.sysinternals.com/files/Streams.zip) **(140 KB)**


## Introduction

The NTFS file system provides applications the ability to create
alternate data streams of information. By default, all data is stored in
a file's main unnamed data stream, but by using the syntax
'file:stream', you are able to read and write to alternates. Not all
applications are written to access alternate streams, but you can
demonstrate streams very simply. First, change to a directory on a NTFS
drive from within a command prompt. Next, type 'echo hello &gt;
test:stream'. You've just created a stream named 'stream' that is
associated with the file 'test'. Note that when you look at the size of
test it is reported as 0, and the file looks empty when opened in any
text editor. To see your stream enter 'more &lt; test:stream' (the type
command doesn't accept stream syntax so you have to use more).

NT does not come with any tools that let you see which NTFS files have
streams associated with them, so I've written one myself. Streams will
examine the files and directories (note that directories can also have
alternate data streams) you specify and inform you of the name and sizes
of any named streams it encounters within those files. Streams makes use
of an undocumented native function for retrieving file stream
information.



## Using Streams

**Usage: streams \[-s\] \[-d\] &lt;file or directory&gt;**


|                         Parameter                         |       Description       |
|-----------------------------------------------------------|-------------------------|
|                          **-s**                           | Recurse subdirectories. |
|                          **-d**                           |     Delete streams.     |
|            Streams takes wildcards e.g. 'streams \*.txt'. |                         |

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/Streams.zip) [**Download Streams**](https://download.sysinternals.com/files/Streams.zip) **(140 KB)**

**Runs on:**

-   Client: Windows Vista and higher
-   Server: Windows Server 2008 and higher
-   Nano Server: 2016 and higher



