--- 
TOCTitle: AdInsight
title: AdInsight
description: An LDAP (Light-weight Directory Access Protocol) real-time monitoring tool aimed at troubleshooting Active Directory client applications.
ms:assetid: 'f3eb3300-3b79-45b4-bf1e-b4ae9fc68ca8'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897539(v=MSDN.10)'
ms.date: 10/26/2015
---

Insight for Active Directory v1.2
=================================

**By Mark Russinovich**

Published: October 26, 2015

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/AdInsight.zip) [**Download AdInsight**](https://download.sysinternals.com/files/AdInsight.zip) **(113 KB)**  
**Run now** from [Sysinternals Live](https://live.sysinternals.com/ADInsight.exe).

## Introduction

ADInsight is an LDAP (Light-weight Directory Access Protocol) real-time
monitoring tool aimed at troubleshooting Active Directory client
applications. Use its detailed tracing of Active Directory client-server
communications to solve Windows authentication, Exchange, DNS, and other
problems.

ADInsight uses DLL injection techniques to intercept calls that
applications make in the Wldap32.dll library, which is the standard
library underlying Active Directory APIs such ldap and ADSI. Unlike
network monitoring tools, ADInsight intercepts and interprets all
client-side APIs, including those that do not result in transmission to
a server. ADInsight monitors any process into which it can load it’s
tracing DLL, which means that it does not require administrative
permissions, however, if run with administrative rights, it will also
monitor system processes, including windows services.

![ADInsight](/media/landing/sysinternals/adinsight.jpg)  

 
[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/AdInsight.zip) [**Download AdInsight**](https://download.sysinternals.com/files/AdInsight.zip) **(113 KB)**

**Run now** from [Sysinternals Live](https://live.sysinternals.com/ADInsight.exe).

**Runs on:**

-   Client: Windows Vista and higher.
-   Server: Windows Server 2008 and higher.

## Related Links

The Sysinternals
[AdRestore](adrestore.md)
utility enables you to restore deleted objects on Windows Server 2003
domains.

[AD Explorer](adexplorer.md)
is an advanced Active Directory (AD) viewer and editor.  