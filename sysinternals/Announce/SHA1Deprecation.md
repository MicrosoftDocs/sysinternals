--- 
TOCTitle: SHA1Deprecation
title: Preparing for the mandatory use of SHA1
ms.date: 06/20/2019
---

Preparing for the deprecation of SHA1 signatures
===========

**By Mark Cook**

Published: June 20, 2019


## Summary

In support of our promise to provide best-in-class encryption to our customers, Microsoft are planning to discontinue support for SHA1 code signing certificates. 
Background details on the reasons for this and how it will affect you are available at [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/en-us/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).

## More Information

Currently Sysinternals binaries are dual signed using for SHA-1 and SHA-2. As of July 31, 2019, these will be signed using only SHA-2 signatures.

Prior to this date customers running our tools on legacy OS versions will need to install SHA-2 code signing support in order to run the SHA-2 signed versions.
Although this support will typically be delivered via Windows Update, standalone security updates are also available for download. 
Refer to [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/en-us/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus) for details on these updates



