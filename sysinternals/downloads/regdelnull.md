--- 
TOCTitle: RegDelNull
Title: RegDelNull
ms:assetid: '8f4db30a-523f-4482-91d6-f6a68a11126c'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Bb897448(v=MSDN.10)'
---

RegDelNull v1.11
================

**By Mark Russinovich**

Published: July 4, 2016

[![](/media/landing/sysinternals/download_sm.png)
 **Download RegDelNull (152
KB)**](https://download.sysinternals.com/files/regdelnull.zip)


## Introduction

This command-line utility searches for and allows you to delete Registry
keys that contain embedded-null characters and that are otherwise
undeleteable using standard Registry-editing tools. Note: deleting
Registry keys may cause the applications they are associated with to
fail.

 

## Using RegDelNull

**Usage: regdelnull &lt;path&gt; \[-s\]**  

 
-------- 
-----------------------
  **-s**   Recurse into subkeys.
 
-------- 
-----------------------

  
Here's an example of RegDelNull when used on a system on which the
[RegHide](https://technet.microsoft.com/en-us/bb897446#ezb) sample
program has created a null-embedded key:

+------+
| <div |
| styl |
| e="P |
| ADDI |
| NG-R |
| IGHT |
| : 15 |
| px;  |
| PADD |
| ING- |
| LEFT |
| : 20 |
| px;  |
| PADD |
| ING- |
| BOTT |
| OM:  |
| 0px; |
|  PAD |
| DING |
| -TOP |
| : 0p |
| x">  |
|      |
| \    |
| C:\\ |
| &gt; |
| regd |
| elnu |
| ll   |
| hklm |
| -sRe |
| gDel |
| Null |
| v1.1 |
| 0    |
| -    |
| Dele |
| te   |
| Regi |
| stry |
| keys |
| with |
| embe |
| dded |
| Null |
| s\   |
| \    |
| Copy |
| righ |
| t    |
| (C)  |
| 2005 |
| -200 |
| 6    |
| Mark |
| Russ |
| inov |
| ich  |
|      |
| Sysi |
| nter |
| nals |
| -    |
| www. |
| sysi |
| nter |
| nals |
| .com |
|      |
| Null |
| -emb |
| edde |
| d    |
| key  |
| (Nul |
| ls   |
| are  |
| repl |
| aced |
| by   |
| '\*' |
| ):   |
|      |
| HKLM |
| \\SO |
| FTWA |
| RE\\ |
| Syst |
| ems  |
| Inte |
| rnal |
| s\\C |
| an't |
| touc |
| h    |
| me!\ |
| *    |
|      |
| Dele |
| te   |
| (y/n |
| )    |
| y    |
|      |
| Scan |
| comp |
| lete |
| .\   |
|      |
| </di |
| v>   |
+------+

  

[![Download](/media/landing/sysinternals/download_sm.png "Download")
](https://download.sysinternals.com/files/regdelnull.zip)

[**Download Regdelnull**  
](https://download.sysinternals.com/files/regdelnull.zip)**(152 KB)**

  


<div class="RightAdRail">

<div>


## Download

  

[![Download](/media/landing/sysinternals/download_sm.png "Download")
](https://download.sysinternals.com/files/regdelnull.zip)

[**Download Regdelnull**  
](https://download.sysinternals.com/files/regdelnull.zip)**(152 KB)**

 

**Runs on:**

-   Client: Windows Vista (32-bit) and higher
-   Server: Windows Server 2008 (32-bit) and higher
-   Nano Server: 2016 and higher



