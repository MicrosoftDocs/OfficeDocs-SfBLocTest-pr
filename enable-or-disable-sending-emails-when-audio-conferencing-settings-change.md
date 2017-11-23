---
title: Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: How To
ms.service: OFFICE365
description: Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. 
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
- Strat_SB_PSTN
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
---


# Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la  [declinación de responsabilidades](26ea19d3-e420-4fc1-baa3-2692d17e5e1d.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo  [aquí](https://support.office.com/en-us/article/26ea19d3-e420-4fc1-baa3-2692d17e5e1d). 
  
    
    


Audioconferencia de forma predeterminada Enviar correo electrónico a los usuarios cuando están habilitados para conferencias de audio. Puede haber ocasiones aunque cuando desea reducir el número de mensajes de correo electrónico que se envían a Skype para usuarios de empresa y Teams de Microsoft y, en ese caso puede deshabilitar esta opción.
  
    
    


Si deshabilita el envío de correos electrónicos, todos los correos electrónicos de conferencia de Audio no se enviará a los usuarios incluidos mensajes de correo electrónico para cuando los usuarios están habilitados o deshabilitados para conferencias de audio, al restablece su PIN, cuando los cambios del número de teléfono, el identificador de conferencia y la conferencia de forma predeterminada.
  
    
    


Aquí tiene un ejemplo del correo electrónico que se envía a los usuarios cuando están habilitados para conferencias de Audio:
  
    
    


  
    
    
![Correo electrónico de conferencia de acceso telefónico](images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
    
    

  
    
    

  
    
    

## ¿Cuándo se envían correos electrónicos a los usuarios?


- Hay varios correos electrónicos que se envían a los usuarios de su organización después de que están habilitados para conferencias de audio:
    
  - Cuando se asigna una licencia de **Conferencias de Audio** en ellos.
    
  
  - Al restablecer manualmente PIN de conferencia de audio del usuario.
    
  
  - Al restablecer de forma manual el id. de conferencia del usuario.
    
  
  - Cuando se elimina la licencia de **Conferencias de Audio** de ellos.
    
  
  - Cuando se cambia el proveedor de conferencias de audio de un usuario de Microsoft a otro proveedor, o **Ninguno**.
    
  
  - Cuando se cambia el proveedor de conferencias de audio de un usuario a Microsoft.
    
  

## Habilitar o deshabilitar el correo electrónico se envíe a los usuarios

Puede usar el Centro de administración de Skype Empresarial o Windows PowerShell para habilitar o deshabilitar el envío de correos electrónicos a los usuarios.
  
    
    
 **Usar la Skype centro de administración de la empresa**
  
    
    

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
  
2. Vaya al **Centro de administración de Office 365** > **Skype Empresarial** y en el panel de navegación izquierdo, haga clic en **conferencias de Audio**.
    
  
3. En la página **Configuración del puente de Microsoft**, active o desactive **Enviar automáticamente los mensajes de correo electrónico a los usuarios si cualquiera de los cambios de configuración de conferencias de audio**.
    
  
4. Haga clic en **Guardar**.
    
    > [!TIP]
      > También puede enviar correo electrónico al usuario con la configuración de conferencias de audio, vaya a las propiedades del usuario > **audioconferencia** > **Enviar información de conferencia por correo electrónico**. > Si hace esto, se enviará un correo electrónico que solo contenga el id. de la conferencia y el número de teléfono de la conferencia, pero no se incluirá el PIN. > Ver,  [Enviar un correo electrónico a un usuario con su información sobre la conferencia de acceso telefónico local](send-an-email-to-a-user-with-their-audio-conferencing-information.md). 
 **Uso de Windows PowerShell**
  
    
    

- Ejecutar las siguientes acciones para deshabilitar el envío de correos electrónicos: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```


    Para ayudarle con este cmdlet, vea  [Establecer CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
  

## ¿Qué más tengo que saber?


- Cuando están deshabilitados los correos electrónicos, puede activar manualmente enviar un correo electrónico con la conferencia ID y número de teléfono con la Skype para el centro de administración de la empresa. Sin embargo, si hace esto el PIN no esté incluido. Si desea restablecer el PIN de conferencia de audio y enviar correos electrónicos está deshabilitado, debe enviar al usuario de otra manera.
    
  
- De forma predeterminada, será el remitente de los mensajes de correo electrónico de Office 365, pero puede cambiar la dirección de correo electrónico y nombre con Windows PowerShell para mostrar y también usar el cmdlet  [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .
    
    > [!NOTE]
      > Si quiere cambiar la información de la dirección de correo electrónico, tendrá que asegurarse de que las directivas de correo electrónico de entrada de su organización permitan la recepción de mensajes enviados por la dirección específica personalizada. 

  - Escriba la dirección de correo electrónico en el parámetro  _SendEmailFromAddress_.
    
  
  - Escriba el nombre para mostrar del correo electrónico en el parámetro  _SendEmailFromDisplayName_.
    
  
  - Establecer el  _SendEmailOverride_ parámetro en _True_.
    
  
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
  
- El envío de correos electrónicos a los usuarios se puede deshabilitar con el Centro de administración de Skype Empresarial o con Windows PowerShell.
    
  

## ¿Desea saber cómo administrar con Windows PowerShell?


- También puede usar estos cmdlets para ahorrar tiempo o automatizar esto.
    
  -  [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  
  -  [Quitar CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  
  -  [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  
  -  [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  
- Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office UNRESOLVED_TOKEN_VAL(365) con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  -  [Seis razones por las podría desear usar Windows PowerShell para administrar Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  
  -  [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  
- Windows PowerShell cuenta con muchas ventajas en velocidad, simplicidad y productividad en comparación con solo usar el centro de administración de Office 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes:
    
  -  [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  
  -  [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  
  -  [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  

    > [!NOTE]
      > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en  [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)

## 
<a name="MT_Footer"> </a>


> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  
    
    


## See also
<a name="MT_Footer"> </a>


#### 


  
    
    
 [Conferencias de acceso telefónico en Office 365](http://technet.microsoft.com/library/90d51188-0ba9-4dc4-bd6c-ae11dd1f8551%28Office.14%29.aspx)
