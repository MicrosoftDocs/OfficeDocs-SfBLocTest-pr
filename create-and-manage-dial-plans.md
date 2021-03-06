---
title: Crear y administrar planes de marcado
ms.author: tonysmit
author: tonysmit
ms.date: 9/22/2017
ms.audience: Admin
description: Learn how to create calling dial plans (PSTN Calling dial plans) in Office 365 and how to manage them. 
ms.technology:
- Office 365 Enterprise admin
- Office 365 Midsize Business admin
- Office 365 Small Business admin
- Skype for Business
- Skype for Business admin center
- Skype for Business Online
ms.set-free-tag: Strat_SB_PSTN
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
---


# Crear y administrar planes de marcado

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la  [declinación de responsabilidades](7af17c94-5f8f-4452-ae1d-01f495b4dc94.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo  [aquí](https://support.office.com/en-us/article/7af17c94-5f8f-4452-ae1d-01f495b4dc94). 
  
    
    


Después de haber planeado los planes de marcado para su organización y descubrió todas las reglas de normalización necesitan creadas para el enrutamiento de llamadas, debe usar Windows PowerShell para crear los planes de marcado y realice los cambios de configuración.
  
    
    


> [!NOTE]
> Los planes de marcado no se pueden crear y administrar en el centro de administración de Skype Empresarial. 
  
    
    


## Verificar e iniciar PowerShell remoto

 **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
  
    
    

1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
    
  
2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
  
3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea  [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
    
  
4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en  [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
  
Si necesita más información, consulte  [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
  
    
    
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
  
    
    

## Crear y administrar sus planes de marcado

Para crear y administrar planes de marcado de inquilino puede utilizar un cmdlet sencillo o un script de PowerShell.
  
    
    

### Uso de cmdlets sencillos


- Para crear un nuevo plan de marcado, ejecute:
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```


    Para ver otros ejemplos y parámetros, consulte  [Nuevo-CsPlanMarcadoInquilinio](https://technet.microsoft.com/library/mt775026.aspx).
    
  
- Para cambiar la configuración en un plan de marcado, ejecute:
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```


    Para ver otros ejemplos y parámetros, consulte [Configurar-CsPlanMarcadoInquilino](https://technet.microsoft.com/library/mt775023.aspx).
    
  
- Para agregar usuarios a un plan de marcado, ejecute:
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```


    Para ver otros ejemplos y parámetros, consulte  [Garantizar-CsPlanMarcadoInquilino](https://technet.microsoft.com/library/mt775021.aspx).
    
  
- Para ver la configuración de un plan de marcado, ejecute:
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```


    Para ver otros ejemplos y parámetros, consulte [Obtener-CsPlanMarcadoInquilino](https://technet.microsoft.com/library/mt775024.aspx).
    
  
- Para eliminar un plan de marcado, ejecute:
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```


    Para ver otros ejemplos y parámetros, consulte  [Eliminar-CsPlanMarcadoInquilino](https://technet.microsoft.com/library/mt775020.aspx).
    
  
- Para ver la configuración del plan de marcado efectivo, ejecute:
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```


    Para ver otros ejemplos y parámetros, consulte  [Obtener-CsPlanMarcadoEfectivoInquilino](https://technet.microsoft.com/library/mt775022.aspx).
    
  
- Para evaluar la configuración efectiva de un plan de marcado, ejecute:
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```


    Para ver otros ejemplos y parámetros, consulte  [Probar-CsPlanMarcadoEfectivoInquilino](https://technet.microsoft.com/library/mt775025.aspx).
    
  

### Uso de un script de PowerShell

Ejecute esto para eliminar una regla de normalización que esté asociada con un plan de marcado inquilino sin que tenga que eliminar en primer lugar el plan de marcado inquilino:
  
    
    

```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
```


```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
```


```
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
```


```
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
```


```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```

Ejecute esto para agregar la siguiente regla de normalización al plan de marcado inquilino existente denominado RedmondDialPlan. 
  
    
    



```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
```




```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```

Ejecute esto para eliminar la siguiente regla de normalización del plan de marcado inquilino existente denominado RedmondDialPlan.
  
    
    



```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
```




```
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

Ejecute lo siguiente cuando también desee examinar las reglas de normalización existentes, determine cuál desea eliminar y después utilice el índice para eliminarlo. La matriz de reglas de normalización comienza con el índice 0. Nos gustaría eliminar la regla de normalización de tres dígitos, por lo que se trata del índice 1.
  
    
    



```
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
```




```
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False
```




```
$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
```




```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Ejecute esto para buscar todos los usuarios a los que se les ha garantizado el plan de marcado inquilino RedmondDialPlan.
  
    
    



```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Ejecute estos para agregar el plan de marcado local existente denominado OPDP1 como un plan de marcado inquilino para su organización. En primer lugar debe guardar el plan de marcado local como un archivo xml y, a continuación, úselo para crear el nuevo plan de marcado inquilino.
  
    
    
Ejecute esto para guardar el plan de marcado local como el archivo xml.
  
    
    



```
$DPName = "OPDP1"
```




```
$DPFileName = "dialplan.xml"
```




```
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

Ejecute esto para crear el nuevo plan de marcado inquilino.
  
    
    



```
$DPFileName = "dialplan.xml"
```




```
$DP = Import-Clixml $DPFileName
```




```
$NormRules = @()
```




```
ForEach($nr in $dp.NormalizationRules)
```




```
{
```




```
 $id1 = "Global/" +$nr.Name
```




```
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
```




```
$NormRules += $nr2
```




```
}
```




```
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```


## ¿Quiere saber más sobre Windows PowerShell?


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
  
    
    


## See also
<a name="MT_Footer"> </a>


#### 


  
    
    
 [Marco de operaciones de Skype](https://www.skypeoperationsframework.com/)
