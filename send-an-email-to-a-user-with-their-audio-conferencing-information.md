---
title: Enviar un correo electrónico a un usuario con su información sobre la conferencia de acceso telefónico local
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: How To
ms.service: OFFICE365
description: Send your users an email with their dial-in conferencing information.
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
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
---


# Enviar un correo electrónico a un usuario con su información sobre la conferencia de acceso telefónico local

A veces, puede que los usuarios necesiten que les envíe su información sobre la conferencia de acceso telefónico local. Para hacerlo con el Centro de administración de Skype Empresarial, haga clic en **Enviar información de conferencia por correo electrónico** en las propiedades de acceso telefónico local de un usuario. Al enviar este correo electrónico, contendrá toda la información de acceso telefónico local, incluido:
  
    
    


- El número de teléfono de la conferencia o el número de teléfono de acceso telefónico local del usuario.
    
  
- El id. de conferencia del usuario.
    
    > [!NOTE]
      > Se usan identificadores estáticos cuando los usuarios de su organización prefieren no tener que recordar un número aleatorio, poder seleccionar un número concreto o tener un número fácil de recordar. Cuando se usan identificadores de conferencia dinámicos, se asignará a cada reunión programada por un usuario un identificador de conferencia único. Si desea asignar identificadores de conferencia dinámicos y no estáticos,  [Usar audioconferencia dinámicos identificadores de su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md). 

Este es un ejemplo de este correo electrónico que se ha enviado:
  
    
    


  
    
    
![Correo electrónico de conferencia de acceso telefónico](images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
    
    

  
    
    

  
    
    

## Enviar un correo electrónico con información sobre la conferencia de acceso telefónico local a un usuario


1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
  
2. Vaya al **Centro de administración de Office 365** > **Skype Empresarial** y, en el panel de navegación de la izquierda, haga clic en **Conferencia de acceso telefónico local**.
    
  
3. Haga clic en **Usuarios de acceso telefónico local** y, después, seleccione el usuario.
    
  
4. En el panel de acciones, haga clic en **Enviar información de conferencia por correo electrónico**.
    
  

> [!TIP]
> También puede enviar correos electrónicos al usuario con la configuración de conferencia de acceso telefónico local (en las propiedades del usuario > **Conferencia de acceso telefónico local** > **Enviar información de conferencia por correo electrónico**). 
  
    
    


## ¿Qué más debe saber sobre este correo electrónico?


- Los usuarios de su organización reciben varios correos electrónicos después de que se habilita la opción de conferencias de acceso telefónico local para esos usuarios:
    
  - En qué casos se les asigna una licencia de **Conferencias RTC de Skype Empresarial**.
    
  
  - Al restablecer de forma manual el PIN de conferencia de acceso telefónico local del usuario.
    
  
  - Al restablecer de forma manual el id. de conferencia del usuario.
    
  
  - En qué casos se les quita una licencia de **Conferencias RTC de Skype Empresarial**.
    
  
  - Cuando se cambia el proveedor de servicios de conferencia de acceso telefónico local de un usuario de Microsoft a otro usuario o a **Ninguno**.
    
  
  - Cuando se cambia el proveedor de servicios de conferencia de acceso telefónico local de un usuario a Microsoft.
    
  
- De manera predeterminada, el remitente de los mensajes será de Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell y el cmdlet  [Set-CsOnlineDialInConferencingTenantSettings](http://go.microsoft.com/fwlink/?LinkId=708983). Para realizar cambios en la dirección de correo electrónico que envía el correo electrónico a los usuarios debe:
    
    > [!NOTE]
      > Si quiere cambiar la información de la dirección de correo electrónico, asegúrese de que las directivas de correo electrónico de entrada de su organización permitan la recepción de mensajes enviados por la dirección de correo electrónico personalizada configurada. 

  - Escriba la dirección de correo electrónico en el parámetro  _SendEmailFromAddress_.
    
  
  - Establecer el parámetro  _SendEmailOverride_ en _True_.
    
  
  - Escriba el nombre para mostrar del correo electrónico en el parámetro  _SendEmailFromDisplayName_.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
  

## ¿Desea saber cómo administrar con Windows PowerShell?


- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet  [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688 ).
    
    Para enviar un correo electrónico al usuario con su información sobre la conferencia de acceso telefónico local, ejecute lo siguiente:
    


  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```


- Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office UNRESOLVED_TOKEN_VAL(365) con un único punto de administración que puede simplificar el trabajo diario cuando tiene varias tareas que realizar. Para empezar a usar Windows PowerShell, vea estos temas:
    
  -  [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](http://go.microsoft.com/fwlink/?LinkId=525041)
    
  
  -  [Las mejores formas de administrar Office 365 con Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=525142)
    
  
- Windows PowerShell cuenta con muchas ventajas en velocidad, simplicidad y productividad en comparación con solo usar el centro de administración de Office 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes:
    
  -  [Introducción a Windows PowerShell y Skype Empresarial Online](http://go.microsoft.com/fwlink/?LinkId=525039)
    
     [Usar Windows PowerShell para administrar Skype Empresarial Online](http://go.microsoft.com/fwlink/?LinkId=525453)
    
  
  -  [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](http://go.microsoft.com/fwlink/?LinkId=525038)
    
  

    > [!NOTE]
      > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en  [Módulo de Windows PowerShell para Skype Empresarial Online.](http://go.microsoft.com/fwlink/?LinkId=294688)

