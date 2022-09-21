--- 
TOCTitle: Junction
title: Junction
description: Create Win2K NTFS junction points.
ms:assetid: '16f763c0-cb78-4d67-a865-63e79bef0c58'
ms:mtpsurl: 'https://learn.microsoft.com/sysinternals/downloads/junction'
ms.date: 09/17/2020
---

# Junction v1.07

**By Mark Russinovich**

Published: July 4, 2016

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/Junction.zip) [**Download Junction**](https://download.sysinternals.com/files/Junction.zip) **(504 KB)**

## Introduction

Windows 2000 and later support junction points, where a directory serves as an
alias to another directory on the computer. For example, if the directory
D:\\WIN specified C:\\WINNT\\SYSTEM32 as its target, then an application
accessing D:\\WIN\\DRIVERS would in reality be accessing
C:\\WINNT\\SYSTEM32\\DRIVERS. Unfortunately, Windows 2000 comes with no tools
for creating junction points. You have to purchase the Windows 2000 Resource
Kit, which comes with the `linkd` utility for creating junctions. I therefore
decided to write my own junction point-creating tool: `Junction`. It creates
NTFS junction points, it allows you to see if files or directories are actually
reparse points. (Reparse points are the mechanism on which NTFS junctions are
based. The Remote Storage Service uses reparse points as well as volume mount
points.)

> [!NOTE]
> Windows does not support junctions to directories on remote shares.

## Using Junction

### Syntax

- To obtain reparse point information: `junction.exe [-s] [-q] <file or directory>`
- To create a junction point: `junction.exe <junction directory> <junction target>`
- To delete a junction point: `junction.exe -d <junction directory>`

### Parameters

| Parameter              | Description                                                       |
| ---------------------- | ----------------------------------------------------------------- |
| `<file or directory>`  | Path to the file or folder to query for reparse point information |
| `-s`                   | Recurse subdirectories                                            |
| `<junction directory>` | Name of the junction point to create or delete                    |
| `<junction target>`    | Full path to the target of the junction point to create           |
| `-d`                   | Delete the junction point                                         |


## Examples

To determine if a file is a junction, specify the file name:

```cmd
junction c:\test
```

To list junctions beneath a directory, include the –s switch:

```cmd
junction -s c:\
```

To create a junction c:\\Program-Files for "c:\\Program Files":

```cmd
junction c:\Program-Files "c:\Program Files"
```

To delete a junction, use the –d switch:

```cmd
junction -d c:\Program-Files
```

## Return codes

**0**  - on success  
**-1** - on failed creation of new junction  
**0**  - on failed deletion of junction  (e.g. if file not found)  
**0**  - on the check if a file is a junction fails (e.g. if file not found)  

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/Junction.zip) [**Download Junction**](https://download.sysinternals.com/files/Junction.zip) **(504 KB)**

**Runs on:**

- Client: Windows Vista and higher
- Server: Windows Server 2008 and higher
- Nano Server: 2016 and higher
