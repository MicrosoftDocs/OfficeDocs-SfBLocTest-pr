---
title: Asignar a un tercero como el proveedor de conferencias de audio
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/3/2017
ms.audience: Admin
ms.topic: How To
f1_keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.service: OFFICE365
description: Learn how to set up a third-party as your dial-in conferencing provider with Skype for Business. 
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
- Strat_SB_PSTN
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
---


# Asignar a un tercero como el proveedor de conferencias de audio

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la  [declinación de responsabilidades](77f68ca7-c1cf-40d9-9c23-87a6b2abe9de.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo  [aquí](https://support.office.com/en-us/article/77f68ca7-c1cf-40d9-9c23-87a6b2abe9de). 
  
    
    


Un proveedor de servicios de audioconferencia proporciona el  *puente de conferencia*  . Puente de conferencia proporciona el número de teléfono de acceso telefónico, bordes e identificadores de conferencia para las reuniones que se crean. Solo debe asignar un proveedor de servicios de audioconferencia a las personas que van a programar o dirigir reuniones de Microsoft Teams o Skype Empresarial.
  
    
    


> [!NOTE]
> Para Teams de Microsoft, un usuario no puede usar un proveedor de servicios de audioconferencia de terceros, deben utilizar audioconferencia en Office 365 que establece el proveedor de servicios de audioconferencia a Microsoft. 
  
    
    


## Pasos para poder asignar un proveedor de servicios de audioconferencia de terceros


1. Dependiendo del plan de Office 365, debe comprar licencias de complemento de **Conferencias de Audio** para las personas de su organización que se va a programar o cliente potencial Skype para empresas o Microsoft Teams reuniones usando las conferencias de Audio. Para obtener más información, vea [Skype para Business y Microsoft Teams licencias de complemento](skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
  
2. Si ha adquirido licencias de complemento de **Conferencias de Audio**, asignarlos a las personas de su organización que se va a programar o dirigir reuniones que se utilizan las conferencias de Audio. Vea  [Asignar Skype para Business y Microsoft Teams licencias](assign-skype-for-business-and-microsoft-teams-licenses.md).
    
    > [!NOTE]
      > Si se asigna una licencia de **Conferencias de Audio** a una persona después de asignar de un proveedor de servicios de audioconferencia de terceros, esa persona se establece automáticamente para usar Microsoft como su proveedor de servicios de audioconferencia en su lugar! Si esto sucede, debe quitar Microsoft como proveedor de conferencias de audio antes de poder asignar un proveedor de servicios de audioconferencia de terceros en ellos.
3. Buscar un proveedor de servicios de audioconferencia de terceros en  [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530). Póngase en contacto con ellos y descubra cómo obtener cosas configurar con ellos.
    
    Se le ofrecerá lo siguiente: 
    
  - **Números de acceso telefónico (número)** y números gratuitos, si están disponibles.
    
  
  - **Id. de conferencia** para cada persona que programe reuniones. Algunos ACP los llaman códigos de acceso a conferencias.
    
    > [!NOTE]
      > Al habilitar a una persona para conferencias de audio y agregar les asigna a un proveedor de audioconferencia de terceros, los números de audio e identificadores de conferencia (códigos de acceso) se agregan automáticamente a las reuniones Skype Empresarial Online **nueva** que crean.

## Cómo asignar un proveedor de servicios de audioconferencia de terceros a un usuario


1. En el **Centro de administración de Skype Empresarial**, seleccione **Usuarios**. Seleccione el usuario de la lista y haga clic en **Editar** en el panel de acciones.
    
  
2. En la página de propiedades del usuario haga clic en **conferencias de Audio** y, a continuación, ponga en esta información:
    
  - **Nombre de proveedor**: seleccione el proveedor de terceros en la lista.
    
  
  - **Número de pago**: es obligatorio.
    
  
  - **Número gratuito**: es obligatorio.
    
  
  - **ID de conferencia**: inclúyalo. Lo proporciona su proveedor de servicios de audioconferencia. 
    
  
3. Haga clic en **Guardar**.
    
  
4. Enviar a cada persona el PIN que ha recibido en el proveedor de servicios de audioconferencia. El PIN puede que deba llamar como el organizador de la llamada de conferencia o el carácter de relleno.
    
    > [!NOTE]
      > Usar un proveedor de servicios de audioconferencia de terceros, no hay una forma de ver o configurar el PIN en nombre de los organizadores de la reunión. 

## Cómo asignar un proveedor de servicios de audioconferencia de terceros a varias personas al mismo tiempo


1. En el **Centro de administración de Skype Empresarial**, elija **audioconferencia** > **puente de Microsoft**. En la parte inferior de la página, haga clic en **Si desea configurar un proveedor de servicios de audioconferencia de terceros en su lugar, haga clic aquí**.
    
    > [!NOTE]
      > Si ya existe un proveedor de servicios de audioconferencia configurar, en la parte inferior de la página, haga clic en **haga clic aquí para configurar un proveedor de servicios de audioconferencia de terceros**. 
2. En **Configurar página de proveedores de audioconferencia de terceros**, en **usuarios importar y exportar**, haga clic en **Asistente para exportación** y, a continuación, siga los pasos del **Asistente para exportar usuarios**. Cuando haya terminado, tendrá un archivo que contenga las personas que desea configurar para conferencias de audio.
    
  
3. Enviar el archivo que creó en su proveedor de servicios de audioconferencia de terceros. Se agregue información de conferencias de audio para las personas que aparecen en el archivo y, a continuación, devuelva el archivo.
    
  
4. Compruebe que el archivo devuelto contiene la información correcta. Hemos sabido de casos en los que no todas las personas que aparecían en el archivo obtuvieron la información correcta. 
    
  
5. En **Configurar página de proveedores de audioconferencia de terceros**, en **usuarios importar y exportar**, haga clic en **Asistente para importar** y, a continuación, siga los pasos del **Asistente para importar usuarios**
    
  
6. Enviar a cada persona el PIN que ha recibido en el proveedor de servicios de audioconferencia. El PIN puede que deba llamar como el organizador de la llamada de conferencia o el carácter de relleno.
    
    > [!NOTE]
      > Usar un proveedor de servicios de audioconferencia de terceros, no hay una forma de ver o configurar el PIN en nombre de los organizadores de la reunión. 

## Cuándo usar un proveedor de servicios de audioconferencia de terceros

Si se encuentra en un país o región donde Microsoft audioconferencia no está disponible, la calidad de servicio no es excelente debido a su ubicación o tiene un contrato existente con un proveedor de servicios de audioconferencia de terceros, se recomienda utilizar un tercero de audio proveedor de conferencias. En caso contrario, se recomienda utilizar Microsoft como su proveedor de servicios de audioconferencia.
  
    
    

## Automatizar la asignación del proveedor de audioconferencias de terceros mediante Windows PowerShell


- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet  [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851).
    
    > [!NOTE]
      > Para cambiar el proveedor de audio de Microsoft a un proveedor de servicios de audioconferencia de terceros, debe quitar Microsoft como el proveedor de servicios de audioconferencia. Para ello, use el cmdlet  [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) .
- Para obtener más información sobre el uso de Windows PowerShell, vea  [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038).
    
  

## ¿Qué más necesito saber?

Una persona de su organización solo puede usar un proveedor de servicios de audioconferencia. Para cambiar el proveedor de conferencias de audio de una persona a Microsoft, consulte  [Moving a user's audio conferencing provider to Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) o [Asignar Microsoft como proveedor de conferencias de audio](assign-microsoft-as-the-audio-conferencing-provider.md).
  
    
    

## Temas relacionados

 [Set up Audio Conferencing for Skype for Business and Microsoft Teams](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
    
    
 [Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)
  
    
    

## 
<a name="MT_Footer"> </a>


> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  
    
    


