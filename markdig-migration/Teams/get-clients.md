---
title: Get clients for Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/27/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara; vichau
localization_priority: Priority
description: Learn how to use the various clients available for Microsoft Teams which include web, desktop (Windows and Mac), and mobile (Android, iOS, and Windows Phone).
ms.custom:
- NewAdminCenter_Update
appliesto: 
- Microsoft Teams
---

Get clients for Microsoft Teams 
===========================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Microsoft Teams has clients available for web, desktop (Windows and Mac), and mobile (Android, iOS, and Windows Phone). These clients all require an active internet connection and do not support an offline mode.

Web client 
----------

The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers. The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser. The browser must be configured to allow third-party cookies. 

[!INCLUDE [browser-support](includes/browser-support.md)]

The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753) and if an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app. and 
Desktop client
--------------

The Microsoft Teams desktop client is a standalone application and currently not part of Office Pro Plus. Teams is available for both Windows (7+), both 32-bit and 64-bit versions, and MacOS (10.10+). On Windows, Teams requires .NET framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it. 

The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.

Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).

IT admins can choose their preferred method to distribute the installation files to machines in their organization such as System Center Configuration Manager (Windows) or Casper Suite (MacOS). To get the MSI Package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).

> [!NOTE]
> Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.


#### Windows

The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.

> [!NOTE]
> The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.

The Windows client is deployed to the AppData folder located in the user’s profile. Deploying to the user’s local profile allows the client to be installed without requiring elevated rights. The Windows client is installed in the following locations:

-   %appdata%\\local\\Microsoft\\Teams

-   %appdata%\\roaming\\Microsoft\\Teams

When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication. Users may be instructed to ignore this message because the call will work, even when the warning is dismissed.

![Screenshot of a Windows Security Alert dialog.](media/Get_clients_for_Microsoft_Teams_image3.png)


> [!NOTE]
> Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”. Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.

#### Mac

Microsoft also provides a DMG installation file for Mac OSX computers. Administrative access is required to install the Mac client. The Mac OSX client is installed to the /Applications folder.


Mobile clients
--------------

The Microsoft Teams mobile apps are available for Android, iOS, and Windows Phones, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls. For mobile apps, go to the relevant mobile store for Google Play, Apple App Store, and Microsoft Store.

Supported mobile platforms for Microsoft Teams mobile apps are the following:

-   **Android**: 4.4 or later

-   **iOS**: 10.0 or later

-   **Windows Phone**: Windows 10 Mobile

> [!NOTE]
> The mobile version must be available to the public in order for Teams to work as expected.

Mobile apps are distributed and updated through the respective mobile platform’s app store only, and are not available to be distributed through MDM (mobile device management) solutions or side-loaded.


| | | |
|---------|---------|---------|
|![Decision Point icon.](media/Get_clients_for_Microsoft_Teams_image4.png)      |Decision Point         |Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?         |
|![Next Steps icon.](media/Get_clients_for_Microsoft_Teams_image5.png)     |Next Steps         |If your organization restricts software installation, make sure that process is compatible with Microsoft Teams. Note: Admin rights are not required for PC client installation but are required for installation on a Mac.         |


  <span id="_Hlk477176062" class="anchor"></span>  Decision Point   Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?

Client update management
------------------------

Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required. If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will kick off.

Client-side configurations
---------------------------

Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.

Notification settings
----------------------------

There are currently no options available for IT administrators to configure client-side notification settings. All notification options are set by the user. The figure below outlines the default client settings.

![Screenshot of Notifications settings.](media/Get_clients_for_Microsoft_Teams_image6.png)
