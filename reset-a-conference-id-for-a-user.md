---
title: Restablecer un id. de conferencia para un usuario
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: How To
ms.service: OFFICE365
description: Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. 
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
- httpsfix
- Strat_SB_PSTN
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
---


# Restablecer un id. de conferencia para un usuario

Cuando en su organización no se hayan habilitado en su organización los identificadores de conferencia dinámicos, se creará automáticamente un identificador de conferencia estático cuando se habilite a un usuario para las conferencias de acceso telefónico local con Microsoft como proveedor. Este identificador de conferencias se incluye en la parte inferior de las invitaciones a las reuniones de Skype Empresarial Online, junto con los números de teléfono de acceso telefónico que pueden usar los autores de las llamadas a una reunión. Cuando el usuario marca el número de teléfono, el operador automático de la reunión le solicitará al autor de la llamada que introduzca este identificador de conferencia para que pueda asistir a la reunión.
  
    
    


Se usan identificadores estáticos cuando los usuarios de su organización prefieren no tener que recordar un número aleatorio, poder seleccionar un número concreto o tener un número fácil de recordar. Cuando se usan identificadores de conferencia dinámicos, se asignará a cada reunión programada por un usuario un identificador de conferencia único. Si desea asignar identificadores de conferencia dinámicos y no estáticos,  [Usar audioconferencia dinámicos identificadores de su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
    
    


Skype Empresarial solo establece automáticamente los identificadores de conferencia si un usuario está habilitado para las conferencias de acceso telefónico local con Microsoft como su proveedor. Si necesita restablecer un identificador de conferencia para un usuario que está usando un proveedor de servicios de audioconferencia (ACP) de terceros, tendrá que introducir manualmente un identificador de conferencia en la página de propiedades del usuario para el usuario.
  
    
    


## Restablecer el id. de conferencia de reunión para un usuario


### Para restablecer el id. de conferencia de reunión


1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
  
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
  
3. En el **Centro de administración de Skype Empresarial**> **Conferencias de acceso telefónico local**, en la página de acciones en **Id. de conferencia** haga clic en **Restablecer**.
    
  
4. En la ventana ** ¿Restablecer Id. de conferencia?** haga clic en **Sí**. Se creará automáticamente un Id. de conferencia y se enviará un correo electrónico al usuario con el nuevo Id. de conferencia. De forma predeterminada, los correos electrónicos se envían a los usuarios, pero esto se puede desactivar. 
    
    > [!NOTE]
      > Después de restablecer el Id. de conferencia, se enviará al usuario un correo electrónico con el nuevo Id. de conferencia. Este mensaje de correo electrónico se enviará a la dirección de correo electrónico principal, en muchos casos, su buzón de correo de Office 365. El correo electrónico contiene el nuevo Id. de conferencia, los números de teléfono de acceso telefónico local predeterminados y las instrucciones para usar la herramienta de actualización de reuniones de Skype Empresarial para actualizar las reuniones existentes. 

## ¿Qué más debo saber?


- Puede enviar toda la información de la conferencia al usuario en un correo electrónico que incluya el Id. de conferencia y los números de teléfono de acceso telefónico local haciendo clic en **Enviar información de conferencia a través del correo electrónico**. De esta forma no se envía el PIN.
    
  
- El Id. de conferencia tiene que contener siete dígitos y su longitud no se puede cambiar ni en el Centro de administración de Skype Empresarial ni con Windows PowerShell.
    
  
- Una vez que se ha restablecido el nuevo id. de conferencia, podrá verlo en **Id. de conferencia**.
    
  
- El id. de conferencia para un usuario para las conferencias de acceso telefónico local se puede ver en la parte inferior del panel de acciones en **Conferencias de acceso telefónico local** al seleccionar el usuario en la página **Usuarios**.
    
  
- Después de crear un identificador de conferencia nuevo, los autores de las llamadas no podrán usar el identificador de conferencia anterior. Deberá solicitar a los usuarios que reprogramen las invitaciones de las reuniones existentes a fin de asegurarse de que el nuevo identificador de conferencia se agregue a las invitaciones. Los usuarios pueden usar la Herramienta de reuniones de Skype Empresarial para actualizar las reuniones existentes. Para ver cómo descargar, instalar y ejecutar la Herramienta de actualización de reuniones de Skype Empresarial, consulte:
    
  -  [Herramienta de actualización de reuniones para Skype y Lync](http://technet.microsoft.com/library/2b525fe6-ed0f-4331-b533-c31546fcf4d4%28Office.14%29.aspx)
    
  
  -  [Skype Empresarial Online, herramienta de migración de reuniones (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)
    
  
  -  [Skype Empresarial Online, herramienta de migración de reuniones (32 bits)](http://go.microsoft.com/fwlink/?LinkID=626046)
    
  

## ¿Desea saber cómo administrar con Windows PowerShell?


- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  -  [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  
  -  [Seis razones por las podría desear usar Windows PowerShell para administrar Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  -  [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  
  -  [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  
  -  [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  

