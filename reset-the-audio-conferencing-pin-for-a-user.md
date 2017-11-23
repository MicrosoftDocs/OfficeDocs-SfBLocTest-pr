---
title: Restablecer el PIN de conferencia de acceso telefónico local de un usuario
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: How To
ms.service: OFFICE365
description: Find out what you should know about PINs and how to reset them for your users. 
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
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
---


# Restablecer el PIN de conferencia de acceso telefónico local de un usuario

Un PIN es un código formado por números que se crea para cada usuario habilitado para conferencias de acceso telefónico local. El PIN de conferencia de acceso telefónico local es usado por el organizador de la reunión para identificarse como el organizador de la reunión y permitirle iniciar una por teléfono. Si usa un cliente de Skype Empresarial para iniciar la reunión, no necesitará un PIN. Si un usuario olvida su PIN y no lo puede encontrar en el correo electrónico que se le envió cuando se habilitó su usuario para la conferencia de acceso telefónico local, el administrador tendrá que restablecer su PIN. Un usuario no puede restablecer su propio PIN.
  
    
    


Las reuniones se pueden iniciar cuando un usuario autenticado se une con un cliente de Skype Empresarial o cuando el organizador se une con su código PIN por teléfono. Cuando una reunión necesita un PIN para empezar, los usuarios que se unan a la reunión por teléfono se colocarán en la sala de espera y escucharán música en espera hasta que se inicie la reunión. Si el organizador de la reunión no necesita un PIN para iniciar la reunión por teléfono, a los autores de la llamada no se les pedirá un PIN cuando se unan a la reunión.
  
    
    


## 


  
    
    

### Restablecer el PIN del organizador de una conferencia


1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
  
2. Vaya al **Centro de administración de Office 365** > **Skype Empresarial** y, en el panel de navegación izquierdo, haga clic en **Conferencia de acceso telefónico local**.
    
  
3. Haga clic en **Usuarios de acceso telefónico local** y seleccione el usuario para el que quiera restablecer el PIN.
    
  
4. En el panel de acciones, haga clic en **Restablecer PIN**.
    
  

## ¿Qué más tiene que saber sobre los códigos PIN?


- Por motivos de seguridad, el PIN solo se muestra a un administrador una vez, cuando se restablece el PIN. Cuando un administrador restablezca el PIN, este aparecerá como *********** en el Centro de administración de Skype Empresarial y en los resultados cuando usen **Get-CsCsOnlineDialInConfencingUser** en Windows PowerShell.
    
  
- El envío automático de correos electrónicos a los usuarios está habilitado de manera predeterminada, y los usuarios recibirán un correo electrónico con su PIN cuando estén habilitados para la conferencia de acceso telefónico local o cuando se restablezca el PIN. Pero, si ha deshabilitado el envío automático de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN al usuario y tendrá que enviar de forma manual la información del PIN al usuario.
    
  
- Cuando se inicia una reunión, todos los usuarios de la sala de espera se unirán automáticamente. Por ejemplo, si los dos participantes intentan unirse a una reunión antes de que se haya iniciado, se enviarán a la sala de espera y escucharán música en espera y, cuando el organizador de la reunión se una con su PIN a través del teléfono, la reunión se iniciará y los participantes de la sala de espera se unirán a la reunión.
    
  
- La configuración predeterminada no permite que se inicie una reunión con autores de llamada anónimos.
    
  
- Al habilitar a un usuario para la conferencia de acceso telefónico local, de manera predeterminada se les enviarán correos electrónicos con información sobre la conferencia y con su PIN. Es necesario que el usuario tenga un buzón de Office 365 ya que, cuando se restablece un PIN, se enviará un nuevo PIN al usuario por correo electrónico a la dirección SMTP principal (alias) configurada para el usuario.
    
  
- Al configurar la conferencia de acceso telefónico local, establecerá los dígitos necesarios para los códigos PIN en su organización. Los códigos PIN pueden tener de 4 a 12 dígitos (el valor predeterminado es 5). Si cambia la configuración de longitud del PIN, la configuración solo se aplicará en los nuevos códigos PIN, pero no se aplicará en la configuración de PIN de los usuarios existentes que tengan habilitada la conferencia de acceso telefónico local. Vea  [Establecer la longitud del PIN para las reuniones de acceso telefónico local](set-the-length-of-the-pin-for-audio-conferencing-meetings.md)
    
  
- De manera predeterminada, el correo electrónico se establece en la dirección SMTP principal de Office 365 del usuario, aunque también se puede enviar un correo electrónico a una dirección que no sea de Office 365, como direcciones de Hotmail o MSN. Si usa Windows PowerShell, puede reemplazar la dirección de correo electrónico predeterminada. Esto es útil si los usuarios no tienen un buzón de Exchange en Office 365.
    
  
- Para reemplazar la dirección del usuario predeterminada donde se enviará el correo electrónico, el administrador del inquilino puede usar el siguiente cmdlet:  `Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com"`. Se necesita el parámetro  _SendEmail_ para reemplazar la dirección de correo electrónico del usuario.
    
  

## ¿Desea saber cómo administrar con Windows PowerShell?


- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet  [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688 ).
    
  
- Para establecer el PIN para Guillermo Rodarte, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
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

