--- 
TOCTitle: Autologon
title: Autologon
description: Bypass password screen during logon.
ms:assetid: '121f300c-85cb-418d-8199-48e587d864c3'
ms:mtpsurl: 'https://technet.microsoft.com/Bb963905(v=MSDN.10)'
ms.date: 09/17/2020
---

# Autologon v3.10

**By Mark Russinovich**

Published: August 29, 2016

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/AutoLogon.zip) [**Download Autologon**](https://download.sysinternals.com/files/AutoLogon.zip) **(495 KB)**  
**Run now** from [Sysinternals Live](https://live.sysinternals.com/Autologon.exe).

## Introduction

Autologon enables you to easily configure Windows’ built-in autologon
mechanism. Instead of waiting for a user to enter their name and
password, Windows uses the credentials you enter with Autologon, which
are encrypted in the Registry, to log on the specified user
automatically.

**Note:** Although the password is encrypted in the registry as an LSA secret, a user with administrative rights can easily retrieve and decrypt them.

See also: https://docs.microsoft.com/en-us/windows/win32/secauthn/protecting-the-automatic-logon-password

*Autologon* is easy enough to use. Just run autologon.exe, fill in the
dialog, and hit Enable. The next time the system starts, Windows will try to use the entered credentials to log on the user at the console. Note that Autologon does not verify the submitted credentials, nor does it verify that the specified user account is allowed to log on to the computer.

To turn off auto-logon, hit *Disable*. Also, if
the shift key is held down before the system performs an autologon, the
autologon will be disabled for that logon. You can also pass the
username, domain and password as command-line arguments:

**autologon user domain password**

**Note:** When Exchange Activesync password restrictions are in place,
Windows will not process the autologon configuration.

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/AutoLogon.zip) [**Download Autologon**](https://download.sysinternals.com/files/AutoLogon.zip) **(495 KB)**  
**Run now** from [Sysinternals Live](https://live.sysinternals.com/Autologon.exe).
