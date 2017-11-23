---
title: Establecer la longitud del PIN para las reuniones de acceso telefónico local
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: How To
ms.service: OFFICE365
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business.
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
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
---


# Establecer la longitud del PIN para las reuniones de acceso telefónico local

Cuando configure conferencias de acceso telefónico local en Skype Empresarial Online, recibirá los números de teléfono y lo que se denomina un puente de audioconferencia o de RTC. Un puente de conferencia puede contener uno o más números de teléfono. El número de teléfono que establezca se incluirá en la invitación a la reunión.
  
    
    


La conferencia de acceso telefónico local o el puente de audioconferencia responderá a las llamadas de los usuarios que llamen a una reunión mediante un teléfono. Este sistema responde al autor de la llamada con mensajes de voz que emite un operador automático y, a continuación, dependiendo de la configuración que se haya definido, pueden reproducir las notificaciones y pedir a los autores de las llamadas que registren su nombre. En la configuración del puente de Microsoft de Skype Empresarial Online, puede cambiar la configuración de las notificaciones de reunión y de la experiencia de unirse a esta, así como establecer la longitud de los PIN que usan los organizadores de la reunión. Los PIN se proporcionan a los organizadores de la reunión para empezar una.
  
    
    


## Configurar la longitud del PIN


### Establecer la longitud del PIN para los organizadores de la reunión


1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
  
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
  
3. En el **Centro de administración de Skype Empresarial**, en la barra de navegación izquierda, vaya a **Conferencias de acceso telefónico local** > **Configuración del puente de Microsoft**.
    
  
4. En **Seguridad** > **Longitud del PIN**, introduzca la cantidad de dígitos que desee para el PIN y, luego, haga clic en **Guardar**.
    
  

> [!NOTE]
> Un PIN no es lo mismo que un identificador de conferencia. Los autores de llamada usan los identificadores de conferencia al unirse a la reunión. Se utilizan para identificar la reunión. El PIN se usa para autenticar un autor de llamada como organizador de la reunión. 
  
    
    


## ¿Desea más información sobre la configuración del PIN?


- Los PIN pueden tener de 4 a 12 dígitos (el valor predeterminado es 5). En la creación de un PIN solo pueden usarse números. Por lo tanto, no pueden usarse letras ni caracteres especiales.
    
  
- Solo es necesario un PIN para el organizador de la reunión cuando un usuario cliente de Skype Empresarial aún no ha iniciado la reunión. Si todas las personas llaman a la reunión, se necesita el PIN para que el organizador de la reunión inicie la reunión.
    
  
- La configuración de seguridad del PIN se aplica a todos los números de teléfono asociados a un puente de Microsoft, así como a todas las reuniones que usen los números de teléfono asociados a dicho puente.
    
  

## ¿Desea saber cómo administrar con Windows PowerShell?


- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet  [Set-CsOnlineDialInConferencingTenantSettings](http://go.microsoft.com/fwlink/?LinkId=715757).
    
  
- Para establecer el número de dígitos del PIN en 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
  
- Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office UNRESOLVED_TOKEN_VAL(365) con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  -  [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](http://go.microsoft.com/fwlink/?LinkId=525041)
    
  
  -  [Las mejores formas de administrar Office 365 con Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=525142)
    
  
- Windows PowerShell cuenta con muchas ventajas en velocidad, simplicidad y productividad en comparación con solo usar el centro de administración de Office 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Obtenga más información sobre estas ventajas en los temas siguientes:
    
  -  [Introducción a Windows PowerShell y Skype Empresarial Online](http://go.microsoft.com/fwlink/?LinkId=525039)
    
  
  -  [Usar Windows PowerShell para administrar Skype Empresarial Online](http://go.microsoft.com/fwlink/?LinkId=525453)
    
     [Usar Windows PowerShell para administrar Skype Empresarial Online](http://go.microsoft.com/fwlink/?LinkId=525453)
    
  
  -  [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](http://go.microsoft.com/fwlink/?LinkId=525038)
    
  

    > [!NOTE]
      > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en  [Módulo de Windows PowerShell para Skype Empresarial Online.](http://go.microsoft.com/fwlink/?LinkId=294688)

## See also


#### 


  
    
    
 [Conferencias de acceso telefónico en Office 365](http://technet.microsoft.com/library/90d51188-0ba9-4dc4-bd6c-ae11dd1f8551%28Office.14%29.aspx)
