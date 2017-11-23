---
title: Ver, cambiar y restablecer un id. de conferencia asignado a un usuario
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: How To
ms.service: OFFICE365
description: Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. 
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
- Skype for Business Online operated by 21Vianet
- Skype for Business Online operated by 21Vianet - admin center
ms.set-free-tag:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
---


# Ver, cambiar y restablecer un id. de conferencia asignado a un usuario

Se asigna automáticamente un id. de conferencia a un usuario cuando se configura para conferencias de acceso telefónico local con Microsoft como proveedor de dichas conferencias. El id. de conferencia asignado puede ser estático o dinámico y se envía en la invitación a la reunión cuando se programa la reunión. 
  
    
    


Se usan id. estáticos cuando los usuarios de su organización prefieren no tener que recordar un número aleatorio, poder seleccionar un número concreto o tener un número fácil de recordar. Cuando se usan id. de conferencia dinámicos, se asignará a cada reunión programada por un usuario un id. de conferencia único. Si desea asignar identificadores de conferencia dinámicos y no estáticos,  [Usar audioconferencia dinámicos identificadores de su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
    
    


Aunque un se creará y se asignará id. de conferencia automáticamente a un usuario, puede que a veces el usuario no desee usarlo y que usted desee establecerlo en un número concreto, o que los usuarios no recuerden o hayan perdido su id. de conferencia. En esos casos, puede usar el centro de administración de Skype Empresarial y Windows PowerShell para ver, cambiar y restablecer su id. de conferencia.
  
    
    


Se enviará un correo electrónico al usuario con el id. de conferencia y con los números de teléfono de conferencia de acceso telefónico local predeterminados o, si restablece el id. de conferencia, se enviará un correo electrónico distinto que incluirá el id. de conferencia, pero no incluirá un PIN. 
  
    
    


## 


### Para ver el id. de conferencia

Puede ver el id. de conferencia de un usuario y enviárselo.
  
    
    

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
  
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
  
3. En **Centro de administración de Skype Empresarial**> **Conferencia de acceso telefónico local**, en la lista de usuarios, seleccione el usuario que necesita el Id. de conferencia.
    
  
4. En la página Acciones, busque en **Id. de conferencia**.
    
    > [!TIP]
      > Para enviar toda la información sobre la conferencia al usuario en un correo electrónico que incluya el id. de conferencia y los números de teléfono de acceso telefónico local, haga clic en el vínculo **Enviar información de conferencia por correo electrónico** después de seleccionar el usuario en la página **Usuarios de acceso telefónico local**. 

    Si quiere usar Windows PowerShell para ver el id. de conferencia de un usuario, ejecute:
    


  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```


    Para más información sobre el cmdlet, vea  [Get-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617693 ).
    
  

### Para asignar o cambiar el id. de conferencia

Puede asignar un id. de conferencia a un usuario o cambiarlo si, por ejemplo, alguien desea tener un id. de conferencia fácil de recordar.
  
    
    

> [!NOTE]
> El Centro de administración de Skype Empresarial no se puede usar para editar un id. de conferencia que se haya creado automáticamente, pero puede usar Windows PowerShell para editar o cambiar un id. de conferencia que haya establecido. 
  
    
    


- Para editar o cambiar el id. de conferencia de un usuario, ejecute:
    
    > [!TIP]
      > El id. de conferencia tiene que contener siete dígitos y no se puede cambiar en el Centro de administración de Skype Empresarial ni con Windows PowerShell. 

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```


### Para restablecer el id. de conferencia

Puede restablecer el id. de conferencia de un usuario, por ejemplo, si lo ha olvidado.
  
    
    

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
  
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
  
3. En el **Centro de administración de Skype Empresarial**> **Conferencias de acceso telefónico local**, en la página de acciones en **Id. de conferencia** haga clic en **Restablecer**.
    
  
4. En la ventana **¿Restablecer id. de conferencia?** haga clic en **Sí**. Se creará automáticamente un id. de conferencia y se enviará un correo electrónico al usuario con el nuevo id. de conferencia.
    
    Puede restablecer el id. de conferencias de un usuario si usa Windows PowerShell. Para ello, ejecute:
    


  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```


## ¿Qué más tengo que saber?


-     > [!IMPORTANT]
      >  Tras crear o restablecer un id. de conferencia, los autores de llamadas ya no podrán usar el id. de conferencia antiguo. Debe notificar a los usuarios que deberán volver a programar sus invitaciones a reuniones existentes para asegurarse de que el nuevo id. de conferencia se agrega a las invitaciones. Los usuarios pueden usar la herramienta de migración de reuniones de Skype Empresarial para actualizar sus reuniones existentes. Para saber cómo descargar, instalar y ejecutar la herramienta, vea:>  [Herramienta de actualización de reuniones para Skype y Lync](http://technet.microsoft.com/library/2b525fe6-ed0f-4331-b533-c31546fcf4d4%28Office.14%29.aspx)>  [Skype Empresarial Online, herramienta de migración de reuniones (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)>  [Skype Empresarial Online, herramienta de migración de reuniones (32 bits)](http://go.microsoft.com/fwlink/?LinkID=626046)
- Para más información sobre el cmdlet, vea  [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688 ).
    
  
- El id. de conferencia debe respetar la longitud en dígitos establecida en el puente de conferencias de acceso telefónico local. No puede usar caracteres alfabéticos o especiales en los id. de conferencia. Solo puede usar números.
    
  
- El id. de conferencia de todos los usuarios de conferencia de acceso telefónico local será de siete dígitos de manera predeterminada. Además, el número de dígitos no se puede cambiar.
    
  
- Si el usuario cambia desde Microsoft como el proveedor de conferencia de acceso telefónico local a un proveedor de servicios de audioconferencia de terceros o el proveedor se establece en **Ninguno**, el id. de conferencia dejará de funcionar. Vea  [Asignar a un tercero como el proveedor de conferencias de audio](assign-a-third-party-as-the-audio-conferencing-provider.md) o [Cambiar el proveedor de servicios de conferencia de acceso telefónico local para los usuarios](http://technet.microsoft.com/library/9b74f053-4d23-485f-9232-3d30370a8c6e%28Office.14%29.aspx).
    
  

## ¿Desea saber cómo administrar con Windows PowerShell?


- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  -  [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  
  -  [Seis razones por las podría desear usar Windows PowerShell para administrar Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  -  [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  
  -  [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  
  -  [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  

## See also


#### 


  
    
    
 [Set up Audio Conferencing for Skype for Business and Microsoft Teams](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
