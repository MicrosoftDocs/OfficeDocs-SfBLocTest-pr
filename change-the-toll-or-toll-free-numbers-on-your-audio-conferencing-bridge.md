---
title: Cambiar el pago o gratuitos números en el puente de conferencia de audio
ms.author: tonysmit
author: tonysmit
ms.date: 9/25/2017
ms.audience: Admin
f1_keywords: ms.lync.lac.PSTNConferencingRemovePhoneNumberFromBridge
ms.technology:
- Microsoft Teams
- Office 365 Enterprise admin
- Office 365 Midsize Business admin
- Office 365 Small Business admin
- Skype for Business
- Skype for Business admin center
- Skype for Business Online
ms.set-free-tag: Strat_SB_PSTN
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
---


# Cambiar el pago o gratuitos números en el puente de conferencia de audio

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la  [declinación de responsabilidades](6403f6d1-c05a-44ab-a6e0-558000e246f4.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo  [aquí](https://support.office.com/en-us/article/6403f6d1-c05a-44ab-a6e0-558000e246f4). 
  
    
    


Al comprar licencias de **Conferencias de Audio**, Microsoft aloja el  *puente de conferencia de audio*  para su organización. El puente de conferencia de audio ofrece números de teléfono desde diferentes ubicaciones para que los participantes y organizadores de reuniones pueden usarlos para unirse a reuniones de empresa o Teams de Microsoft mediante un teléfono de Skype.
  
    
    


Además de los números de teléfono que se ha asignado el puente de conferencia, puede  [Obtener números de teléfono de servicio de Skype Empresarial](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) (pago y números gratuitos utilizados para conferencias de audio) desde otras ubicaciones y, a continuación, asignar para el conferencias puente para que pueda Expandir cobertura para los usuarios.
  
    
    


> [!NOTE]
> Para poder asignar o cancelar la asignación de un puente de conferencia para un número de teléfono, el número de teléfono debe ser un número de ' *servicio*  '. Puede ver el tipo de número es mediante la **voz** > pestaña **números de teléfono** y busque en la columna **Tipo de número**.
  
    
    


## Pasos para asignar un número de teléfono de servicio nuevo a su puente de conferencia


### Paso 1: asignar al nuevo número de teléfono a su puente de conferencia de audio


1. Inicie sesión en Office 365 con su cuenta profesional.
    
  
2. Vaya al **Centro de administración de Office 365** > **Centros de administración** > **Skype Empresarial** > **Voz** > **Números de teléfono** y busque el número de teléfono.
    
  
3. Seleccione el número de teléfono en la lista y, en el panel de acciones, haga clic en **Asignar**.
    
  
4. En la página **Asignar**, haga clic en **Guardar**.
    
    Solo un número de teléfono de servicio se puede establecer como el número predeterminado para el puente de conferencia, **números de teléfono gratuitos de servicio no pueden configurarse como el número predeterminado de su puente de conferencia**. Si va a asignar a un número de teléfono de servicio y que desea establecer como el nuevo número predeterminado para el puente de conferencia de audio, active **usar este número como predeterminado**.
    
    > [!NOTE]
      > Tras asignar un nuevo número de teléfono, incluso si el número ha pasado a ser el nuevo número predeterminado, no cambiará el número predeterminado de los usuarios existentes. Para establecer el número de pago o gratuito predeterminado que se agrega a las invitaciones de reunión del organizador, consulte  [Establecer los números de teléfono de conferencias de Audio para organizadores que se incluyen en invitaciones](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md). 

### Paso 2: Cambiar los números de teléfono predeterminados que se incluyen en las invitaciones de reunión de los usuarios (opcional)

Los números de teléfono predeterminado de usuario son los que se incluyen en su reunión invita al programar una reunión. Para obtener más información, vea  [Establecer los números de teléfono de conferencias de Audio para organizadores que se incluyen en invitaciones](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
    
    

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
  
2. Vaya al **Centro de administración de Office 365** > **centros de administración** > **Skype empresarial** > **audioconferencia** > **usuarios de acceso telefónico** y encontrar los usuarios en la lista.
    
  
3. Haga clic en **Editar** en el panel de acciones.
    
  
4. En ** Número de teléfono de pago predeterminado** o Número de teléfono gratuito predeterminado, seleccione el número en la lista y haga clic en **Guardar**.
    
  
Cuando los cambios se hayan guardado, los números de teléfono nuevos predeterminados se incluirán en las invitaciones de reunión de los organizadores la próxima vez que se programe una nueva reunión.
  
    
    

### Paso 3: Actualizar las invitaciones de reunión existentes de los usuarios que usan el servicio de migración de reuniones (opcional)

Para estos dos pasos, debe iniciar Windows PowerShell. Para ver cómo hacerlo, haga clic  [¿Desea saber cómo administrar con Windows PowerShell?](6403f6d1-c05a-44ab-a6e0-558000e246f4.md#bk_PowerShell).
  
    
    
Al utilizar el servicio de migración de reuniones podrá decidir si quiere actualizar las invitaciones de reunión que se enviaron a los usuarios de su organización antes de cambiar los números de teléfono predeterminados. Para obtener información adicional, consulte  [Configuración del servicio de migración de reuniones (MMS)](setting-up-the-meeting-migration-service-mms.md)﻿.
  
    
    

- Ejecutar el servicio de migración de reunión (MMS) para los usuarios que tenían sus números de teléfono predeterminado cambiados en el paso 2. Para ello, ejecute el siguiente comando:
    
  



```
	Start-CsExMeetingMigration user@contoso.com


```


- También puede ver el estado de migración de las reuniones. Todas las reuniones se volverán a programar cuando no quede ninguna operación con el estado  *Pendiente*  o *En curso*  .
    
  



```
	Get-CsMeetingMigrationStatus -SummaryOnly
```


## Pasos para quitar la asignación de un número de teléfono de servicio de su puente de conferencia
<a name="bk_StartPowerShell"> </a>

Al cancelar la asignación de un número de teléfono de un puente de conferencia, los usuarios no podrán unirse a las reuniones con ese número de teléfono ya. Porque está cambiando el número de teléfono, es importante para actualizar todos los usuarios que podrían tener un número de teléfono como su número predeterminado (si existe) y actualizar sus invitaciones a la reunión antes de que el número de teléfono no está asignado del puente de conferencia de audio de existentes.
  
    
    
Si se quita el número de teléfono sin actualizar los usuarios y sus reuniones, las invitaciones de reunión existentes podrían contener un número de teléfono que no funcione para unirse a las reuniones.
  
    
    
Para los tres primeros pasos, debe iniciar Windows PowerShell. Para ver cómo hacerlo, haga clic  [aquí](http://technet.microsoft.com/library/bk_PowerShell.aspx).
  
    
    

### Paso 1: Actualizar usuarios que puedan tener el número de teléfono cuya asignación se va a cancelar como uno de sus números predeterminados

Reemplace el número de teléfono gratuito o de pago predeterminado de todos los usuarios que tengan el número cuya asignación se va a cancelar como número predeterminado e inicie el proceso de volver a programar las reuniones. Para ello, ejecute el siguiente comando:
  
    
    

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```


> [!NOTE]
> Dependiendo de cuál sea el tamaño de su organización, este proceso podría llevar algún tiempo. 
  
    
    

 **También puede cambiar el número gratuito o de pago predeterminado de los usuarios en el centro de administración de Skype Empresarial, si bien de este modo no se volverán a programar las reuniones automáticamente**. Para obtener información adicional, consulte [Establecer los números de teléfono de conferencias de Audio para organizadores que se incluyen en invitaciones](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
    
    

### Paso 2: Ver el estado de migración de las reuniones con Windows PowerShell

Todas las reuniones se volverán a programar cuando no quede ninguna operación con el estado  *Pendiente*  o *En curso*  .
  
    
    

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Para obtener más información sobre el servicio de migración de reuniones, consulte  [Configuración del servicio de migración de reuniones (MMS)](setting-up-the-meeting-migration-service-mms.md).
  
    
    

### Paso 3: cancelar la asignación del puente de conferencia de audio de antiguo número de teléfono


1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
  
2. Vaya al **Centro de administración de Office 365** > **Centros de administración** > **Skype Empresarial** > **Voz** > **Números de teléfono** y busque el número de teléfono.
    
  
3. Seleccione el número de teléfono en la lista y, en el panel de acciones, haga clic en **Quitar asignación**.
    
  
4. En la ventana **¿Desea anular la asignación de este número?**, haga clic en **Sí**.
    
  

> [!IMPORTANT]
> Una vez sin asignar un puente de conferencia de audio de un número de teléfono, el número de teléfono ya no estará disponible para los usuarios puedan unirse a reuniones nuevas o existentes. 
  
    
    


## ¿Desea saber cómo administrar con Windows PowerShell?
<a name="bk_PowerShell"> </a>


### Para verificar que Windows PowerShell está listo

 **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
  
    
    

1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
    
  
2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
  
3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea  [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
    
  
4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en  [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
  
Si necesita más información, consulte  [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
  
    
    

### Para iniciar Windows PowerShell


  
    
    
 **Iniciar una sesión de Windows PowerShell**
  
    
    

1. En el **menú Inicio** > **Windows PowerShell**.
    
  
2. En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:
    
    > [!NOTE]
      > Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.


  
    
    
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```


  
    
    
> 
  ```
  $credential = Get-Credential
  ```


  
    
    
> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```


  
    
    
> 
  ```
  Import-PSSession $session
  ```

Si desea obtener más información sobre cómo iniciar Windows PowerShell, consulte  [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o [Conectarse a Skype Empresarial Online con Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).
  
    
    

### Ahorrar tiempo o automatizar

Para ahorrar tiempo o automatizar este proceso, puede usar los cmdlet  [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) o **Set-CsOnlineDialInConferencingUserDefaultNumber**.
  
    
    

- Use el cmdlet  [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) para cambiar el número de pago o el número gratuito predeterminado para usuarios específicos.
    
  - Para cambiar el número gratuito predeterminado de un usuario, ejecute:
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Use el cmdlet de **Set-CsOnlineDialInConferencingUserDefaultNumber** para cambiar el número de pago o el número gratuito predeterminado de los usuarios, según el número predeterminado original o la ubicación.
    
    > [!NOTE]
      > Nota:Para buscar el id. de puente, use **Get-CsOnlineDialInConferencingBridge**.

  - Para establecer el 8005551234 como número gratuito predeterminado para todos los usuarios que no tengan un número, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Para cambiar el número gratuito predeterminado de todos los usuarios que tienen el 8005551234 como su número gratuito predeterminado al 8005551239 y volver a programar automáticamente sus reuniones, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - Para establecer el 8005551234 como número gratuito predeterminado para todos los usuarios que se encuentren en EE. UU. y volver a programar automáticamente sus reuniones, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```


    > [!NOTE]
      > La ubicación que se usa arriba debe coincidir con la información de contacto de los usuarios establecidos en el Centro de administración de Office 365. 

### Más información


- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  -  [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  
  -  [Seis razones por las podría desear usar Windows PowerShell para administrar Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  -  [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  
  -  [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  
  -  [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  

## 
<a name="MT_Footer"> </a>


> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  
    
    


