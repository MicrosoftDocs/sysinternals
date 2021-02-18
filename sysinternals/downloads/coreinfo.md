--- 
TOCTitle: Coreinfo
title: Coreinfo
description: Coreinfo is a command-line utility that shows you the mapping between logical processors and the physical processor.
ms:assetid: 'c5e117b5-d674-4409-914d-17bcac43f1fd'
ms:mtpsurl: 'https://technet.microsoft.com/Cc835722(v=MSDN.10)'
ms.date: 02/18/2021
---
# Coreinfo v3.52

**By Mark Russinovich**

Published: February 18, 2021

[![Download](/media/landing/sysinternals/Download_sm.png)](https://download.sysinternals.com/files/Coreinfo.zip) [**Download Coreinfo**](https://download.sysinternals.com/files/Coreinfo.zip) **(367 KB)**

## Introduction

Coreinfo is a command-line utility that shows you the mapping between logical processors and the physical processor, NUMA node, and socket on which they reside, as well as the cache’s assigned to each logical processor. It uses the Windows’ [GetLogicalProcessorInformation](https://msdn.microsoft.com/library/ms683194.aspx) function to obtain this information and prints it to the screen, representing a mapping to a logical processor with an asterisk e.g. ‘*’. Coreinfo is useful for gaining insight into the processor and cache topology of your system.

## Installation

You run Coreinfo by typing "coreinfo”.

## Using CoreInfo

For each resource it shows a map of the OS-visible processors
that correspond to the specified resources, with '*' representing the
applicable processors. For example, on a 4-core system, a line in the
cache output with a map of shared by cores 3 and 4.

**Usage: coreinfo [-c][-f][-g][-l][-n][-s][-m][-v]**

|Parameter  |Description  |
|---------|---------|
| **-c** | Dump information on cores. |
| **-f** | Dump core feature information. |
| **-g** | Dump information on groups. |
| **-l** | Dump information on caches. |
| **-n** | Dump information on NUMA nodes. |
| **-s** | Dump information on sockets. |
| **-m** | Dump NUMA access cost. |
| **-v** | Dump only virtualization-related features including support for second level address translation.
(requires administrative rights on Intel systems). |

All options except -v are selected by default.

**Coreinfo Output:**
```shell
Coreinfo v3.03 - Dump information on system CPU and memory topology
Copyright (C) 2008-2011 Mark Russinovich
Sysinternals - www.sysinternals.com

Intel(R) Xeon(R) CPU           W3520  @ 2.67GHz
Intel64 Family 6 Model 26 Stepping 5, GenuineIntel
EM64T           *       Supports 64-bit mode
VMX             -       Supports Intel hardware-assisted virtualization
SVM             -       Supports AMD hardware-assisted virtualization
HYPERVISOR      *       Hypervisor is present
HTT             *       Supports hyper-threading

SMX             -       Supports Intel trusted execution
SKINIT          -       Supports AMD SKINIT
EIST            *       Supports Enhanced Intel Speedstep

NX              *       Supports no-execute page protection
PAGE1GB         -       Supports 1GB large pages
PAE             *       Supports &gt; 32-bit physical addresses
PAT             *       Supports Page Attribute Table
PSE             *       Supports 4-MB pages
PSE36           *       Supports &gt; 32-bit address 4-MB pages
PGE             *       Supports global bit in page tables
SS              *       Supports bus snooping for cache operations
VME             *       Supports Virtual-8086 mode

FPU             *       Implements i387 FP instructions
MMX             *       Supports MMX instruction set
MMXEXT          -       Implements AMD MMX extensions
3DNOW           -       Supports 3DNow! instructions
3DNOWEXT        -       Supports 3DNow! extension instructions
SSE             *       Supports Streaming SIMD Extensions
SSE2            *       Supports Streaming SIMD Extensions 2
SSE3            *       Supports Streaming SIMD Extensions 3
SSSE3           *       Supports Supplemental SIMD Extensions 3
SSE4.1          *       Supports Streaming SIMD Extensions 4.1
SSE4.2          *       Supports Streaming SIMD Extensions 4.2

AES             -       Supports AES extensions
AVX             -       Supports AVX intruction extensions
FMA             -       Supports FMA extensions using YMM state
MSR             *       Implements RDMSR/WRMSR instructions
MTTR            *       Supports Mmeory Type Range Registers
XSAVE           -       Supports XSAVE/XRSTOR instructions
OSXSAVE         -       Supports XSETBV/XGETBV instructions

CMOV            *       Supports CMOVcc instruction
CLFSH           *       Supports CLFLUSH instruction
CX8             *       Supports compare and exchange 8-byte instructions
CX16            *       Supports CMPXCHG16B instruction
DCA             -       Supports prefetch from memory-mapped device
F16C            -       Supports half-precision instruction
FXSR            *       Supports FXSAVE/FXSTOR instructions
FFXSR           -       Supports optimized FXSAVE/FSRSTOR instruction
MONITOR         -       Supports MONITOR and MWAIT instructions
MOVBE           -       Supports MOVBE instruction
PCLULDQ         -       Supports PCLMULDQ instruction
POPCNT          *       Supports POPCNT instruction
SEP             *       Supports fast system call instructions

DE              *       Supports I/O breakpoints including CR4.DE
DTES64          -       Can write history of 64-bit branch addresses
DS              -       Implements memory-resident debug buffer
DS-CPL          -       Supports Debug Store feature with CPL
PCID            -       Supports PCIDs and settable CR4.PCIDE
PDCM            -       Supports Performance Capabilities MSR
RDTSCP          *       Supports RDTSCP instruction
TSC             *       Supports RDTSC instruction
TSC-DEADLINE    -       Local APIC supports one-shot deadline timer
xTPR            *       Supports disabling task priority messages

ACPI            *       Implements MSR for power management
TM              *       Implements thermal monitor circuitry
TM2             *       Implements Thermal Monitor 2 control
APIC            *       Implements software-accessible local APIC
x2APIC          -       Supports x2APIC

CNXT-ID         -       L1 data cache mode adaptive or BIOS

MCE             *       Supports Machine Check, INT18 and CR4.MCE
MCA             *       Implements Machine Check Architecture
PBE             *       Supports use of FERR#/PBE# pin

PSN             -       Implements 96-bit processor serial number

Logical to Physical Processor Map:
*---  Physical Processor 0
-*--  Physical Processor 1
--*-  Physical Processor 2
---*  Physical Processor 3

Logical Processor to Socket Map:
****  Socket 0

Logical Processor to NUMA Node Map:
****  NUMA Node 0

Logical Processor to Cache Map:
*---  Data Cache          0, Level 1,   32 KB, Assoc   8, LineSize  64
*---  Instruction Cache   0, Level 1,   32 KB, Assoc   4, LineSize  64
*---  Unified Cache       0, Level 2,  256 KB, Assoc   8, LineSize  64
-*--  Data Cache          1, Level 1,   32 KB, Assoc   8, LineSize  64
-*--  Instruction Cache   1, Level 1,   32 KB, Assoc   4, LineSize  64
-*--  Unified Cache       1, Level 2,  256 KB, Assoc   8, LineSize  64
--*-  Data Cache          2, Level 1,   32 KB, Assoc   8, LineSize  64
--*-  Instruction Cache   2, Level 1,   32 KB, Assoc   4, LineSize  64
--*-  Unified Cache       2, Level 2,  256 KB, Assoc   8, LineSize  64
---*  Data Cache          3, Level 1,   32 KB, Assoc   8, LineSize  64
---*  Instruction Cache   3, Level 1,   32 KB, Assoc   4, LineSize  64
---*  Unified Cache       3, Level 2,  256 KB, Assoc   8, LineSize  64
****  Unified Cache       4, Level 3,    8 MB, Assoc  16, LineSize  64

Logical Processor to Group Map:
****  Group 0
```

[![Download](/media/landing/sysinternals/Download_sm.png)](https://download.sysinternals.com/files/Coreinfo.zip) [**Download Coreinfo**](https://download.sysinternals.com/files/Coreinfo.zip) **(367 KB)**
