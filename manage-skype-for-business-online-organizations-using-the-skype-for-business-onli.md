---
title: Administrar Skype para las organizaciones empresariales en línea con el Skype para Business Connector en línea
ms.author: crowe
author: crowe
ms.date: 5/17/2017
ms.audience: Admin
ms.topic: How To
ms.prod: SKYPEFORBUSINESS
description: Use Windows PowerShell and the Get-CsTenant and Get-CsTenantLicensingConfiguration cmdlets to get information about your Skype for Business Online tenant.
ms.collection: Adm_Skype4B_Online
ms.technology:
- Office 365 Enterprise admin
- Office 365 Midsize Business admin
- Office 365 Small Business admin
- Skype for Business
- Skype for Business Online
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
---


# Administrar Skype para las organizaciones empresariales en línea con el Skype para Business Connector en línea

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la  [declinación de responsabilidades](c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo  [aquí](https://support.office.com/en-us/article/c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a). 
  
    
    


Puede encontrar información sobre su inquilino Skype Empresarial Online usando los cmdlets **Get-CsTenant** y **Get-CsTenantLicensingConfiguration**.
  
    
    


## Administrar Skype empresarial Online inquilinos

Para obtener información sobre el inquilino Skype Empresarial Online, llame el cmdlet  [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sin ningún parámetro adicional.
  
    
    

```
Get-CsTenant
```


  
    
    
Para devolver el inquilino de al nombre e Id., utilice este comando.
  
    
    



```
Get-CsTenant | Select-Object Name, TenantID
```

El valor del parámetro  _TenantID_ se requiere cuando se ejecuta cmdlets como [Conjunto CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) y [Establecer CsTenantFederationConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849602).
  
    
    
Para obtener información acerca de la información de licencia del inquilino especificado está disponible en el centro de administración de Skype Empresarial Online, use el cmdlet  [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .
  
    
    

## 
<a name="MT_Footer"> </a>


> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  
    
    


