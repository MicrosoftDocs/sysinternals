--- 
TOCTitle: PsFile
title: PsFile
description: See what files are opened remotely.
ms:assetid: '01e9104e-4b10-4fec-a69d-a521dcc1b1e3'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897552(v=MSDN.10)'
ms.date: 06/29/2016
---

PsFile v1.03
============

**By Mark Russinovich**

Published: June 29, 2016

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(1.6 MB)**


## Introduction

The "net file" command shows you a list of the files that other
computers have opened on the system upon which you execute the command,
however it truncates long path names and doesn't let you see that
information for remote systems. *PsFile* is a command-line utility that
shows a list of files on a system that are opened remotely, and it also
allows you to close opened files either by name or by a file
identifier.  

## Installation

Just copy *PsFile* onto your executable path, and type "psfile".  

## Using PsFile

The default behavior of *PsFile* is to list the files on the local
system that are open by remote systems. Typing a command followed by "-
" displays information on the syntax for the command.

**Usage: psfile \[\\\\RemoteComputer \[-u Username \[-p Password\]\]\]
\[\[Id | path\] \[-c\]\]**

|Parameter  |Description  |
|---------|---------|
|  **-u** |    Specifies optional user name for login to remote computer.|
|  **-p** |    Specifies password for user name. If this is omitted, you will be prompted to enter the password without it being echoed to the screen.|
|  **Id** |    Identifier (as assigned by PsFile) of the file for which to display information or to close.|
|  **Path** |  Full or partial path of files to match for information display or close.|
|  **-c**  |   Closes the files identifed by ID or path.|

## How it Works

*PsFile* uses the NET API, which is documented in the Platform SDK.
 
[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(1.6 MB)**