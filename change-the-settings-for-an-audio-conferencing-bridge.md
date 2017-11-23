---
title: Cambiar la configuración de un puente de conferencia de audio
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: How To
ms.service: OFFICE365
description: Get the steps you need to change settings for a Microsoft dial-in conferencing bridge that's used to prompt callers and gather names and pins for meeting organizers when they're not using Skype for Business clients. 
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
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
---


# Cambiar la configuración de un puente de conferencia de audio

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la  [declinación de responsabilidades](783fad3f-b77c-422b-b91f-7c8b0af324fb.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo  [aquí](https://support.office.com/en-us/article/783fad3f-b77c-422b-b91f-7c8b0af324fb). 
  
    
    


Si está configurando audioconferencia en Office 365, recibirás números de teléfono para los usuarios de lo que se denomina un puente de conferencia de audio. Un puente de conferencia puede contener uno o más números de teléfono. Los números de teléfono se usan cuando las personas que llaman llamen a una reunión. El número de teléfono se incluye en la parte inferior de la Skype para la invitación a la reunión de la empresa o Teams de Microsoft.
  
    
    


El puente de conferencia responde una llamada y avisos los avisos de la llamada de voz con una reunión de operador automático de y, a continuación, dependiendo de la configuración pueden reproducir las notificaciones, pida a las personas que llaman grabar su nombre y controla la configuración de PIN. PIN reciben al organizador de la reunión para permitirles para iniciar una reunión cuando están no está usando un Skype para empresas o Microsoft Teams la aplicación.
  
    
    


> [!IMPORTANT]
> Un PIN solo es necesario para el organizador de la reunión cuando un usuario de aplicación de Microsoft Teams o Skype Empresarial ya no ha iniciado la reunión. Si todos los usuarios se llaman a la reunión, el PIN es necesario para el organizador de la reunión iniciar la reunión. 
  
    
    


## Cambiar la configuración de un puente de conferencia de audio de Microsoft

 **Configurar la experiencia de reunión cuando las personas que llaman unirse a una reunión**
  
    
    

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
  
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
  
3. En la **Centro de administración de Skype Empresarial**, en el panel de navegación izquierdo, vaya a las **conferencias de Audio** > **Configuración del puente de Microsoft**.
    
  
4. En la página **Configuración del puente de Microsoft** en **Experiencia de unirse a la reunión** seleccione:
    
  - **Habilitar que se activen las notificaciones de entrada y salida de un reunión**. Esta opción está seleccionada de forma predeterminada. Si la desactiva, no se solicitará a las personas que llamen que registren su nombre antes de unirse a una reunión.
    
    Cuando selecciona **Habilitar activación de notificaciones de entrada y salida a reuniones** puede seleccionar estas opciones desde el menú desplegable **Tipo de anuncio de entrada y salida**:
    
  - **Números de teléfono** Cuando un usuario ingresa a una reunión, se muestra su número de teléfono cuando se une a esta.
    
  
  - **Tonos** Cuando los usuarios ingresan a una reunión mediante una llamada, se reproduce un tono de audio cuando se une a esta.
    
    > [!NOTE]
      > **Tono** está ahora disponible como tipo de anuncio para todos los clientes como una característica de vista previa.
  - **Solicitar a los autores de la llamada que registren su nombre antes de unirse a la reunión**. Esta opción está seleccionada de forma predeterminada. Si la desactiva, no se solicitará a las personas que llamen que registren su nombre antes de unirse a una reunión.
    
  
5. Después de realizar los cambios, haga clic en **Guardar**.
    
  
 **Configurar la longitud PIN las reuniones**
  
    
    

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
  
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
  
3. En la **Centro de administración de Skype Empresarial**, en el panel de navegación izquierdo, vaya a las **conferencias de Audio** > **Configuración del puente de Microsoft**.
    
  
4. En la página **Configuración del puente de Microsoft** > **Seguridad** > **Longitud del PIN** e introduzca el número de dígitos que quieren que tenga el PIN y haga clic en **Guardar**.
    
    > [!IMPORTANT]
      > El PIN puede ser de 4 a 12 dígitos. 
 **Seleccione si desea enviar correo electrónico a los usuarios**
  
    
    

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
  
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
  
3. En la **Centro de administración de Skype Empresarial**, en el panel de navegación izquierdo, vaya a las **conferencias de Audio** > **Configuración del puente de Microsoft**.
    
  
4. En la página **Configuración del puente de Microsoft**, active o desactive **Enviar automáticamente los mensajes de correo electrónico a los usuarios si cambia su configuración de conferencias de audio**, a continuación, haga clic en **Guardar**.
    
    Ver  [Mensajes de correo electrónico que se envían automáticamente a los usuarios cuando cambie su configuración de conferencias de Audio](emails-that-are-automatically-sent-to-users-when-their-audio-conferencing-settin.md)
    
  

## ¿Desea saber cómo administrar con Windows PowerShell?


- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet  [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ).
    
  
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
