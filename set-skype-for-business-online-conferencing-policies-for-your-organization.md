---
title: Establecer directivas de conferencia de Skype Empresarial Online en su organización
ms.author: tonysmit
author: tonysmit
ms.date: 2/22/2017
ms.audience: Admin
ms.technology:
- Office 365 Enterprise admin
- Office 365 Midsize Business admin
- Office 365 Small Business admin
- Skype for Business
- Skype for Business Online
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
---


# Establecer directivas de conferencia de Skype Empresarial Online en su organización

El servicio de conferencias es una parte importante de Skype Empresarial Online: mediante las conferencias, los grupos de usuarios pueden reunirse en línea para ver diapositivas y vídeo, compartir aplicaciones, cederse archivos, y colaborar y comunicarse de otros modos.
  
    
    


Es importante que mantenga el control sobre las conferencias y su configuración. En algunos casos puede ser necesario cierto grado de seguridad, pues, de forma predeterminada, todos los usuarios, incluidos los no autenticados, pueden participar en las reuniones, y guardar las diapositivas y documentos informativos que se distribuyan en ellas. Además, es posible que deban tenerse en cuenta aspectos legales. Por ejemplo, de forma predeterminada, los participantes de una reunión pueden hacer anotaciones en el contenido compartido; sin embargo, estas anotaciones no se guardan al archivar la reunión. Si su organización debe conservar un registro de toda la comunicación electrónica, es posible que prefiera desactivar las anotaciones. 
  
    
    


En Skype Empresarial Online las conferencias se administran mediante directivas de conferencia. Las directivas de conferencia determinan las funcionalidades y características que se pueden usar en una conferencia y cubren todos los aspectos, desde si la conferencia puede incluir o no audio y vídeo IP, hasta el número máximo de personas que pueden asistir a una reunión. Las directivas de conferencia se pueden configurar para que tengan aplicación global o por usuario. Esto ofrece a los administradores una enorme flexibilidad a la hora de decidir qué características podrán usar qué usuarios.
  
    
    


La configuración de las directivas se puede establecer al mismo tiempo que se crea la directiva o posteriormente, usando el cmdlet **Set-CsConferencingPolicy** para modificar los ajustes de una directiva existente.
  
    
    


## Establecer las directivas de conferencia


> [!NOTE]
> Para la configuración de directivas de conferencia en Skype Empresarial Online debe usar Windows PowerShell y **no** el **centro de administración de Skype Empresarial**. 
  
    
    


  
    
    

### Verificar e iniciar Windows PowerShell


- **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
    
1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
    
  
2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
  
3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea  [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
    
  
4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en  [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
  

    Si necesita más información, consulte  [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
  
- **Iniciar una sesión de Windows PowerShell**
    
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
    
  

### Bloquear la transferencia de archivos y el uso compartido de escritorios durante las reuniones


- Para crear una nueva directiva para esta configuración, ejecute:
    

  
    
    
> 
  ```
  New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
  ```


    Más información sobre el cmdlet  [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx).
    
  
- Para aplicar la nueva directiva a todos los usuarios de la organización, ejecute:
    

  
    
    
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
  ```


    Más información sobre el cmdlet  [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx).
    
  
Si ya ha creado una directiva, puede usar el cmdlet  [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para hacer cambios en la directiva existente y, a continuación, usar [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar la configuración a los usuarios.
  
    
    

### Bloquear la grabación de conferencias e impedir la presencia de participantes anónimos en las reuniones


- Para crear una nueva directiva para esta configuración, ejecute:
    

  
    
    
> 
  ```
  New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
  ```


    Más información sobre el cmdlet  [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx).
    
  
- Para aplicar la nueva directiva a Amos Marble, ejecute:
    

  
    
    
> 
  ```
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
  ```


    Más información sobre el cmdlet  [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx).
    
  
Si ya ha creado una directiva, puede usar el cmdlet  [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para hacer cambios en la directiva existente y, a continuación, usar [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar la configuración a los usuarios.
  
    
    

### Impedir que los participantes anónimos puedan grabar reuniones y que los usuarios externos puedan guardar contenido de las reuniones


- Para crear una nueva directiva para esta configuración, ejecute:
    

  
    
    
> 
  ```
  New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
  ```


    Más información sobre el cmdlet  [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx).
    
  
- Para aplicar la nueva directiva a todos los usuarios de la organización, ejecute:
    

  
    
    
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
  ```


    Más información sobre el cmdlet  [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx).
    
  
Si ya ha creado una directiva, puede usar el cmdlet  [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para hacer cambios en la directiva existente y, a continuación, usar [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar la configuración a los usuarios.
  
    
    

## ¿Quiere saber más sobre Windows PowerShell?


- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  -  [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  
  -  [Seis razones por las podría desear usar Windows PowerShell para administrar Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  -  [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  
  -  [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  
  -  [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  

