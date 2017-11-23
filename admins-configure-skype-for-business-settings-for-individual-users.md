---
title: Admins Configure Skype for Business settings for individual users
ms.author: TONYSMIT
author: TONYSMIT
manager: scotv
ms.date: 11/2/2017
ms.audience: Admin
ms.topic: How To
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: Learn how to change the Skype for Business settings for individual users such as Audio and video conferencing, recording of calls and meetings. 
ms.collection: Adm_Skype4B_Online
ms.technology:
- Microsoft Teams
- Office 365 Enterprise
- Office 365 Enterprise admin
- Office 365 Midsize Business admin
- Office 365 Small Business admin
- Skype for Business
- Skype for Business admin center
- Skype for Business Online
- Skype for Business Online admin center
ms.set-free-tag:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
---



# Admins: Configure Skype for Business settings for individual users

This article explains how admins configure Skype for Business for a small number of users. To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.
  
    
    


To allow (or block) everyone in your business to communicate with external people, see:
  
    
    


-  [Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md) : You can let your organization use advanced Skype Empresarial features (share desktops, look for who's online) to communicate with people in a specific trusted (federated) business. Also explains how to block communication with specific domains.
    
  
-  [Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md) . You can let your organization use Skype Empresarial to search for and IM people who use Skype, the free app.
    
  

## Configure general settings for one user
<a name="__toc325019204"> </a>

You must have  [Acerca de los roles de administrador de Office 365](http://technet.microsoft.com/library/da585eea-f576-4f55-a1e0-87090b6aaa9d%28Office.14%29.aspx) to perform these steps.
  
    
    

1. Sign in to Office 365 with your work or school account.
    
  
2. Choose **Admin centers** > **Skype for Business**.
    
  
3. Choose **Users**.
    
    ![In the Skype for Business admin center, choose Users.](images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
    
    

    
  
4. Choose which users you want to edit.
    
  
5. In the right panel, choose **Edit**.
    
    ![Choose the edit icon.](images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
    
    

    
  
6. On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.
    

|**Option**|**Details**|
|:-----|:-----|
|Audio and HD video  <br/> |Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meeetings (none).  <br/> |
|Record conversations and meetings  <br/> |Choose what this person is allowed to record.  <br/> This option is not available with Skype Empresarial Basic.  <br/> |
|For compliance, turn off non-archived features  <br/> | Choose this option if you're legally required to preserve electronically stored information. <br/>  Selecting this option turns off features that aren't captured when you have an [In-place hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in in the Exchange admin center. It turns off the following features: <br/>  File transfer using instant messaging <br/>  Shared OneNote pages <br/>  PowerPoint annotations <br/> |
   
To configure these settings in bulk, use PowerShell. See  [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).
  
    
    

## Block external communications
<a name="__toc325019206"> </a>

After you  [Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.
  
    
    

1. Choose **Users**, select the users whose settings you want to disable, and then choose **Edit**![Editar](images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
  
2. Choose **External communications**, and then clear the options as appropriate:
    
  - **External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype Empresarial users in federated domains.
    
  
  - **External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.
    
  
3. Click **Save**.
    
  
To configure these settings in bulk, use PowerShell. See  [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).
  
    
    

## Edit audio conferencing settings for one user
<a name="__toc314837483"> </a>


1. Click **Users** > *UserName >* **Edit**.
    
  
2. Select your audio conferencing provider, type or change the requested information, and then click **Save**.
    

|**Audio conferencing setting**|**Description**|
|:-----|:-----|
|Provider  <br/> |Choose your audio conferencing provider from the list.  <br/> |
|**Toll number** (required) <br/> |For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype Empresarial and Microsoft Teams meeting requests.  <br/> |
|**Toll-free number** <br/> |For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype Empresarial and Microsoft Teams meeting requests.  <br/> |
|**Passcode** (required) <br/> |The participant passcode, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, this won't be required.  <br/> |
   
To configure these settings in bulk, use PowerShell. See  [Establecer los números de teléfono de conferencias de Audio para organizadores que se incluyen en invitaciones](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
    
    

## 
<a name="__toc314837483"> </a>


||
|:-----|
|![Icono pequeño de LinkedIn Learning](images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **¿Usa Office 365 por primera vez?**         Descubra cursos en vídeo gratuitos para **administradores de Office 365 y profesionales de TI**, ofrecidos por LinkedIn Learning. |
   

## Related Topics
<a name="__toc314837483"> </a>

 [Configurar Skype Empresarial Online](set-up-skype-for-business-online.md) [Skype para Business y Microsoft Teams licencias de complemento](skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
    
    
