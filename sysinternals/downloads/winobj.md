--- 
TOCTitle: WinObj
title: WinObj - Windows Sysinternals | Microsoft Docs
description: The ultimate Object Manager namespace viewer is here.
ms:assetid: 'f5aabfba-811c-4b35-8d76-e64fd7083177'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb896657(v=MSDN.10)'
ms.date: 02/14/2011
---

WinObj v2.22
============

**By Mark Russinovich**

Published: February 14, 2011

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/WinObj.zip) [**Download WinObj**](https://download.sysinternals.com/files/WinObj.zip) **(447 KB)**


## Introduction

*WinObj* is a must-have tool if you are a system administrator concerned
about security, a developer tracking down object-related problems, or
just curious about the Object Manager namespace.

*WinObj* is a 32-bit Windows NT program that uses the native Windows NT
API (provided by NTDLL.DLL) to access and display information on the NT
Object Manager's name space. Winobj may seem similar to the Microsoft
SDK's program of the same name, but the SDK version suffers from
numerous significant bugs that prevent it from displaying accurate
information (e.g. its handle and reference counting information are
totally broken). In addition, our WinObj understands many more object
types. Finally, Version 2.0 of our WinObj has user-interface
enhancements, knows how to open device objects, and will let you view
and change object security information using native NT security
editors.  
  

## Installation and Use

There is no device driver component to WinObj, so you can run it like
any Win32 program.

![WinObj](/media/landing/sysinternals/WinObj.png) 
  

## How it Works

The Object Manager is in charge of managing NT objects. As part of this
responsibility, it maintains an internal namespace where various
operating system components, device drivers and Win32 programs can store
and lookup objects. The native NT API provides routines that allow
user-mode programs to browse the namespace and query the status of
objects located there, but the interfaces are undocumented.  
  

## More Information

Helen Custer's *Inside Windows NT* provides a good overview of the
Object Manager name space, and Mark's October 1997 [WindowsITPro
Magazine](http://www.windowsitpro.com/) column, "Inside the Object
Manager", is (of course) an excellent overview.

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/WinObj.zip) [**Download WinObj**](https://download.sysinternals.com/files/WinObj.zip) **(447 KB)**

[**Run WinObj**](https://live.sysinternals.com/Winobj.exe) now from
Live.Sysinternals.com

**Runs on:**

-   Client: Windows Vista and higher.
-   Server: Windows Server 2008 and higher.



