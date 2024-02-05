--- 
TOCTitle: PendMoves
title: PendMoves and MoveFile
description: Enumerate the list of file rename and delete commands that will be executed the next boot.
ms:assetid: 'a49e9434-8fa3-4f2c-9ae1-8212360d4917'
ms:mtpsurl: 'https://technet.microsoft.com/Bb897556(v=MSDN.10)'
ms.date: 09/17/2020
---

# PendMoves v1.3 and MoveFile v1.02

**By Mark Russinovich**
Published: September 17, 2020

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/pendmoves.zip) [**Download PendMoves and MoveFile**](https://download.sysinternals.com/files/pendmoves.zip) **(988 KB)**

## Introduction

There are several applications,  such as service packs and  hotfixes, that must replace a file that's in use and is unable to. Windows therefore provides the MoveFileEx API to rename or  delete a file and allows the caller to specify that they want the operation to take place the  next time the system boots,before the files are referenced. Session Manager performs this task by reading the registered rename and delete commands from  the HKLM\\System\\CurrentControlSet\\Control\\Session Manager\\PendingFileRenameOperations value. 

## PendMoves Usage

This applet dumps the contents of the pending rename/delete value  and also reports an error when the source file is notaccessible. 

**Usage: pendmoves**  
Here is example output that shows a temporary installation file is scheduled for deletion at the next reboot:

```Shell
C:\\>pendmoves 
PendMove v1.2 
Copyright (C) 2013 Mark Russinovich 
Sysinternals - www.sysinternals.com  

Source: C:\\Config.Msi\\3ec7bbbf.rbf 
Target: DELETE 
```

## MoveFile usage

The included MoveFile utility allows you to schedule move and  delete commands for the next reboot:
**usage: movefile [source] [dest]**  
Specifying an empty destination  ("") deletes the source at boot. An example that deletes test.exe is: 

```Shell
movefile test.exe ""
```

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/pendmoves.zip) [**Download PendMoves and MoveFile**](https://download.sysinternals.com/files/pendmoves.zip) **(988 KB)**
