---
title: Habilitar la Difusión de reunión de Skype
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 6/1/2017
ms.audience: Admin
ms.topic: Setup/Install
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.technology:
- Office 365 Enterprise admin
- Office 365 Midsize Business admin
- Office 365 Small Business admin
- Skype for Business
- Skype for Business admin center
- Skype for Business Online
ms.set-free-tag:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
---


# Habilitar la Difusión de reunión de Skype

Antes de que los miembros de su organización puedan usar Difusión de reunión de Skype, usted deberá habilitarla. Para llevar a cabo este paso, tiene que saber cómo usar Windows PowerShell. Si no tiene experiencia con Windows PowerShell, analice contratar un  [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.
  
    
    


> [!CAUTION]
> Difusión de reunión de Skype está desactivada de manera predeterminada porque la distribución del contenido multimedia de una reunión de difusión usa Red de entrega de contenido (CDN) de Microsoft Azure para conseguir una escala realmente elevada y ser compatible con las miles de personas que están viendo la difusión. El contenido multimedia agrupado que pasa a través de la CDN está cifrado, y el caché de CDN tiene un tiempo de vida limitado. Además, es posible que el componente de CDN de Azure todavía no satisfaga todos los elementos de las cláusulas modelo de la UE que deriva de la Directiva de protección de datos de la UE. Al habilitar esta característica, da por hecho que conoce esta advertencia. 
  
    
    


## Habilitar Difusión de reunión de Skype mediante el Centro de administración de Skype Empresarial


1. Inicie sesión con su cuenta de administrador global de Office 365 en  [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
  
2. En el Centro de administración de Office 365, vaya a **Centros de administración** > **Skype Empresarial**.
    
  
3. En el **Centro de administración de Skype Empresarial** > **Reuniones en línea** > **Difusión de reuniones**. Después, haga clic en **Habilitar Difusión de reunión de Skype**.
    
  

## Habilitar la Difusión de reunión de Skype mediante PowerShell


1. Compruebe que está ejecutando la versión 3.0 o superior de Windows PowerShell.
    
1. Para comprobar que ejecuta la versión 3.0 o superior: **menú Inicio** > **Windows PowerShell**.
    
  
2. Compruebe la versión escribiendo  _Get-Host_ en la ventana de **Windows PowerShell**.
    
  
3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea  [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
    
  
4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en  [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
  
2. En el **menú Inicio** > **Windows PowerShell**.
    
  
3. En la ventana de **Windows PowerShell** y conéctese a su organización de Office 365 ejecutando el siguiente comando:
    
  ```
  $Credential = get-credential
  ```


  ```
  $O365Session = New-CsOnlineSession -Credential $credential
  ```


  ```
  Import-PSSession $O365Session
  ```

4. Confirme la configuración actual de Difusión de reunión de Skype ejecutando el siguiente comando:
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```


    Compruebe que el parámetro  _EnableBroadcastMeeting_ está establecido como `False`.
    
     ![Habilitar cmdlet de organización en una Difusión de reunión de Skype.](images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  

  

  
5. Habilite la Difusión de reunión de Skype para su organización ejecutando el siguiente comando:
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```


    Puede confirmar que la opción está habilitada volviendo a ejecutar  `Get-CsBroadcastMeetingConfiguration`.
    
     ![Habilitar cmdlet de organización en una Difusión de reunión de Skype.](images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  

    
    > [!TIP]
      > Después de realizar el cambio, es posible que tarde hasta una hora en surtir efecto en el portal de Difusión de reunión de Skype. 
6. Los usuarios ahora pueden realizar reuniones de difusión con otros usuarios de su empresa. Para que puedan empezar, pídales que lean  [¿Qué es una Difusión de reunión de Skype?](http://technet.microsoft.com/library/c472c76b-21f1-4e4b-ab58-329a6c33757d%28Office.14%29.aspx)
    
  

## Configurar su red para difundir reuniones con asistentes externos

Si tiene un firewall y quiere realizar difusiones con personas que no pertenecen a su empresa (que no son una empresa federada), tendrá que configurar su red con estas instrucciones:  [Configurar la red para Difusión de reunión de Skype](set-up-your-network-for-skype-meeting-broadcast.md). 
  
    
    
Si no tiene experiencia con la configuración del firewall, analice contratar un  [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.
  
    
    
Para omitir este paso y, en su lugar, agregar otra empresa a su federación, siga los pasos en  [Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md). 
  
    
    

## See also


#### 


  
    
    
 [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
    
    
 [Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)
