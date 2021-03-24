--- 
TOCTitle: TLSDeprecation
title: Preparing for the mandatory use of TLS 1.2+
description: As of November 2018 Sysinternals transitions to TLS 1.2 site certificates.
ms.date: 09/17/2017
---

# Preparing for the mandatory use of TLS 1.2+

**By Mark Cook**

Published: September 17, 2018

## Summary

In support of our promise to provide best-in-class encryption to our customers, Microsoft are planning to discontinue support for Transport Layer Security (TLS) versions 1.0 and 1.1 soon.
We understand that the security of your data is important, and we are committed to transparency about changes that could affect your use of the service.
The [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336/schannel-implementation-of-tls-1-0-in-windows-security-status-update-n) has no known security vulnerabilities. But because of the potential for future protocol downgrade attacks and other TLS vulnerabilities, we are discontinuing support for the use of TLS 1.0 and 1.1 on [https://docs.microsoft.com/sysinternals/](https://docs.microsoft.com/sysinternals) and [https://live.sysinternals.com](https://live.sysinternals.com).
For information about how to remove TLS 1.0 and 1.1 dependencies, see the whitepaper [Solving the TLS 1.0 problem](https://www.microsoft.com/download/details.aspx?id=55266). 

## More Information

As of October 31, 2018, Sysinternals sites will no longer support TLS 1.0 and 1.1.

By October 31, 2018, all client-server and browser-server combinations should use TLS version 1.2 (or a later version) to ensure connection without issues to [https://docs.microsoft.com/sysinternals/](https://docs.microsoft.com/sysinternals) or [https://live.sysinternals.com](https://live.sysinternals.com). This may require updates to certain client-server and browser-server combinations.

If you do not update to TLS version 1.2 (or later) by October 31, 2018, you may experience issues when connecting and you will be required to update to TLS 1.2 as part of the resolution.

The following are some clients that we know are unable to use TLS 1.2. Please update your clients to ensure uninterrupted access to the service.

* Android 4.3 and earlier versions
* Firefox version 5.0 and earlier versions
* Internet Explorer 8-10 on Windows 7 and earlier versions
* Internet Explorer 10 on Win Phone 8.0
* Safari 6.0.4/OS X10.8.4 and earlier versions

Although current analysis of connections to Microsoft Online services shows that most services/endpoints see very little TLS 1.0 and 1.1 usage, we are providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.0 and 1.1 ends. 

Note Using TLS 1.2 does not mean you must have TLS 1.0/1.1 disabled in your environments by October 31, 2018. If parts of your environment require the use of TLS 1.0 and 1.1 on or after October 31, 2018, you can leave the older protocol versions enabled.
