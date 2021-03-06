---
title: ¿Cuántos números de teléfono puede obtener?
ms.author: tonysmit
author: tonysmit
ms.date: 9/25/2017
ms.technology:
- Office 365 Enterprise admin
- Office 365 Midsize Business admin
- Office 365 operated by 21Vianet - Small Business admin
- Skype for Business Online
- Skype for Business Online admin center
ms.set-free-tag: Strat_SB_PSTN
ms.assetid: 61dfb27c-5bfa-4481-a930-9c026e73ff3a
---



# ¿Cuántos números de teléfono puede obtener?

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la  [declinación de responsabilidades](61dfb27c-5bfa-4481-a930-9c026e73ff3a.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo  [aquí](https://support.office.com/en-us/article/61dfb27c-5bfa-4481-a930-9c026e73ff3a). 
  
    
    


Al obtener números de teléfono para su organización, puede obtener más números de teléfono que los que le corresponden por las licencias que tiene asignadas. Sin embargo, esto depende de los tipos de números de teléfono y del tipo de licencias que ha adquirido y asignado.
  
    
    


Puede ver la cantidad de números de teléfono que puede obtener en la página **Números de teléfono** del Centro de administración de Skype Empresarial o bien puede ejecutar el cmdlet [Get-CsOnlineTelephoneNumberAvailableCount](https://technet.microsoft.com/en-us/library/mt634605.aspx). 
  
    
    


> [!IMPORTANT]
> Los siguientes límites no incluyen números de teléfono en los que haya realizado portabilidad o que haya transferido a Microsoft. 
  
    
    


## ¿Cuántos números de teléfono puede obtener?


||||
|:-----|:-----|:-----|
|**Este es el tipo de número de teléfono** <br/> |**¿Cómo se obtiene el total de números de teléfono?** <br/> |**Este es un ejemplo** <br/> |
|Número de usuario (suscriptor)  <br/> |El número de números de teléfono es igual que el número total de **Llamar a planear nacionales** o reciben licencias **Llamar a planear internacional** multiplicados por 1.1 + 10 números de teléfono adicionales. <br/> |Si tengo 50 usuarios en total con una bien llamar a planear nacionales o llamar a planear internacional, puede adquirir el número de teléfono de **65** **(1.1 x 50 + 10)**. <br/> |
|Número de servicio de pago  <br/> | El número de números de teléfono es igual a la cantidad de licencias de **Sistema telefónico** y **Conferencias de Audio** y usa la siguiente: <br/>  Si hay **1-25 licencias**, se proporcionan **5** números de teléfono. <br/>  Si hay **26-49 licencias**, se proporcionan **10** números de teléfono. <br/>  Si hay **50-99 licencias**, se proporcionan **20** números de teléfono. <br/>  Si hay **100-149 licencias**, se proporcionan **30** números de teléfono. <br/>  Si hay **150-199 licencias**, se proporcionan **40** números de teléfono. <br/>  Si hay **200-499 licencias**, se proporcionan **65** números de teléfono. <br/>  Si hay **500-749 licencias**, se proporcionan **90** números de teléfono. <br/>  Si hay **750-999 licencias**, se proporcionan **110** números de teléfono. <br/>  Si hay **1.000-1.249 licencias**, se proporcionan **125** números de teléfono. <br/>  Si hay **1.250-1.499 licencias**, se proporcionan **135** números de teléfono. <br/>  Si hay **1.500-1.999 licencias**, se proporcionan **160** números de teléfono. <br/>  Si hay **2.000-2.999 licencias**, se proporcionan **210** números de teléfono. <br/>  Si hay **3.000-6.999 licencias**, se proporcionan **420** números de teléfono. <br/>  Si hay **7.000-9.999 licencias**, se proporcionan **500** números de teléfono. <br/>  Si hay **10.000-14.999 licencias**, se proporcionan **600** números de teléfono. <br/>  Si hay **15.000-19.999 licencias**, se proporcionan **700** números de teléfono. <br/>  Si hay **20.000-49.999 licencias**, se proporcionan **1000** números de teléfono. <br/>  Si hay **más de 50.000**, se proporcionan **1.500** números de teléfono. <br/> |Si tiene un total de **51** licencias de **Sistema telefónico** y **Conferencias de Audio** puede obtener números de servicio de pago de **20**. <br/> |
|Número de servicio gratuito  <br/> | El número de números de teléfono es igual a la cantidad de licencias de **Sistema telefónico** y **Conferencias de Audio** y usa la siguiente: <br/>  Si hay **1-25 licencias**, se proporcionan **5** números de teléfono. <br/>  Si hay **26-49 licencias**, se proporcionan **10** números de teléfono. <br/>  Si hay **50-99 licencias**, se proporcionan **20** números de teléfono. <br/>  Si hay **100-149 licencias**, se proporcionan **30** números de teléfono. <br/>  Si hay **150-199 licencias**, se proporcionan **40** números de teléfono. <br/>  Si hay **200-499 licencias**, se proporcionan **65** números de teléfono. <br/>  Si hay **500-749 licencias**, se proporcionan **90** números de teléfono. <br/>  Si hay **750-999 licencias**, se proporcionan **110** números de teléfono. <br/>  Si hay **1.000-1.249 licencias**, se proporcionan **125** números de teléfono. <br/>  Si hay **1.250-1.499 licencias**, se proporcionan **135** números de teléfono. <br/>  Si hay **1.500-1.999 licencias**, se proporcionan **160** números de teléfono. <br/>  Si hay **2.000-2.999 licencias**, se proporcionan **210** números de teléfono. <br/>  Si hay **3.000-6.999 licencias**, se proporcionan **420** números de teléfono. <br/>  Si hay **7.000-9.999 licencias**, se proporcionan **500** números de teléfono. <br/>  Si hay **10.000-14.999 licencias**, se proporcionan **600** números de teléfono. <br/>  Si hay **15.000-19.999 licencias**, se proporcionan **700** números de teléfono. <br/>  Si hay **20.000-49.999 licencias**, se proporcionan **1000** números de teléfono. <br/>  Si hay **más de 50.000**, se proporcionan **1.500** números de teléfono. <br/> |Si tiene un total de licencias de **Conferencias de Audio** y **Sistema telefónico** **1001** puede obtener números de servicio gratuito de **125**. <br/> > [!IMPORTANT]>  [Configurar comunicaciones créditos para su organización](set-up-communications-credits-for-your-organization.md) es necesaria para reservar y utiliza los números de teléfono gratuito.          |
   

> [!NOTE]
> Si necesita obtener más números de teléfono, consulte  [Póngase en contacto con el soporte de Office 365 para empresas: ayuda para administradores](http://technet.microsoft.com/library/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b%28Office.14%29.aspx). 
  
    
    


## 
<a name="MT_Footer"> </a>


> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  
    
    

