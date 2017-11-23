---
title: Crear una cola de llamada del sistema telefónico
ms.author: tonysmit
author: tonysmit
ms.date: 10/25/2017
description: Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. 
ms.technology:
- Office 365 Enterprise admin
- Office 365 Midsize Business admin
- Office 365 Small Business admin
- Skype for Business
- Skype for Business admin center
- Skype for Business Online
- Skype for Business Online admin center
ms.set-free-tag: Strat_SB_PSTN
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
---



# Crear una cola de llamada del sistema telefónico

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la  [declinación de responsabilidades](67ccda94-1210-43fb-a25b-7b9785f8a061.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo  [aquí](https://support.office.com/en-us/article/67ccda94-1210-43fb-a25b-7b9785f8a061). 
  
    
    


Colas de llamada de teléfono sistema incluyen saludos que se usan cuando alguien le llama a un número de teléfono para su organización, la capacidad de automáticamente poner las llamadas en espera y buscar para el siguiente agente de llamada disponibles controlar la llamada cuando las personas que están de llamada escuchar música en espera. Puede crear una llamada de una o varias colas para su organización.
  
    
    


Pueden proporcionar colas de llamada del sistema de teléfono:
  
    
    


- Un mensaje de saludo empresarial.
    
  
- Música que se reproduce mientras los usuarios se mantienen a la espera.
    
  
- Redireccionamiento de llamadas a agentes de llamadas en listas de distribución habilitadas para correo electrónico y grupos de seguridad.
    
  
- Posibilidad de realizar ajustes del tamaño máximo de las colas de llamadas, tiempos de espera y opciones de administración de llamadas.
    
  

Cuando alguien llama a un número de teléfono que tiene configurada una cola de llamadas, el autor de la llamada oye primero un mensaje de saludo (si se ha configurado uno) y después la llamada se pone en la cola, donde esperará hasta que un agente de llamadas esté disponible. El autor de la llamada escuchará música mientras está en espera, y las llamadas se ofrecerán a los agentes de llamadas según el principio de  *primero en entrar, primero en salir*  (FIFO).
  
    
    


Todas las llamadas que se encuentran en espera en la cola se distribuyen usando un modo de enrutamiento a los operadores:
  
    
    


- La primera llamada de la cola sonará a todos los agentes de llamadas al mismo tiempo.
    
    > [!NOTE]
      > No se llamará a los agentes de llamadas que estén **sin conexión** o hayan establecido su presencia en ** No molestar**. 
- Solo se enviará a los agentes de llamadas una notificación de llamada entrante cada vez (la de la llamada que se encuentra en primer lugar de la cola).
    
  
- Después de que un agente de llamadas acepte la llamada, la siguiente llamada entrante de la cola se enviará a los demás agentes de llamadas.
    
  

## Paso 1: tareas iniciales

Para comenzar a utilizar colas de llamadas, es importante recordar algunas cosas:
  
    
    

- Licencia Enterprise E5 o una licencia Enterprise E3 plus **Sistema telefónico**, debe tener su organización (como mínimo). El número de licencias de usuario de **Sistema de teléfono** asignados desventajas el número del servicio de números que está disponible para utilizarse para colas de llamada. El número de colas de llamada que puede tener depende del número de licencias de **Sistema telefónico** y **Conferencias de Audio** que se asignan en su organización. Para obtener más información sobre licencias, vaya [Skype para Business y Microsoft Teams licencias de complemento](skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
      > Para desviar llamadas a las personas de su organización que están en línea, deben tener una licencia de **Sistema telefónico** y estar habilitadas para telefonía IP empresarial o tiene Office 365 llamar a los planes. Vea [Asignar Skype para Business y Microsoft Teams licencias](assign-skype-for-business-and-microsoft-teams-licenses.md). Para habilitarlos para telefonía IP empresarial, puede usar Windows PowerShell. Ejecutar por ejemplo:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
- Para obtener más información sobre planes de llamada de Office 365, consulte  [¿Qué planes de llamada en Office 365?](what-are-calling-plans-in-office-365.md) y [Calling Plans for Office 365](calling-plans-for-office-365.md)
    
    > [!NOTE]
      > Los usuarios locales que utilicen Skype Empresarial Server 2015 o Lync Server 2013 y 2010 no se pueden utilizar como agentes de colas de llamadas. 
- Solo puede asignar un pago y colas de llamadas de números de teléfono de un servicio gratuito que obtuvo en el **Skype centro de administración de la empresa** o transfieren desde otro proveedor de servicios al sistema telefónico. Para obtener y utilizar números gratuitos de servicio, debe configurar créditos de comunicaciones. Además, si desea que la cola de llamada para llamar a un número de RTC (en lugar de transferir la llamada a un usuario), llamadas salientes de RTC se cargarán por minuto con créditos de comunicación independientemente de si es la llamada de salida a un número de teléfono nacionales e internacionales. Para ello, consulte [¿Qué son créditos de comunicaciones?](what-are-communications-credits.md) y [Configurar comunicaciones créditos para su organización](set-up-communications-credits-for-your-organization.md).
    
    > [!NOTE]
      > Los números de teléfono de usuario (suscriptor) no se pueden asignar a las colas de llamadas; solo se pueden usar números de teléfono de servicio de pago y gratuitos. 

- Cuando se distribuye las llamadas entrantes de una cola de llamada de sistema telefónico, estos clientes son compatibles para los agentes de llamada:
    
  - Cliente de escritorio de Skype Empresarial 2016 (versiones de 32 y 64 bits)
    
  
  - Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)
    
  
  - Todos los modelos de teléfonos IP admitidos para Skype Empresarial Online. Consulte  [Obtener teléfonos con Skype Empresarial Online](getting-phones-for-skype-for-business-online.md).
    
  
  - Mac Skype empresarial Client (versión 16.8.196 y posteriores)
    
  
  - Android Skype empresarial Client (versión 6.16.0.9 y posteriores)
    
  
  - iPhone Skype empresarial Client (versión 6.16.0 y posteriores)
    
  
  - iPad Skype empresarial Client (versión 6.16.0 y posteriores)
    
  

## Paso 2: obtener o transferir números de servicio de pago o gratuitos

Antes de crear y configurar sus colas de llamadas, deberá obtener los números de servicio de pago o gratuitos, o transferir los existentes. Después de obtener los números de servicio de pago o gratuitos, estos se mostrarán en el **Centro de administración de Skype Empresarial** > **Voz** > **ficha Números de teléfono** y en el **Tipo de número** se indicará **Servicio - Número gratuito**. Para obtener los números de servicio, consulte  [Obtener números de teléfono de servicio de Skype Empresarial](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) o, si desea transferir un número de servicio existente, consulte [Números de teléfono de transferencia a Office 365](transfer-phone-numbers-to-office-365.md).
  
    
    

> [!NOTE]
> Si usted se encuentra fuera de los EE. UU., no podrá usar el Centro de administración de Skype Empresarial para obtener números de servicio. En su lugar, vaya  [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization.md) para ver cómo realizar esta acción desde fuera de los EE. UU.
  
    
    


## Paso 3: crear una cola de llamadas nueva

En el **Centro de administración de Skype Empresarial**, haga clic en **Enrutamiento de llamadas** > **Colas de llamadas**, y después en **Agregar nueva**:
  
    
    

### Definir el nombre para mostrar de la cola de llamadas, el número de teléfono y el dominio (si disponible)


  
    
    
![Setting up a call queue.](images/37ecc300-a108-4294-8463-fce570dfce72.png)
  
    
    

  
    
    

|||
|:-----|:-----|
|**1** <br/> |**Nombre**: introduzca un nombre para mostrar descriptivo para la cola de llamadas. Este campo es obligatorio y puede tener hasta 64 caracteres, espacios incluidos.  <br/> Este nombre se mostrará en la notificación de la llamada entrante.  <br/> |
|**2** <br/> |**Número de teléfono**: seleccione un número de servicio de pago o gratuito para la cola de llamadas. Este campo es obligatorio.  <br/> Si no se enumera ninguno, deberá obtener los números de servicio para poder crear esta cola de llamadas. Para obtener los números de servicio, consulte  [Obtener números de teléfono de servicio de Skype Empresarial](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) <br/> |
|**3** <br/> |**Dominio**: si está disponible, elija el dominio de Office 365 que desee usar. Esta opción solo está disponible si tiene más de un dominio en uso con Office 365. Si tiene más de uno, deberá elegir un nombre de dominio de la lista.  <br/> Por ejemplo, puede tener un dominio como:  _contoso.com or redmond.contoso.com_.  <br/> |
   

### Establecer el mensaje de saludo y la música que se debe reproducir durante el tiempo en espera

![Setting up a call queue.](images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
    
    

  
    
    

  
    
    

|||
|:-----|:-----|
|**1** <br/> |**Saludo**: este campo es opcional. Es el saludo que se reproduce para las personas que realizan una llamada al número de la cola de llamadas.  <br/> Puede cargar un archivo de audio (en el formato .wav, .mp3 o .wma).  <br/> |
|**2** <br/> |**Música en espera**: puede utilizar la música en espera predeterminada que se suministra con la cola de llamadas o cargar un archivo de audio en el formato .wav, mp3 o .wma para utilizarlo como su música en espera personalizada.  <br/> |
   

### Agregar agentes de llamadas a una cola de llamadas

![Set up call queues.](images/9c0c551b-218b-4268-9b73-c85000c99296.png)
  
    
    

  
    
    

  
    
    

|||
|:-----|:-----|
|**1** <br/> | Agentes de llamadas (50 como máximo) pueden ser: <br/>  Un usuario en línea con una licencia de **Sistema telefónico** y estar habilitada para telefonía IP empresarial o tiene un Plan de llamada. <br/> > [!NOTE]>  Para desviar llamadas a las personas de su organización que están en línea, deben tener una licencia de **Sistema telefónico** y estar habilitadas para telefonía IP empresarial o tiene un Plan de llamada. Vea [Asignar Skype para Business y Microsoft Teams licencias](assign-skype-for-business-and-microsoft-teams-licenses.md). Para habilitarlos para telefonía IP empresarial, puede usar Windows PowerShell. Ejecutar por ejemplo:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`           Usuarios en línea con una con una licencia de **Sistema telefónico** o una llamada Plan que se agregan a una lista de distribución o grupo de seguridad habilitados para correo. Puede tardar hasta 30 minutos para un nuevo agente de agregado de una lista de distribución o un grupo de seguridad para empezar a recibir llamadas de una cola de la llamada. Un grupo de seguridad o lista de distribución recién creado puede tardar hasta 48 horas esté disponible para su uso con colas de llamada. <br/> > [!NOTE]>  Office 365 (grupos moderna) no se pueden usar con colas de llamada.          > [!NOTE]>  Los usuarios locales que utilicen Skype Empresarial Server 2015 o Lync Server 2013 y 2010 no son compatibles.          |
   

### Establecer el tamaño máximo de cola y el tiempo de espera máximo

![Set up a call queue.](images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
    
    

  
    
    

  
    
    

|||
|:-----|:-----|
|**1** <br/> |**Número máximo de llamadas en la cola**: use esta opción para establecer el número máximo de llamadas que pueden esperar en la cola al mismo tiempo. El valor predeterminado es 50, pero puede elegir un valor entre 0 y 200.  <br/> Una vez alcanzado el límite, la llamada se administrará del modo que establezca en el ajuste **Cuando se alcanza el número máximo de llamadas**, que se describe a continuación.  <br/> |
|**2** <br/> |**Cuando se alcanza el número máximo de llamadas**: puede elegir lo que debe suceder cuando la cola de llamadas llegue al tamaño máximo (configurado con el ajuste **Número máximo de llamadas en la cola**).  <br/> **Desconectar con una señal de línea ocupada**: se desconectará la llamada.  <br/> **Desviar a**: si opta por este ajuste, tiene tres opciones:  <br/> **Persona de la empresa** Un usuario en línea con una licencia de **Sistema telefónico** y estar habilitada para telefonía IP empresarial o tiene un Plan de llamada. Puede configurarlo para que la persona que llama se pueden enviar al correo de voz. Para ello, seleccione una **persona de su empresa** y esta persona tendrán sus llamadas directamente al correo de voz. <br/> > [!NOTE]>  No son compatibles los usuarios locales que utilicen Skype Empresarial Server 2015, o Lync Server 2013 o 2010.          **Cola de llamadas**: debe haber creado anteriormente otra cola de llamadas para poder seleccionarla.  <br/> **Operador automático** Debe ya ha creado a un operador automático, pero después, puede seleccionar a operador automático. Consulte [Configurar un operador automático de sistema telefónico](set-up-a-phone-system-auto-attendant.md).  <br/> |
|**3** <br/> |**Cuánto tiempo puede esperar una llamada en la cola**: también puede decidir cuánto tiempo puede ponerse en espera una llamada en la cola antes de redirigirla o desconectarla. Adónde se redirigirá depende de cómo configure el ajuste **Cuando una llamada agota el tiempo de espera**. Puede establecer un intervalo de entre 0 y 45 minutos.  <br/> |
|**4** <br/> |**Cuando una llamada agota el tiempo de espera**: puede elegir lo que sucede con las llamadas cuando alcanzan el límite establecido en el ajuste **Cuánto tiempo puede esperar una llamada en la cola**:  <br/> **Desconectar**: la llamada se desconectará.  <br/> **Desviar a**: si opta por este ajuste, tiene tres opciones:  <br/> **Persona de la empresa** Un usuario en línea con una licencia de **Sistema telefónico** y estar habilitada para telefonía IP empresarial o tiene llamar a los planes. Puede configurarlo para que la persona que llama se pueden enviar al correo de voz. Para ello, seleccione una **persona de su empresa** y esta persona tendrán sus llamadas directamente al correo de voz. <br/> > [!NOTE]>  No son compatibles los usuarios locales que utilicen Skype Empresarial Server 2015, o Lync Server 2013 o 2010.          **Cola de llamadas**: debe haber creado anteriormente otra cola de llamadas para poder seleccionarla.  <br/> **Operador automático** Debe ya ha creado a un operador automático, pero después, puede seleccionar a operador automático. Consulte [Configurar un operador automático de sistema telefónico](set-up-a-phone-system-auto-attendant.md).  <br/> |
   

## Cambiar el identificador de usuario para que sea el número de teléfono de una cola de llamada

Puede proteger la identidad de un usuario cambiando su identificador de llamada para las llamadas salientes a una cola de llamada en su lugar mediante la creación de una directiva mediante el cmdlet **New-CallingLineIdentity**.
  
    
    
Para hacer esta ejecución:
  
    
    



```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

A continuación, aplicar la directiva al usuario mediante el cmdlet **Grant-CallingLineIdentity**. Para hacer esta ejecución:
  
    
    



```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Puede obtener más información sobre cómo realizar cambios en la configuración de identificador de llamada de su organización  [Cómo se puede usar la identificación de llamadas en su organización](how-can-caller-id-be-used-in-your-organization.md).
  
    
    

## ¿Desea obtener más información?

También puede usar Windows PowerShell para crear y configurar colas de llamadas.
  
    
    

### Cmdlets de colas de llamadas

Estos son los cmdlets que necesita para administrar una cola de llamadas.
  
    
    

-  [New-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
  
-  [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
  
-  [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
  
-  [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
  

### Más información sobre Windows PowerShell


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
  
    
    

