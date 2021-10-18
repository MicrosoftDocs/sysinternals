--- 
TOCTitle: ShellRunas
title: ShellRunas
description: Launch programs as a different user via a convenient shell context-menu entry.
ms:assetid: 'd3e6e430-46f4-48ba-8860-4e2daa38024f'
ms:mtpsurl: 'https://technet.microsoft.com/Cc300361(v=MSDN.10)'
ms.date: 10/12/2021
---

# ShellRunas v1.02

**By Mark Russinovich and Jon Schwartz**

Published: October 12, 2021

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/ShellRunas.zip) [**Download ShellRunas**](https://download.sysinternals.com/files/ShellRunas.zip) **(90 KB)**

## Introduction

The command-line Runas utility is handy for launching programs under
different accounts, but it’s not convenient if you’re a heavy Explorer
user. ShellRunas provides functionality similar to that of Runas to
launch programs as a different user via a convenient shell context-menu
entry.

**Screenshot**

![ShellRunas screenshot](media/shellrunas/ShellRunas.jpg)

## Using ShellRunas

**Usage:**

**shellrunas /reg \[/quiet\]  
shellrunas /regnetonly \[/quiet\]  
shellrunas /unreg \[/quiet\]  
shellrunas \[/netonly\] &lt;*program*&gt; \[*arguments*\]**

|Parameter  |Description  |
|---------|---------|
|  **/reg**                   |  Registers ShellRunas shell context-menu entry|
|  **/regnetonly**            |  Registers Shell /netonly context-menu entry  <br /> **Note:** a command prompt will flash when the program starts|
|  **/unreg**                 |  Unregisters ShellRunas shell context-menu  entry|
|  **/quiet**                 |  Register or unregisters ShellRunas shell context-menu entry without result dialog|
|  **/netonly**               |  Use if specified credentials are for remote access only|
|  **&lt;program&gt;**        |  Runs program with specified credentials and parameters

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/ShellRunas.zip) [**Download ShellRunas**](https://download.sysinternals.com/files/ShellRunas.zip) **(90 KB)**

**Runs on:**

- Client: Windows Vista and higher.
- Server: Windows Server 2008 and higher.

## Getting Help

If you have problems or questions, please visit the [Sysinternals Forum](https://forum.sysinternals.com).  
