---
title: Mensajes de correo electrónico que se envían automáticamente a los usuarios cuando cambie su configuración de conferencias de Audio
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: Reference
ms.service: OFFICE365
description: Learn about what information is sent automatically to users by email when their dial-in conferencing settings change. 
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
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
---


# Mensajes de correo electrónico que se envían automáticamente a los usuarios cuando cambie su configuración de conferencias de Audio

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la  [declinación de responsabilidades](1b46da6d-f93a-4cc0-9ae8-af765935b007.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo  [aquí](https://support.office.com/en-us/article/1b46da6d-f93a-4cc0-9ae8-af765935b007). 
  
    
    


Los correos electrónicos se enviarán automáticamente a los usuarios que están  [Set up Audio Conferencing for Skype for Business and Microsoft Teams](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md) con Microsoft como proveedor de conferencias de audio.
  
    
    


De forma predeterminada, hay cuatro tipos de correo electrónico que se enviará a los usuarios que están habilitados para conferencias de Audio. Sin embargo, si desea limitar el número de correos electrónicos enviados a los usuarios, puede desactivar el. Audioconferencia en Office 365 le enviará el correo electrónico a los usuarios de correo electrónico cuando:
  
    
    


- **Se asigna una licencia de **Conferencias de Audio** o al que desea cambiar el proveedor de servicios de audioconferencia a Microsoft.**
    
    Este correo electrónico incluye el identificador de conferencia, el número de teléfono de conferencia predeterminado para las reuniones, la audioconferencia PIN para el usuario y las instrucciones y el vínculo utilicen la Skype empresarial Online reunión actualizar herramienta que se utiliza para actualizar reuniones existentes para la usuarios. Vea  [Asignar Skype para Business y Microsoft Teams licencias](assign-skype-for-business-and-microsoft-teams-licenses.md) o [Asignar Microsoft como proveedor de conferencias de audio](assign-microsoft-as-the-audio-conferencing-provider.md).
    
    > [!NOTE]
      > Si su organización se ha habilitado para identificadores de conferencia dinámico, todas las reuniones de un usuario que se programan tendrá identificadores de conferencia único. Puede configurar  [Usar audioconferencia dinámicos identificadores de su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md). 

    Este es un ejemplo de este correo electrónico:
    
     ![Skype Empresarial: comprobar licencia](images/17913e03-8b4a-4563-b58d-2f09b65fbcaa.png)
  

    Puede encontrar más información acerca de Skype para Business licensing mirando  [Skype para Business y Microsoft Teams licencias de complemento](skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
  
- **Cambia el id. de conferencia o número de teléfono de conferencia predeterminado de un usuario.**
    
    Este mensaje contiene el identificador de conferencia, número de teléfono de la conferencia de forma predeterminada y las instrucciones y vínculos para usar la Skype empresarial Online reunión actualizar herramienta que se utiliza para actualizar reuniones existentes para el usuario. Pero este mensaje no incluye el PIN de conferencia de audio del usuario. Vea  [Restablecer un id. de conferencia para un usuario](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
      > Si su organización se ha habilitado para identificadores de conferencia dinámico, todas las reuniones de un usuario que se programan tendrá identificadores de conferencia único. Puede configurar  [Usar audioconferencia dinámicos identificadores de su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md). 

    Este es un ejemplo de este correo electrónico:
    
     ![La información de conferencias de acceso telefónico local ha cambiado.](images/d6d3e028-d9fb-48c4-97c0-a73d6ade5ea3.png)
  

  

  
- **Se restablece el PIN de un usuario de audioconferencia.**
    
    Este mensaje contiene el PIN de conferencia de audio del organizador, el identificador de conferencia existente y número de teléfono de conferencia predeterminado para el usuario. Vea  [Restablecer el PIN de conferencia de acceso telefónico local de un usuario](reset-the-audio-conferencing-pin-for-a-user.md)
    
    > [!NOTE]
      > Si su organización se ha habilitado para identificadores de conferencia dinámico, todas las reuniones de un usuario que se programan tendrá identificadores de conferencia único. Puede configurar  [Usar audioconferencia dinámicos identificadores de su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md). 

    Este es un ejemplo de este correo electrónico:
    
     ![El PIN para las conferencias de acceso telefónico local ha cambiado.](images/df8df4f8-d11f-41b8-9187-99e66a88831b.png)
  

  

  
- **Se elimina la licencia de un usuario o cuando se cambia su proveedor de servicios de audioconferencia de Microsoft a otro proveedor o ninguno**
    
    Esto ocurre cuando se elimina la licencia de **Conferencias de Audio** de un usuario o al cambiar el proveedor de conferencias de audio de un usuario de Microsoft a un proveedor de servicios de audioconferencia de terceros o al establecer el proveedor en **Ninguno**. Este mensaje contiene las instrucciones y la información del usuario usar el Skype para la herramienta de actualización de reunión en línea de negocio para quitar la información específica de conferencias de audio, como el ID predeterminado conferencia teléfono número o conferencia.
    
    Vea  [Asignar o cancelar licencia para Office 365 para empresas](http://technet.microsoft.com/library/997596b5-4173-4627-b915-36abac6786dc%28Office.14%29.aspx) o [Asignar a un tercero como el proveedor de conferencias de audio](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
    Este es un ejemplo de este correo electrónico:
    
     ![Las conferencias de acceso telefónico local están desactivadas.](images/4ebc8ae6-b516-452e-8d27-6177e145daba.png)
  

  

  

## Realizar cambios en los mensajes de correo electrónico que se les envían

Puede realizar cambios en el correo electrónico que se envía automáticamente a los usuarios incluidos en la dirección de correo electrónico y el nombre para mostrar que se incluye en la información  *de*  contacto. De forma predeterminada, el remitente de los correos electrónicos será de Office 365, pero puede cambiar la dirección de correo electrónico y nombre para mostrar con Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Para realizar cambios en la dirección de correo electrónico que envía el correo electrónico a los usuarios, debe:
  
    
    

- Escriba la dirección de correo electrónico en el parámetro  _SendEmailFromAddress_.
    
  
- Escriba el nombre para mostrar del correo electrónico en el parámetro  _SendEmailFromDisplayName_.
    
    
    
  
- Establecer el parámetro  _SendEmailOverride_ en _True_.
    
  
Puede realizar cambios en el correo electrónico que se envía a los usuarios, como la dirección de correo electrónico desde la que se envía el mensaje o el nombre para mostrar del correo electrónico, si ejecuta lo siguiente:
  
    
    



```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```


> [!NOTE]
> Si quiere cambiar la información de la dirección de correo electrónico, tendrá que asegurarse de que las directivas de correo electrónico de entrada de su organización permitan la recepción de mensajes enviados por la dirección específica personalizada. > Si decide reemplazar la información de contacto del  *remitente*  , tendrá que comprobar que los correos electrónicos se envían correctamente a los usuarios. Para ello, pruebe con un usuario de su organización.
  
    
    

Puede usar el cmdlet  [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) para administrar otros ajustes de su organización como correo electrónico.
  
    
    

## ¿Qué pasa si no desea que se les envíen correos electrónicos?

Cuando se deshabilita enviarlos correos electrónicos a los usuarios, no se envía correo electrónico incluso cuando un usuario obtiene asigna una licencia. Si este es el caso, el identificador de conferencia, número de teléfono de conferencias de forma predeterminada y lo más importante, su PIN de conferencia de audio no se enviará al usuario. Cuando esto ocurre, debe decir al usuario mediante el envío de un correo electrónico independiente o mediante una llamada a ellos.
  
    
    
De forma predeterminada, los correos electrónicos se enviarán a los usuarios, pero si desea evitar que recibe correo electrónico para conferencias de audio puede usar la Skype para el centro de administración de la empresa o de Windows PowerShell.
  
    
    
 **Usar la Skype centro de administración de la empresa**
  
    
    

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
  
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
  
3. En la **Centro de administración de Skype Empresarial**, en el panel de navegación izquierdo, vaya a las **conferencias de Audio** > **Configuración del puente de Microsoft**.
    
  
4. En la página **Configuración del puente de Microsoft**, active o desactive **Enviar automáticamente correos electrónicos al usuario si cambia su información de conferencias de audio**.
    
  
5. Haga clic en **Guardar**.
    
  
 **Uso de Windows PowerShell**
  
    
    

1. Ejecute las acciones siguientes para deshabilitar el envío de todos los correos electrónicos a sus usuarios:
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

Puede usar el  [Conjunto CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) administrar otras opciones de configuración de la organización como correo electrónico.
  
    
    

## ¿Qué más debe saber sobre este correo electrónico?


- Para más información sobre habilitar y deshabilitar el envío de correos electrónicos de forma automática a sus usuarios, vea  [Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md).
    
  
- A veces los usuarios pierden la información de audio y necesita poder enviarlos toda su información de audio a ellos. Puede hacer esto mediante la Skype para centro de administración de la empresa y haciendo clic en **Enviar información de conferencia por correo electrónico** en las propiedades de audioconferencia para un usuario. Vea [Enviar un correo electrónico a un usuario con su información sobre la conferencia de acceso telefónico local](send-an-email-to-a-user-with-their-audio-conferencing-information.md). Sin embargo, esta información no incluye el PIN de conferencia de audio.
    
    Este es un ejemplo del correo electrónico que se les enviará:
    
     ![Correo electrónico de conferencia de acceso telefónico](images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  

  

  

## ¿Desea saber cómo administrar con Windows PowerShell?


- De forma predeterminada, el remitente de los correos electrónicos será de Office 365, pero puede cambiar la dirección de correo electrónico y nombre para mostrar con Windows PowerShell y el cmdlet  [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .
    
  

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


  
    
    
 [Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md)
  
    
    
 [Enviar un correo electrónico a un usuario con su información sobre la conferencia de acceso telefónico local](send-an-email-to-a-user-with-their-audio-conferencing-information.md)
