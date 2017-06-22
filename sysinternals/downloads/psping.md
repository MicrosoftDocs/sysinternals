--- 
TOCTitle: PsPing
Title: PsPing
ms:assetid: '80138356-ebe3-41cd-a14d-8aa7eae81c42'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/JJ729731(v=MSDN.10)'
ms.date: 06/29/2016
---

PsPing v2.1
============

**By Mark Russinovich**

Published: June 29, 2016

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**


## Introduction

PsPing implements Ping functionality, TCP ping, latency and bandwidth
measurement. Use the following command-line options to show the usage
for each test type:

## Installation

Copy *PsPing* onto your executable path. Typing "psping" displays its
usage syntax.  

## Using PsPing

*PsPing* implements Ping functionality, TCP ping, latency and bandwidth
measurement. Use the following command-line options to show the usage
for each test type:

**Usage: psping -? \[i|t|l|b\]**

 
|Parameter  |Description  |
|---------|---------|
|  **-? I** |  Usage for ICMP ping. |
|  **-? T** |  Usage for TCP ping. |
|  **-? L** |  Usage for latency test. |
|  **-? B** |  Usage for bandwidth test. | 

**ICMP ping usage:**  
**psping \[\[-6\]|\[-4\]\] \[-h \[buckets |
&lt;val1&gt;,&lt;val2&gt;,...\]\] \[-i &lt;interval&gt;\] \[-l
&lt;requestsize&gt;\[k|m\] \[-q\] \[-t|-n &lt;count&gt;\] \[-w
&lt;count&gt;\] &lt;destination&gt;**

 
|Parameter  |Description  |
|---------|---------|
|  **-h** |  Print histogram (default bucket count is 20).  |
|         |  If you specify a single argument, it's interpreted as a bucket count and the histogram will contain that number of buckets covering the entire time range of values. Specify a comma-separated list of times to create a custom histogram (e.g. "0.01,0.05,1,5,10").|
|  **-i** |  Interval in seconds. Specify 0 for fast ping.|
|  **-l** |  Request size. Append 'k' for kilobytes and 'm' for megabytes.|
|  **-n** |  Number of pings or append 's' to specify seconds e.g. '10s'.|
|  **-q** |  Don't output during pings.|
|  **-t** |  Ping until stopped with Ctrl+C and type Ctrl+Break for statistics.|
|  **-w** |  Warmup with the specified number of iterations (default is 1).|
|  **-4** |  Force using IPv4.|
|  **-6** |  Force using IPv6. |

For high-speed ping tests use -q and -i 0.

**TCP ping usage:**  
** psping \[\[-6\]|\[-4\]\] \[-h \[buckets |
&lt;val1&gt;,&lt;val2&gt;,...\]\] \[-i &lt;interval&gt;\] \[-l
&lt;requestsize&gt;\[k|m\] \[-q\] \[-t|-n &lt;count&gt;\] \[-w
&lt;count&gt;\] &lt;destination:destport&gt;**

|Parameter  |Description  |
|---------|---------|
|  **-h** |  Print histogram (default bucket count is 20).  |
|         |  If you specify a single argument, it's interpreted as a bucket count and the histogram will contain that number of buckets covering the entire time range of values. Specify a comma-separated list of times to create a custom histogram (e.g. "0.01,0.05,1,5,10").|
|  **-i** |  Interval in seconds. Specify 0 for fast ping.|
|  **-l** |  Request size. Append 'k' for kilobytes and 'm' for megabytes.|
|  **-n** |  Number of pings or append 's' to specify seconds e.g. '10s'.|
|  **-q** |  Don't output during pings.|
|  **-t** |  Ping until stopped with Ctrl+C and type Ctrl+Break for statistics.|
|  **-w** |  Warmup with the specified number of iterations (default is 1).|
|  **-4** |  Force using IPv4.|
|  **-6** |  Force using IPv6.|



For high-speed ping tests use -q and -i 0.

**TCP and UDP latency usage:**

**server: psping \[\[-6\]|\[-4\]\] \[-f\] &lt;-s source:sourceport&gt;**

**client: psping \[\[-6\]|\[-4\]\] \[-f\] \[-u\] \[-h \[buckets |
&lt;val1&gt;,&lt;val2&gt;,...\]\] \[-r\] &lt;-l requestsize&gt;\[k|m\]\]
&lt;-n count&gt; \[-w &lt;count&gt;\] &lt;destination:destport&gt;**

|Parameter  |Description  |
|---------|---------|
|  **-f** |  Open source firewall port during the run.|
|  **-u** |  UDP (default is TCP).|
|  **-h** |  Print histogram (default bucket count is 20).  |
|         |  If you specify a single argument, it's interpreted as a bucket count and the histogram will contain that number of buckets covering the entire time range of values. Specify a comma-separated list of times to create a custom histogram (e.g. "0.01,0.05,1,5,10").|
|  **-l** |  Request size. Append 'k' for kilobytes and 'm' for megabytes.|
|  **-n** |  Number of sends/receives. Append 's' to specify seconds e.g. '10s'|
|  **-r** |  Receive from the server instead of sending.|
|  **-w** |  Warmup with the specified number of iterations (default is 5).|
|  **-4** |  Force using IPv4.|
|  **-6** |  Force using IPv6.|
|  **-s** |  Server listening address and port.|

The server can serve both latency and bandwidth tests and remains active
until you terminate it with Control-C.

**TCP and UDP bandwidth usage:**

**server: psping \[\[-6\]|\[-4\]\] \[-f\] &lt;-s source:sourceport&gt;**

**client: psping \[\[-6\]|\[-4\]\] \[-f\] \[-u\] \[-h \[buckets |
&lt;val1&gt;,&lt;val2&gt;,...\]\] \[-r\] &lt;-l requestsize&gt;\[k|m\]\]
&lt;-n count&gt; \[-i &lt;outstanding&gt;\] \[-w &lt;count&gt;\]
&lt;destination:destport&gt;**

 
|Parameter  |Description  |
|---------|---------|
|  **-f** |  Open source firewall port during the run.|
|  **-u** |  UDP (default is TCP).|
|  **-b** |  Bandwidth test.|
|  **-h** |  Print histogram (default bucket count is 20).  |
|         |  If you specify a single argument, it's interpreted as a bucket count and the histogram will contain that number of buckets covering the entire time range of values. Specify a comma-separated list of times to create a custom histogram (e.g. "0.01,0.05,1,5,10").|
|  **-i** |  Number of outstanding I/Os (default is min of 16 and 2x CPU cores).|
|  **-l** |  Request size. Append 'k' for kilobytes and 'm' for megabytes.|
|  **-n** |  Number of sends/receives. Append 's' to specify seconds e.g. '10s'|
|  **-r** |  Receive from the server instead of sending.|
|  **-w** |  Warmup for the specified iterations (default is 2x CPU cores).|
|  **-4** |  Force using IPv4.|
|  **-6** |  Force using IPv6.|
|  **-s** |  Server listening address and port.|

The server can serve both latency and bandwidth tests and remains active
until you terminate it with Control-C.

## Examples

This command executes an ICMP ping test for 10 iterations with 3 warmup
iterations:  
**psping -n 10 -w 3 marklap**

To execute a TCP connect test, specify the port number. The following
command executes connect attempts against the target as quickly as
possible, only printing a summary when finished with the 100 iterations
and 1 warmup iteration:  
**psping -n 100 -i 0 -q marklap:80**

To configure a server for latency and bandwidth tests, simply specify
the -s option and the source address and port the server will bind to:  
**psping -s 192.168.2.2:5000**

A buffer size is required to perform a TCP latency test. This example
measures the round trip latency of sending an 8KB packet to the target
server, printing a histogram with 100 buckets when completed:  
**psping -l 8k -n 10000 -h 100 192.168.2.2:5000**

This command tests bandwidth to a PsPing server listening at the target
IP address for 10 seconds and produces a histogram with 100 buckets.
Note that the test must run for at least one second after warmup for a
histogram to generate. Simply add -u to have PsPing perform a UDP
bandwidth test.  
**psping -b -l 8k -n 10000 -h 100 192.168.2.2:5000**

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/PSTools.zip) [**Download PsTools**](https://download.sysinternals.com/files/PSTools.zip) **(2.7 MB)**