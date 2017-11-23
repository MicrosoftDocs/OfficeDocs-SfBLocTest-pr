---
title: Llamar a los problemas conocidos de planes
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 10/27/2017
ms.audience: Admin
ms.topic: Troubleshooting
ms.prod: SKYPEFORBUSINESS
description: Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. 
ms.collection: Adm_Skype4B_Online
ms.technology: Skype for Business admin center
ms.set-free-tag: Adm_O365_FullSet
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
---



# Llamar a los problemas conocidos de planes

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la  [declinación de responsabilidades](baa3645a-0518-472e-942e-971c63ba4ca0.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo  [aquí](https://support.office.com/en-us/article/baa3645a-0518-472e-942e-971c63ba4ca0). 
  
    
    


Planes de llamada en Office 365 son una nueva característica que se encuentra en Skype Empresarial Online. Existen problemas actuales que se realiza un seguimiento, conocidas investigar y se potencialmente resolverá cuando la característica se actualiza en futuras versiones de Office 365 y Skype Empresarial Online y se muestran a continuación.
  
    
    


## Llamar a los problemas conocidos de planes



|**Problema conocido**|**Comentarios**|
|:-----|:-----|
|Realizar la transición de Technical Preview licencias a licencias de producción para llamar a los planes no actualizan automáticamente la licencia.  <br/> |Comprar sus nuevas licencias en primer lugar, por lo que está listos para asignar a los usuarios. Quitar la licencia de promoción (Technical Preview) a un usuario y asignar **inmediatamente** las nuevas licencias de **Llamar a planear nacionales** o **Llamar a planear internacional** al usuario. <br/> Si va a quitar y agregar licencias para varios usuarios, es muy importante que quite las licencias de todos los usuarios que usen Windows PowerShell y que después asigne **INMEDIATAMENTE** las licencias de todos los usuarios que usen Windows PowerShell. De este modo se asegura de que no haya interrupciones en el servicio al gestionar grandes volúmenes de asignaciones de licencias de usuario. Para ver muestras de scripts de PowerShell, consulte [Asignar Skype para Business y Microsoft Teams licencias](assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> > [!NOTE]> Si está utilizando la conectividad de RTC local para usuarios de híbrido,  *solo*  tendrán que asigne una licencia de **Sistema telefónico**. **No** debe asignar también un plan de llamadas de voz.> Sin embargo, si va a habilitar llamar a los planes de Office 365 para los usuarios que están en Office 365, debe seguir asignar una licencia de **Llamar a planear nacionales** o **Llamar a planear internacional** para esos usuarios. Vea [Asignar Skype para Business y Microsoft Teams licencias](assign-skype-for-business-and-microsoft-teams-licenses.md).           |
   

## Temas relacionados

 [Términos y condiciones de las llamadas de emergencias](emergency-calling-terms-and-conditions.md)
  
    
    
 [Audio Conferencing complimentary dial-out period](audio-conferencing-complimentary-dial-out-period.md)
  
    
    

## 
<a name="MT_Footer"> </a>


> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  
    
    

