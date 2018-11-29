--- 
TOCTitle: Sysmon
title: Sysmon
description: Monitors and reports key system activity via the Windows event log.
ms:assetid: 'f49b1cb3-c689-469e-ade0-6fa98d72f9d6'
ms:mtpsurl: 'https://technet.microsoft.com/en-us/Dn798348(v=MSDN.10)'
ms.date: 05/22/2017
---

Sysmon v8.0
===========

**By Mark Russinovich and Thomas Garnier**

Published: July 5, 2018

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/Sysmon.zip) [**Download Sysmon**](https://download.sysinternals.com/files/Sysmon.zip) **(1.4 MB)**

## Introduction

*System Monitor* (*Sysmon*) is a Windows system service and device
driver that, once installed on a system, remains resident across system
reboots to monitor and log system activity to the Windows event log. It
provides detailed information about process creations, network
connections, and changes to file creation time. By collecting the events
it generates using [Windows Event
Collection](http://msdn.microsoft.com/en-us/library/windows/desktop/bb427443(v=vs.85).aspx)
or
[SIEM](http://en.wikipedia.org/wiki/security_information_and_event_management)
agents and subsequently analyzing them, you can identify malicious or
anomalous activity and understand how intruders and malware operate on
your network.

Note that *Sysmon* does not provide analysis of the events it generates,
nor does it attempt to protect or hide itself from attackers.

## Overview of Sysmon Capabilities

*Sysmon* includes the following capabilities:

-   Logs process creation with full command line for both current and
    parent processes.
-   Records the hash of process image files using SHA1 (the default),
    MD5, SHA256 or IMPHASH.
-   Multiple hashes can be used at the same time.
-   Includes a process GUID in process create events to allow for
    correlation of events even when Windows reuses process IDs.
-   Include a session GUID in each events to allow correlation of events
    on same logon session.
-   Logs loading of drivers or DLLs with their signatures and hashes.
-   Logs opens for raw read access of disks and volumes
-   Optionally logs network connections, including each connection’s
    source process, IP addresses, port numbers, hostnames and port
    names.
-   Detects changes in file creation time to understand when a file was
    really created. Modification of file create timestamps is a
    technique commonly used by malware to cover its tracks.
-   Automatically reload configuration if changed in the registry.
-   Rule filtering to include or exclude certain events dynamically.
-   Generates events from early in the boot process to capture activity
    made by even sophisticated kernel-mode malware.


## Screenshots

![EventViewer](/media/landing/sysinternals/event-screen-optimized.png "EventViewer")

 

## Usage

Uses Sysmon simple command-line options to install and uninstall it, as
well as to check and modify Sysmon’s configuration:

<strong>Sysinternals Sysmon v6.20 - System activity monitor  
Copyright (C) 2014-2017 Mark Russinovich and Thomas Garnier  
Sysinternals - www.sysinternals.com</strong>

Usage:

**Install:**    **Sysmon.exe -i &lt;configfile&gt;  
\[-h &lt;\[sha1|md5|sha256|imphash|\*\],...&gt;\] \[-n
\[&lt;process,...&gt;\]\]  
\[-l (&lt;process,...&gt;)\]**

**Configure:**  **Sysmon.exe -c &lt;configfile&gt;**  
              **\[--|\[-h &lt;\[sha1|md5|sha256|imphash|\*\],...&gt;\]
\[-n \[&lt;process,...&gt;\]\]  
               \[-l \[&lt;process,...&gt;\]\]\]**

**Uninstall:**  **Sysmon.exe -u**

 
|Parameter  |Description  |
|---------|---------|
|  **-c** |  Update configuration of an installed Sysmon driver or dump the current configuration if no other argument is provided. Optionally take a configuration file.|
|  **-d** |  Specify the name of the installed device driver image. Configuration entry: DriverName. The service image and service name will be the same.|
|  **-h** |  Specify the hash algorithms used for image identification (default is SHA1). It supports multiple algorithms at the same time. Configuration entry: HashAlgorithms.|
|  **-i** |  Install service and driver. Optionally take a configuration file.|
|  **-l** |  Log loading of modules. Optionally take a list of processes to track.|
|  **-m** |  Install the event manifest (done on service install as well).|
|  **-n** |  Log network connections. Optionally take a list of processes to track.|
|  **-r** |  Check for signature certificate revocation.  <br />Configuration entry: CheckRevocation.|
|  **-s** |  Print configuration schema definition.|
|  **-u** |  Uninstall service and driver.|

 

The service logs events immediately and the driver installs as a
boot-start driver to capture activity from early in the boot that the
service will write to the event log when it starts.

On Vista and higher, events are stored in "Applications and Services
Logs/Microsoft/Windows/Sysmon/Operational"  
On older systems, events are written to the System event log.

If you need more information on configuration files, use the '-? config'
command. More examples are available on the Sysinternals website.

Specify -accepteula to automatically accept the EULA on installation,
otherwise you will be interactively prompted to accept it.

Neither install nor uninstall requires a reboot.

## Examples

Install with default settings (process images hashed with sha1 and no
network monitoring)  
**sysmon -accepteula  –i**

Install with md5 and sha256 hashing of process created and monitoring
network connections  
**sysmon -accepteula –i –h md5,sha256 –n**

Install Sysmon with a configuration file (as described below)

**sysmon –accepteula –i c:\\windows\\config.xml**

Uninstall  
**sysmon –u**

Dump the current configuration  
**sysmon –c**

Change the configuration to use all hashes, no network monitoring and
monitoring of DLLs in Lsass  
**sysmon –c –h \* –l lsass.exe**

Change the configuration of sysmon with a configuration file (as
described below)

**sysmon –c c:\\windows\\config.xml**

Change the configuration to default settings  
**sysmon –c --**

Show the configuration schema:  
**sysmon -s**

## Events

On Vista and higher, events are stored in "Applications and Services
Logs/Microsoft/Windows/Sysmon/Operational", and on older systems events
are written to the System event log. Event timestamps are in UTC
standard time.

The following are examples of each event type that Sysmon generates.

### Event ID 1: Process creation

The process creation event provides extended information about a newly
created process. The full command line provides context on the process
execution. The ProcessGUID field is a unique value for this process
across a domain to make event correlation easier. The hash is a full
hash of the file with the algorithms in the HashType field.

### Event ID 2: A process changed a file creation time
The change file creation time event is registered when a file creation
time is explicitly modified by a process. This event helps tracking the
real creation time of a file. Attackers may change the file creation
time of a backdoor to make it look like it was installed with the
operating system. Note that many processes legitimately change the
creation time of a file; it does not necessarily indicate malicious
activity.

### Event ID 3: Network connection

The network connection event logs TCP/UDP connections on the machine. It
is disabled by default. Each connection is linked to a process through
the ProcessId and ProcessGUID fields. The event also contains the source
and destination host names IP addresses, port numbers and IPv6 status.

### Event ID 4: Sysmon service state changed

The service state change event reports the state of the Sysmon service
(started or stopped).

### Event ID 5: Process terminated

The process terminate event reports when a process terminates. It
provides the UtcTime, ProcessGuid and ProcessId of the process.

### Event ID 6: Driver loaded

The driver loaded events provides information about a driver being
loaded on the system. The configured hashes are provided as well as
signature information. The signature is created asynchronously for
performance reasons and indicates if the file was removed after loading.

### Event ID 7: Image loaded

The image loaded event logs when a module is loaded in a specific
process. This event is disabled by default and needs to be configured
with the –l option. It indicates the process in which the module is
loaded, hashes and signature information. The signature is created
asynchronously for performance reasons and indicates if the file was
removed after loading. This event should be configured carefully, as
monitoring all image load events will generate a large number of events.

### Event ID 8: CreateRemoteThread

The CreateRemoteThread event detects when a process creates a thread in
another process. This technique is used by malware to inject code and
hide in other processes. The event indicates the source and target
process. It gives information on the code that will be run in the new
thread: StartAddress, StartModule and StartFunction. Note that
StartModule and StartFunction fields are inferred, they might be empty
if the starting address is outside loaded modules or known exported
functions.

### Event ID 9: RawAccessRead

The RawAccessRead event detects when a process conducts reading
operations from the drive using the \\\\.\\ denotation. This technique
is often used by malware for data exfiltration of files that are locked
for reading, as well as to avoid file access auditing tools. The event
indicates the source process and target device.

### Event ID 10: ProcessAccess

The process accessed event reports when a process opens another process,
an operation that’s often followed by information queries or reading and
writing the address space of the target process. This enables detection
of hacking tools that read the memory contents of processes like Local
Security Authority (Lsass.exe) in order to steal credentials for use in
Pass-the-Hash attacks. Enabling it can generate significant amounts of
logging if there are diagnostic utilities active that repeatedly open
processes to query their state, so it generally should only be done so
with filters that remove expected accesses.

### Event ID 11: FileCreate

File create operations are logged when a file is created or overwritten.
This event is useful for monitoring autostart locations, like the
Startup folder, as well as temporary and download directories, which are
common places malware drops during initial infection.

### Event ID 12: RegistryEvent (Object create and delete)

Registry key and value create and delete operations map to this event
type, which can be useful for monitoring for changes to Registry
autostart locations, or specific malware registry modifications.

Sysmon uses abbreviated versions of Registry root key names, with the
following mappings:

 
|Key name  | Abbreviation  |
|---------|---------|
|  HKEY\_LOCAL\_MACHINEHKLM                     | HKEY |
|  HKEY\_USERS                                  | HKU |
|  HKEY\_LOCAL\_MACHINE\\System\\ControlSet00x  | HKLM\\System\\CurrentControlSet |
|  HKEY\_LOCAL\_MACHINE\\Classes                | HKCR |

### Event ID 13: RegistryEvent (Value Set)

This Registry event type identifies Registry value modifications. The
event records the value written for Registry values of type DWORD and
QWORD.

### Event ID 14: RegistryEvent (Key and Value Rename)

Registry key and value rename operations map to this event type,
recording the new name of the key or value that was renamed.

### Event ID 15: FileCreateStreamHash

This event logs when a named file stream is created, and it generates
events that log the hash of the contents of the file to which the stream
is assigned (the unnamed stream), as well as the contents of the named
stream. There are malware variants that drop their executables or
configuration settings via browser downloads, and this event is aimed at
capturing that based on the browser attaching a Zone.Identifier “mark of
the web” stream.

### Event ID 17: PipeEvent (Pipe Created)

This event generates when a named pipe is created. Malware often uses named 
pipes for interprocess communication. 

### Event ID 18: PipeEvent (Pipe Connected)

This event logs when a named pipe connection is made between a client and a 
server.

### Event ID 19: WmiEvent (WmiEventFilter activity detected)

When a WMI event filter is registered, which is a method used by malware to 
execute, this event logs the WMI namespace, filter name and filter expression. 

### Event ID 20: WmiEvent (WmiEventConsumer activity detected)

This event logs the registration of WMI consumers, recording the consumer name, 
log, and destination. 

### Event ID 21: WmiEvent (WmiEventConsumerToFilter activity detected)
When a consumer binds to a filter, this event logs the consumer name and filter path. 

### Event ID 255: Error

This event is generated when an error occurred within Sysmon. They can
happen if the system is under heavy load and certain tasked could not be
performed or a bug exists in the Sysmon service. You can report any bugs
on the Sysinternals forum or over Twitter
([@markrussinovich](https://twitter.com/markrussinovich)).

## Configuration files

Configuration files can be specified after the **-i** (installation) or
**-c** (installation) configuration switches. They make it easier to
deploy a preset configuration and to filter captured events.

A simple configuration xml file looks like this:

![Configuration file](/media/landing/sysinternals/sysmon_schema.png)

The configuration file contains a schemaversion attribute on the Sysmon
tag. This version is independent from the Sysmon binary version and
allows the parsing of older configuration files. You can get the current
schema version by using the “-? config” command line. Configuration
entries are directly under the Sysmon tag and filters are under the
EventFiltering tag.

Configuration Entries
---------------------

Configuration entries are similar to command line switches. Command line
switches have their configuration entry described in the Sysmon usage
output. Parameters are optional based on the tag. If a command line
switch also enables an event, it needs to be configured though its
filter tag. You can specify the -s switch to have Sysmon print the full
configuration schema, including event tags as well as the field names
and types for each event. For example, here’s the schema for the
RawAccessRead event type:

&lt;event name="SYSMON\_RAWACCESS\_READ" value="9" level="Informational"
template="RawAccessRead detected" rulename="RawAccessRead"
version="2"&gt; &lt;data name="UtcTime" inType="win:UnicodeString"
outType="xs:string" /&gt; &lt;data name="ProcessGuid" inType="win:GUID"
/&gt; &lt;data name="ProcessId" inType="win:UInt32" outType="win:PID"
/&gt; &lt;data name="Image" inType="win:UnicodeString"
outType="xs:string" /&gt; &lt;data name="Device"
inType="win:UnicodeString" outType="xs:string" /&gt; &lt;/event&gt;

Event filtering entries
-----------------------

Event filtering allows you to filter generated events. In many cases
events can be noisy and gathering everything is not possible. For
example, you might be interested in network connections only for a
certain process, but not all of them. You can filter the output on the
host reducing the data to collect.

Each event has its own filter tag under the EventFiltering node in a
configuration file:

 
|ID  |Tag  | Event |
|---------|---------|---------|
|  **1**    ProcessCreate         | Process Create |
|  **2**    FileCreateTime        | File creation time |
|  **3**    NetworkConnect        | Network connection detected |
|  **4**    n/a                   | Sysmon service state change (cannot be filtered) |
|  **5**    ProcessTerminate      | Process terminated |
|  **6**    DriverLoad            | Driver Loaded |
|  **7**    ImageLoad             | Image loaded |
|  **8**    CreateRemoteThread    | CreateRemoteThread detected |
|  **9**    RawAccessRead         | RawAccessRead detected |
|  **10**   ProcessAccess         | Process accessed |
|  **11**   FileCreate            | File created |
|  **12**   RegistryEvent         | Registry object added or deleted |
|  **13**   RegistryEvent         | Registry value set |
|  **14**   RegistryEvent         | Registry object renamed |
|  **15**   FileCreateStreamHash  | File stream created |
|  **16**   n/a                   | Sysmon configuration change (cannot be filtered) |
|  **17**   PipeEvent             | Named pipe created |
|  **18**   PipeEvent             | Named pipe connected |

 

You can also find these tags in the event viewer on the task name.

The onmatch filter is applied if events are matched. It can be changed
with the "onmatch" attribute for the filter tag. If the value is
‘include’, it means only matched events are included. If it is set to
‘exclude’, the event will be included except if a rule match. You can
specify both an include filter set and an exclude filter set for each
event ID, where exclude matches take precedence.

Each filter can include zero or more rules. Each tag under the filter
tag is a field name from the event. Rules that specify a condition for
the same field name behave as OR conditions, and ones that specify
different field name behave as AND conditions. Field rules can also use
conditions to match a value. The conditions are as follows (all are case
insensitive):

|  **Condition**   | **Description** |
|---------|---------|
|  **Is**          | Default, values are equals |
|  **is not**      | Values are different |
|  **Contains**    | The field contains this value |
|  **Excludes**    | The field does not contain this value |
|  **begin with**  | The field begins with this value |
|  **end with**    | The field ends with this value |
|  **less than**   | Lexicographical comparison is less than zero |
|  **more than**   | Lexicographical comparison is more than zero |
|  **Image**       | Match an image path (full path or only image name). For example: lsass.exe will match c:\\windows\\system32\\lsass.exe |
 

You can use a different condition by specifying it as an attribute. This
excludes network activity from processes with iexplore.exe in their
path:

&lt;NetworkConnect onmatch="exclude"&gt; &lt;Image
condition="contains"&gt;iexplore.exe&lt;/Image&gt;
&lt;/NetworkConnect&gt;

You can use both include and exclude rules for the same tag, where
exclude rules override include rules. Within a rule, filter conditions
on the same field have OR behavior, whereas conditions on different
fields have AND behavior. In the sample configuration shown earlier, the
networking filter uses both an include and exclude rule to capture
activity to port 80 and 443 by all processes except those that have
iexplore.exe in their name.

To have Sysmon report which rule match resulted in an event being logged, add names to rules:

&lt;NetworkConnect onmatch="exclude"&gt; &lt;Image
name="network iexplore" condition="contains"&gt;iexplore.exe&lt;/Image&gt;
&lt;/NetworkConnect&gt;

[![Download](/media/landing/sysinternals/download_sm.png)](https://download.sysinternals.com/files/Sysmon.zip) [**Download Sysmon**](https://download.sysinternals.com/files/Sysmon.zip) **(1.4 MB)**
  
**Runs on:**

-   Client: Windows 7 and higher.
-   Server: Windows Server 2008 R2 and higher.

