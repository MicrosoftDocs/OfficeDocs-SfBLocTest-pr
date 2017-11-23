---
title: Permitir a los usuarios grabar su nombre al unirse a una reunión
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: How To
ms.service: OFFICE365
description: Learn how to enable or disable whether your users can record their names when they join a meeting 
ms.collection: Adm_Skype4B_Online
ms.technology:
- Microsoft Teams
- Office 365 Enterprise
- Office 365 Enterprise admin
- Office 365 Midsize Business admin
- Office 365 Small Business admin
- Skype for Business admin center
- Skype for Business Online
ms.set-free-tag:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
---


# Permitir a los usuarios grabar su nombre al unirse a una reunión

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la  [declinación de responsabilidades](1d649328-ada7-422d-a074-d6da4da36970.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo  [aquí](https://support.office.com/en-us/article/1d649328-ada7-422d-a074-d6da4da36970). 
  
    
    


Al configurar conferencias de Audio para Skype Empresarial y Teams de Microsoft, recibirá los números de teléfono y lo que se denomina un puente de conferencia de audio. Un puente de conferencia puede contener uno o más números de teléfono que pueden ser un número de teléfono dedicado o compartidas.
  
    
    


El puente de conferencia responde a la llamada de un usuario que llama a una reunión con un teléfono. Ese puente responde al autor de la llamada con avisos de voz de un operador automático y, luego, de acuerdo con su configuración, puede reproducir notificaciones, solicitar a los autores de las llamadas que graben sus nombres y configura la seguridad del PIN para los organizadores de reuniones. Los PIN se proporcionan al organizador de la reunión y con ellos se puede empezar una reunión, pero puede configurarlo de modo que no se necesite un PIN para comenzar una reunión.
  
    
    


## Establecer si los autores de las llamadas tienen que grabar sus nombres


1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
  
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
  
3. En la **Centro de administración de Skype Empresarial**, en el panel de navegación izquierdo, vaya a las **conferencias de Audio** > **Configuración del puente de Microsoft**.
    
  
4. En **Experiencia de unirse a la reunión** > **Habilitar que se activen las notificaciones de entrada y salida de la reunión**
    
  - **Activado**: se solicitará a los autores de las llamadas que graben sus nombres antes de unirse a la reunión. Esta opción está seleccionada de forma predeterminada.
    
  
  - **Desactivado**: no se solicitará a los autores de las llamadas que graben sus nombres antes de unirse a la reunión.
    
  
5. Después de realizar los cambios, haga clic en **Guardar**.
    
  

## ¿Desea saber cómo administrar con Windows PowerShell?


- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet  [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) .
    
  
- Windows PowerShell es todo sobre la administración de usuarios y lo que los usuarios pueden hacer. Con Windows PowerShell, puede administrar Office UNRESOLVED_TOKEN_VAL(365) mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas a realizar. Para empezar con Windows PowerShell, consulte estos temas:
    
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
