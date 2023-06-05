---
TOCTitle: Microsoft Store
title: Microsoft Store
description: Sysinternals Suite is available as an MSIX package from the Microsoft Store.
ms.date: 05/24/2023
---

# Microsoft Store

## Sysinternals Suite

Version 2023.5  
May 24, 2023

Sysinternals Suite is installed as an [MSIX bundle](/windows/msix/package/bundling-overview) from the Microsoft Store.

### Usage

Like most other MSIX packages, Sysinternals Suite is installed per user, but the binaries are stored in a secure location and shared by users. Graphical tools, like Process Explorer, are added to the Windows Start menu. Starting with Windows 11, they are grouped in a Sysinternals Suite folder ([VisualGroup property](/windows/msix/packaging-tool/create-start-group)).

> [!NOTE]
> Windows 10 does not support Start menu folders for MSIX packages so the tools are not grouped in a Sysinternals Suite folder.

All executables are available from the path via Windows [app execution aliases](/uwp/schemas/appxpackage/uapmanifestschema/element-uap5-appexecutionalias):

```
Microsoft.SysinternalsSuite_8wekyb3d8bbwe "Sysinternals Suite"

    accesschk.exe        AccessEnum.exe       ADExplorer.exe       ADInsight.exe
    adrestore.exe        Autologon.exe        Autoruns.exe         autorunsc.exe
    Bginfo.exe           Cacheset.exe         Clockres.exe         Contig.exe
    Coreinfo.exe         CPUSTRES.EXE         Dbgview.exe          Desktops.exe
    disk2vhd.exe         diskext.exe          Diskmon.exe          DiskView.exe
    du.exe               efsdump.exe          FindLinks.exe        handle.exe
    hex2dec.exe          junction.exe         Listdlls.exe         livekd.exe
    LoadOrd.exe          LoadOrdC.exe         logonsessions.exe    movefile.exe
    notmyfault.exe       notmyfaultc.exe      ntfsinfo.exe         pendmoves.exe
    pipelist.exe         procdump.exe         procexp.exe          Procmon.exe
    PsExec.exe           psfile.exe           PsGetsid.exe         PsInfo.exe
    pskill.exe           pslist.exe           PsLoggedon.exe       psloglist.exe
    pspasswd.exe         psping.exe           PsService.exe        psshutdown.exe
    pssuspend.exe        RAMMap.exe           RDCMan.exe           RegDelNull.exe
    regjump.exe          ru.exe               sdelete.exe          ShareEnum.exe
    ShellRunas.exe       sigcheck.exe         streams.exe          strings.exe
    sync.exe             Sysmon.exe           tcpvcon.exe          tcpview.exe
    Testlimit.exe        vmmap.exe            Volumeid.exe         whois.exe
    Winobj.exe           ZoomIt.exe
```

### App Execution Aliases

- To view all, search for "Manage app execution aliases" from Windows Search or Settings.
- They are a special type of reparse point managed by Windows for MSIX packages.
- They are stored in a directory in the user profile, which is in the path:
  - **%LOCALAPPDATA%\Microsoft\WindowsApps**
- The full list for Sysinternals Suite is in the following directory:
  - **%LOCALAPPDATA%\Microsoft\WindowsApps\Microsoft.SysinternalsSuite_8wekyb3d8bbwe**
  - Looking here is a way to list all app execution aliases from the package.
- They are deleted when the MSIX package is uninstalled.

### Processor Architecture

- The MSIX bundle contains separate packages for ARM64, x64, and x86.
- Only the package matching the OS is downloaded and installed.
- Packaged executables do not have a suffix ('64' for x64, '64a' for ARM64).
  - For example, procexp.exe on x64 is the same as the unpackaged procexp64.exe.
