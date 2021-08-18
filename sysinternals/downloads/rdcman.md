---
TOCTitle: Remote Desktop Connection Manager
title: Remote Desktop Connection Manager
description: Manage multiple remote desktop connections.
ms.date: 08/18/2021
---

# Remote Desktop Connection Manager v2.83

**By Julian Burger**

Published: August 18, 2021

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/RDCMan.zip) [**Download Remote Desktop Connection Manager**](https://download.sysinternals.com/files/RDCMan.zip) **(494 KB)**  
**Run now** from [Sysinternals Live](https://live.sysinternals.com/RDCMan.exe).

## Introduction

RDCMan manages multiple remote desktop connections. It is useful for managing server labs where you need regular access to each machine such as automated checkin systems and data centers.

Servers are organized into named groups. You can connect or disconnect to all servers in a group with a single command. You can view all the servers in a group as a set of thumbnails, showing live action in each session. Servers can inherit their logon settings from a parent group or a credential store. Thus when you change your lab account password, you only need to change the password stored by RDCMan in one place. Passwords are stored securely by encrypting with either CryptProtectData using the (locally) logged on user's authority or an X509 certificate.

User with OS versions prior to Win7/Vista will need to get version 6 of the Terminal Services Client. You can obtain this from the Microsoft Download Center: XP; Win2003

Upgrade note: RDG files with this version of RDCMan are not compatible with older program versions. Any legacy RDG file opened and saved with this version will be backed up as filename.old

---

## The Display

The Remote Desktop Connection Manager display consists of the menu, a tree with groups of servers, a splitter bar, and a client area.

### The Menu

There are several top-level menus in RDCMan:

- **File** - load, save, and close RDCMan file groups
- **Edit** - add, remove, and edit the properties of servers and groups.
- **Session** - connect, disconnect and log off sessions
- **View** - options to control the visibility of the server tree, virtual groups and size of the client area
- **Remote Desktops** - allows access to the groups and servers in a hierarchical fashion, similar to the server tree; primarily useful when the Server Tree is hidden
- **Tools** - change application properties
- **Help** - learn about RDCMan (you probably already found this)

### The Tree

Most work, such as adding, removing, and editing servers and groups, can be accomplished via right-clicking on a tree node. Servers and groups can be moved using drag-and-drop.

Keyboard shortcuts:

- **Enter**: Connect to selected server.
- **Shift+Enter**: Connect to the selected server using the Connect As feature.
- **Delete**: Remove selected server or group.
- **Shift+Delete**: Remove selected server or group without question.
- **Alt+Enter**: Open properties dialog for selected server or group.
- **Tab**: If a connected server is selected, give it focus.

Use the **[View.Server tree location]** menu option to locate the tree at the left or right edge of the window.

The server tree can be docked, auto-hidden, or always hidden via the **[View.Server tree visibility]** menu option. When the server tree is not displayed, servers can still be accessed through the Remote Desktops menu. When the tree is auto-hidden, the splitter bar remains visible at the left side of the window. Hovering over it will bring the server tree back into view.

### The Client Area

The client area display depends on the node selected in the tree. If a server is selected, the client area shows the remote desktop client for that server. If a group is selected, the client area shows a thumbnail of the servers within that group. The size of the client area can be specified via the View menu, as well as resizing the RDCMan window. Use **[View.Lock window size]** to prevent the window from being resized by dragging the frame.

**Caution: Connected servers can receive focus from keyboard navigation of the thumbnail view. It is not always obvious which server has focus, so be careful. There is a setting to control this: [Display Settings.Allow thumbnail session interaction].**

### Full Screen Mode

To work with a server in full screen mode, select the server to give it focus and press **Ctrl+Alt+Break** (this key is configurable, see Shortcut Keys.) To leave full screen mode, press **Ctrl+Alt+Break** again or use the minimize/restore buttons in the connection title bar. Multiple monitors can be spanned if enabled by the monitor spanning option.

### Shortcut Keys

You can find the full list of Terminal Services shortcut keys here. Some of these can be configured from the Hot Keys tab.

## Files

The top-level unit of organization in RDCMan is a remote desktop file group. File groups are collections of groups and/or servers that are stored in a single physical file. Servers can't live outside of a group and groups can't live outside of a file.

A file has all the characteristics of a server group other than being able to change its parent.

## Groups

A group contains a list of servers and configuration information such as logon credentials. Configuration settings can be inherited from another group or the application defaults. Groups can be nested but are homogenous: a group may either contain groups or servers, but not both. All the servers in a group can be connected or disconnected at once.

When a group is selected in the tree view, the servers underneath it are displayed in a thumbnail view. The thumbnails can show the actual server windows or simply the connection status. Global thumbnail view properties can be adjusted via the **[Tools.Options.Client Area]** tab while group/server-specific settings are in Display Settings.

### Smart Groups

Smart groups are populated dynamically based on a set of rules. All ancestors of sibiling groups of the smart group are eligible for inclusion.

### The Connected Virtual Group

When a server is in the connected state, it is automatically added the to Connected virtual group. Servers cannot be explicitly added or removed from the Connected group.

The Connected group can be toggled on/off via the View menu.

### The Reconnect Virtual Group

There are sometimes situations where a server disconnects and will be intentionally offline for an unspecified length of time, e.g. when rebooting after an OS update. When this is the case, drag the server in question to the Reconnect group. RDCMan will continually attempt to connect to the server until it is successful.

The Reconnect group can be toggled on/off via the View menu.

### The Favorites Virtual Group

The Favorites virtual group is a flat file of your favorite servers. You can add any server from the server tree. This is helpful when you have many servers in the tree and often work with a handful of servers from different groups.

The Favorites group can be toggled on/off via the View menu.

### The Connect To Virtual Group

The Connect To Virtual Group contains the servers that are not members of user-created groups. See Ad Hoc Connections for details.

The Connect To group is visible while ad hoc connections exist and disappears when there are none.

### The Recent Virtual Group

The Recent Virtual Group contains the servers that have been recently accessed.

The Recent group can be toggled on/off via the View menu.

## Servers

A server has a server name (the computer's network name or IP address), an optional display name, and logon information. The logon information may be inherited from another group.

### Adding Servers Manually

Servers names following a pattern can be bulk added to a group. There are two pattern classes:

- Iteration - `{a,b,c}` iterates over the comma-delimeted contents.
- Range - `[1-5]` iterates the numerical range. Prefix the lower bound with `0`'s to specify the minimum width.

Examples:

- `server1{a,b,c}`: Adds `server1a`, `server1b`, `server1c`
- `server[001-15]`: Adds `server001`, `server002`, ..., `server015`
- `{dca,dcb}rack[1-5]sql[1-2]`: Adds `dcarack1sql1`, `dcarack1sql2`, `dcarack2sql1`, ..., `dcarack5sql2`, `dcbrack1sql1`, ... `dcbrack5sql2`

### Importing Servers from a Text File

Servers can be imported into a group from a text file. The file format is simply one server name per line:

```txt
Server1
SecondServer
YANS
```

Server names may also be explicitly specified in the dialog.

All servers are imported into the same group with the same preferences. If a server is imported that has the same name as an existing server, the existing server's preferences are updated to the new ones.

### Ad Hoc Connections

Ad hoc server connections can be created via the [Session.Connect to] feature. These servers will be added to the Connect To Virtual Group. From there they can be converted into real servers by moving them to a user-created group. Servers remaining in the Connect To group are not persisted when RDCMan exits.

### Windows Azure

In the **[Connection Settings]** tab, enter the role name and role instance name into *Load balance config* [as described here](/azure/cloud-services/cloud-services-role-enable-remote-desktop-powershell) e.g.
`Cookie: mstshash=MyServiceWebRole#MyServiceWebRole_IN_0#Microsoft.WindowsAzure.Plugins.RemoteAccess.Rdp`

### Session Actions

While in a session, the focus can be released to another session or the server tree.

- Focus release left (default value is **Ctrl+Alt+Left**) : This selects the previously selected session.
- Focus release right (default value is **Ctrl+Alt+Right**): This brings up a dialog to choose where to focus. There will be buttons for up to the of the most-recently used session as well as a button for the server tree and one to minimize RDCMan.

Certain key combinations and Windows actions can be tricky to perform over the remote session--particularly when RDCMan itself is started within a remote session--e.g. **Ctrl+Alt+Del**. These are available from the **[Session.Send keys]** and **[Session.Remote actions]** menu items.

## Global Options

The **[Tool.Options]** menu item brings up the Options Dialog. Global settings, e.g. the client area size, are modifiable from here. Most server-related options, e.g. hot keys and those on the experience page, will not take effect until the next time that server is connected.

### General

*Hide main menu until ALT pressed*  
The main menu can be hidden until the ALT key is pressed or the window caption area is left clicked.

*Auto save interval*  
You can have RDCMan periodically save the open files automatically. Check the auto-save check box and specify the interval (in minutes) for saving. An interval of 0 will not save periodically but will suppress the save prompt when exiting RDCMan.

*Prompt to reconnect connected servers on startup*  
RDCMan remembers which servers where connected when the program was exited. On the next run you are prompted to choose which servers to reconnect. Disabling this option automatically reconnects all previously connected servers. See Command Line for command line switches that affect this behavior.

*Default group settings*  
Clicking this button opens a dialog to configure the settings for the base level of the inheritance hierarchy. E.g. if a File group is set to inherit from its parent, this is where the settings come from.

### Tree

*Click to select gives focus to remote client*  
When selecting a node in the server tree control with a mouse click, the default behavior is to keep focus on the tree control. There is an option to change this to focus on the selected server.

*Dim nodes when the tree control is inactive*  
RDCMan can dim the tree control when it is inactive. This presents a more obvious visual distinction of keyboard focus.

### Client Area

*Client Area Size*  
This option resizes the client area of the RDCMan window. The options are also available from the **[View.Client size]** menu.

*Thumbnail Unit Size*  
The thumbnail unit size can be specified as an absolute pixel size or a relative percentage of the client panel width.

### Hot Keys

Many of the remote desktop hot keys are configurable. There is a limited mapping, however. For example if the default key is ALT-something, the replacement must also be ALT-something. To change a hot key, navigate to the text box for the hot key and press the new "something" key.

### Experience

Depending on the bandwidth available from your machine, you will want to limit Windows UI features to improve performance. The connection speed drop down can be used to set all options together, or they can be individually customized. The features are: desktop backgrounds, showing full window contents when dragging, menu and window animation, and windows themes.

### Full Screen

*Show full screen connection bar*  
*Auto-hide connection bar*  
When a server is displayed in full-screen mode, the remote desktop activeX control provides a UI connection bar at the top of the window. This bar can be toggled on and off. When it is on, you can choose to have it pinned or auto-hidden.

*Full screen window is always on top*  
When RDCMan is displaying a server in full-screen mode, you can choose to have the window always displayed as the top-most window.

*Use multiple monitors when necessary*  
By default, a full screen session is restricted to the monitor containing the server window. You can enable multiple monitor spanning in the full screen options. If the remote desktop is larger than window's monitor, it will span as many monitors as needed to fit the remote session. Note that only rectangular areas are used, so if you have two monitors with differing vertical resolutions, the shorter of the two is used. Also, there is a hard limit of 4096x2048 for the remote desktop control.

## Local Options

Groups and Servers have a number of tabbed property pages with various customization options. Many of these pages are common to groups and servers. When the "Inherit from parent" check box is checked, the settings that follow are inherited from the parent container. Most server-related changes, e.g. remote desktop size, will not take effect until the next time that server is connected.

### File Settings

This page only appears for the properties of a file. It contains options for the file's group name, shows the full path to the file (which can't be edited), and has a comment field.

### Group Settings

This page only appears for the properties of a group. It contains options for the group name, parent nesting, and a comment.

### Server Settings

This page only appears for the properties of a server. It contains options for the server name, its display name, parent nesting, and a comment. SCVMM virtual machines can be connected to via RDP into the host using the VM console connect option. Use the PowerShell command:

```powershell
get-vm | ft ElementName,Name,Id
```

to determine the id corresponding to the VM.

### Logon Credentials

The Logon Credentials property page contains options pertaining to remote login. The user name, password, and domain are set on this page. The domain and user name can be specified together by using the domain\user format. When logging in to a machine "domain" rather than a Windows domain, you can specify [server] or [display]. This former will be substituted with the server name, the latter with the display name, at logon time. It is useful when you have a group of machines which require logging in as administrator. The Logon Settings entered in the properties pages are used by default for new connections. If you want to temporarily customize these settings for a new connection, connect using the Connect As menu item.

### Gateway Settings

The Gateway Settings property page has options for using a TS Gateway Server. The Gateway name, authentication method, and local address bypass options are on this page. Users of operating systems starting from Vista SP1 and Longhorn server will have additional options regarding logon credentials:

Explicit entry of Gateway user name and password
Ability to share the Gateway credentials with the remote server

### Connection Settings

The Connection Settings tab includes settings to customize how a session is connected and what happens upon logon.

You can specify whether the console session should be connected to as well as the remote desktop connection port.

There are also settings that allow you to run a program upon connection. Enter the program name and, optionally, the working directory for that program. Note that these only have an effect if you are connecting to the console session for the first time. That is, reconnecting to a session or connecting to a session other than the console session will not run the program. (At least, this is how Terminal Services appears to work based on empirical observation.)

### Remote Desktop Settings

The size of the remote desktop is specified on this page. This is the logical desktop size, not the physical client view of it. For example, if the remote desktop size is 1280 x 1024 and client size is 1024 x 768, you would see a 1024 x 768 view of the remote desktop with scroll bars. If the client size were 1600 x 1200, the entire remote desktop would be visible, offset by a gray border.

Specifying "Same as client area" will make the remote desktop the same size as the RDCMan client panel, i.e. the RDCMan window client area excluding the server tree. Specifying "Full screen" will make the remote desktop the same size as the screen that the server is viewed on. Note that the remote desktop size is determined upon connecting to a server. Changing this setting for a connected server will have no effect.

The maximum size of the remote desktop is determined by the version of the remote desktop activeX control. Version 5 (pre-Vista) had a maximum of 1600 x 1200; Version 6 (Vista) has a maximum of 4096 x 2048. This limit is enforced at connection time, not during data entry. This is in case the same RDCMan file is shared by multiple computers.

### Local Resources

Various resources of the remote server may be delivered to the client. The remote computer sound can be played locally, played remotely, or disabled entirely. Windows key combinations (for example, those involving the actual Windows key as well as other specials like Alt+Tab) can be applied always to the client machine, always to the remote machine, or to the client when windowed and the remote machine when in full screen mode. Client drive, port, printer, smart card, and clipboard resources can be automatically shared to the remote machine.

### Security Settings

You can specify whether authentication of the remote machine is required before a connection is established.

### Display Settings

Thumbnail display settings are customizable from this page.

The first option is: thumbnail scale. This specifies how many thumbnail units to allocate to the display of a given server. All servers default to a scale of 1. You can change this to increase the display of important servers. For example, a server could be scaled by 3 or 5 making the remote session quite usable in the thumbnail display while still permitting a view of many other servers. This is the only option for servers.

There are three additional options for groups: preview session in thumbnail, allow thumbnail session interaction, and show disconnected thumbnails. The first whether or not the thumbnail view shows the actual live connection, continually updated. The second, dependent on the first, specifies whether the thumbnail session is usable. The final option controls whether disconnected servers appear in the thumbnail view.

### Encryption Settings

RDCMan can encrypt the passwords stored in files either with the local user's credentials via CryptProtectData or an X509 certificate. The Encryption Settings tab is available in the Default Group Settings and File Settings dialogs.

Personal certificates of the current user which have a private key are available for encryption. You can create such a certificate in the following manner:

```powershell
makecert -sky exchange -r -pe -a sha1 -len 2048 -ss my -n "CN=MyRDCManCert"
```

This will create a certificate called "`MyRDCManCert`" in the Personal Certificates store of the current user. To install this cert on another computer, you must export it with the private key.

### Profile Management

Credential profiles can be added, edited, and removed from this tab.

## List Remote Sessions

RDCMan has limited support for managing remote sessions other than those connected from it. The **[Session.List Sessions]** menu item invokes the feature.

Note that the account running RDCMan must have Query Information permissions on the remote server to list the sessions. Furthermore, the remote session must be directly reachable rather than via a gateway server. Disconnect and Logoff permissions must be granted to perform those operations. See msdn for more information on remote desktop permissions.

## Command Line

By default, RDCMan will open the files that were loaded at the time of the last program shutdown. You can override this by specifying a file (or files) explicitly on the RDCMan command line. Additionally, the following switches are accepted:

- `/reset` - reset the persisted application preferences such as window location and size.
- `/noopen` - do not open the previously loaded files, starting with an empty environment.
- `/c server1[,server2...]` - connect specified servers
- `/reconnect` - connect all servers that were connected at shutdown without prompting
- `/noconnect` - do not prompt to connect servers that were connected at shutdown

## Find Servers

There is a dialog for finding servers accessed via **Ctrl+F** or the **Edit.Find** (servers) command. All servers matching a regular expression pattern are displayed in the dialog and can be acted on via a context menu. The pattern is matched against the full name (`group\server`).

## Credential Profiles

Credential profiles store logon credentials globally to RDCMan or in a file. This allows for using the same stored credentials across groups that do not have a common ancestor. One use scenario is to store credentials used for logging into servers and gateways in a single place. When a password changes, it can be edited once. Another scenario is when sharing RDG files across a group. Instead of storing passwords in the file (which would have issues due to the user-specific nature of the encryption RDCMan uses), a profile is created such as "Me" which each user defines in their Global store.

You can update the settings for a credential profile in two ways. The first is to edit from a credentials dialog and then save the exact same profile name/domain to the same store (file or global). That will ask if you want to update. The other way is to go to the group properties for the credential store (again, file or global) and use the Profile Management tab.

File scope credential profile passwords are encrypted according to the containing file's Encryption Settings. Global credential profiles use the Default Group Settings.

## Policies

RDCMan retrieves policy information from the `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\RDCMan` registry key.

- `DisableLogOff` - Create this `DWORD` value as non-zero to disable the log off command throughout RDCMan.

---

## FAQ

- *How do I use smartcard credentials to logon?*

    Enable "Redirect smart cards" in the Local Resources tab.

- *I get an error connecting through a gateway such as Error 50331656. Why?*

    Gateways must be specified as FQDN.

- *How do I make auto-logon work?*

    You must enable the Group Policy controlling it. Use the MMC "Group Policy" Snap-in and navigate to "Local Computer Policy/Computer Configuration/Administrative Templates/Windows Components/Terminal Services/Encryption and Security". Double-click "Always prompt client for password upon connection" and click the "Disabled" box.

- *How do I resize the remote desktop while a server is connected?*

    You can't. To resize you must disconnect and reconnect (use the Reconnect feature to do this in one step).

---

## Download

[![Download](media/shared/Download_sm.png)](https://download.sysinternals.com/files/RDCMan.zip) [**Download Remote Desktop Connection Manager**](https://download.sysinternals.com/files/RDCMan.zip) **(494 KB)**  
**Run now** from [Sysinternals Live](https://live.sysinternals.com/RDCMan.exe).

**Runs on:**

- Client: Windows 8.1 and higher.
- Server: Windows Server 2012 and higher.
