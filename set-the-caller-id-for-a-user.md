---
title: Establecer el identificador de llamada de un usuario
ms.author: tonysmit
author: tonysmit
ms.date: 9/22/2017
ms.audience: Admin
ms.technology:
- Office 365 Enterprise admin
- Office 365 Midsize Business admin
- Office 365 Small Business admin
- Skype for Business
- Skype for Business admin center
- Skype for Business Online
ms.set-free-tag: Strat_SB_PSTN
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
---


# Establecer el identificador de llamada de un usuario

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la  [declinación de responsabilidades](c7323490-d9b7-421a-aa76-5bd485f80583.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo  [aquí](https://support.office.com/en-us/article/c7323490-d9b7-421a-aa76-5bd485f80583). 
  
    
    


El sistema telefónico en Office 365 proporciona un identificador de llamada predeterminado que es el número de teléfono asignados del usuario. Puede cambiar o bloquear el identificador de llamada (también denominado un identificador de línea de llamada) para un usuario. Obtener más información sobre cómo usar el identificador de su organización, vaya  [Cómo se puede usar la identificación de llamadas en su organización](how-can-caller-id-be-used-in-your-organization.md).
  
    
    


Hay algunos ajustes que puede cambiar:
  
    
    


> [!NOTE]
> Esto **no es** para las organizaciones locales con Lync o Skype Empresarial Server.
  
    
    


- **Cambiar el identificador de llamada saliente** Puede reemplazar el identificador de llamada de un usuario, que es de manera predeterminada su propio número de teléfono, por otro número de teléfono. Por ejemplo, puede cambiar el identificador de llamada del usuario de su número de teléfono a un número de teléfono principal de la empresa, o bien cambiar el identificador de línea de llamada del usuario de su número de teléfono a un número de teléfono principal del departamento jurídico. Puede cambiar el número del identificador de llamada por cualquier número de **servicio** en línea (de pago o gratuito).
    
    > [!NOTE]
      > Si desea usar el parámetro  _Service_, deberá especificar un número de servicio válido. 
- **Bloquear el identificador de llamada saliente** Puede impedir que el identificador de llamada saliente se envíe en las llamadas RTC salientes de un usuario. Al hacerlo, se bloqueará el número de teléfono para que no se muestre en el teléfono de la persona que llama.
    
  
- **Bloquear el identificador de llamada entrante** Puede impedir que el usuario reciba el identificador de llamada en las llamadas RTC entrantes.
    
  

> [!IMPORTANT]
> Las llamadas de emergencia siempre envían el número de teléfono de los usuarios (identificador de llamada). 
  
    
    


De manera predeterminada, estos ajustes del identificador de llamada están **desactivados**. Esto significa que el número de teléfono del usuario de Skype Empresarial Online se puede ver cuando el usuario realiza una llamada a un teléfono RTC.
  
    
    


Para obtener más información sobre esta configuración y cómo usarla, vaya  [Cómo se puede usar la identificación de llamadas en su organización](how-can-caller-id-be-used-in-your-organization.md).
  
    
    


## Establecer la configuración de la directiva de identificador de llamada


> [!NOTE]
> Para la configuración relativa al identificador de llamada en Skype Empresarial Online debe usar Windows PowerShell y **no** el **centro de administración de Skype Empresarial**. 
  
    
    


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
    
  

### Ver toda la configuración de directivas de identificador de llamada en su organización


- Para ver toda la configuración de directivas de identificador de llamada en su organización, ejecute:
    
  - 
  ```
  Get-CsCallingLineIdentity |fl
  ```


    Consulte más ejemplos y detalles sobre  [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).
    
  

### Crear una nueva directiva de identificador de llamada en su organización


- Para crear una nueva directiva de identificador de llamada que establezca el identificador de llamada en anónimo, ejecute:
    
  - 
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```


    Consulte más ejemplos y detalles sobre  [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).
    
  
- Para aplicar la nueva directiva a Amos Marble, ejecute:
    
  - 
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```


    Más información sobre el cmdlet  [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).
    
  
Si ya ha creado una directiva, puede usar el cmdlet  [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) para hacer cambios en la directiva existente y, a continuación, usar [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) para aplicar la configuración a los usuarios.
  
    
    

### Ajustar la directiva para bloquear el identificador de llamada entrante


- Para bloquear el identificador de llamada entrante, ejecute:
    
  - 
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```


    Consulte más ejemplos y detalles sobre  [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx).
    
  
- Para aplicar la configuración de la nueva directiva a un usuario de su organización, ejecute:
    
  - 
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```


    Más información sobre el cmdlet  [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).
    
  

### Quitar una directiva de identificación de llamadas

Para quitar una directiva de su organización, ejecute:
  
    
    

```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```

Para quitar una directiva de un usuario, ejecute:
  
    
    



```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```


## ¿Quiere saber más sobre Windows PowerShell?


- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  -  [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  
  -  [Seis razones por las podría desear usar Windows PowerShell para administrar Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  -  [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  
  -  [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  
  -  [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  

## Temas relacionados

 [Términos y condiciones de las llamadas de emergencias](emergency-calling-terms-and-conditions.md)
  
    
    
 [Audio Conferencing complimentary dial-out period](audio-conferencing-complimentary-dial-out-period.md)
  
    
    

## 
<a name="MT_Footer"> </a>


> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  
    
    


