---
title: Implementación de teléfonos de Skype Empresarial Online
ms.author: tonysmit
author: tonysmit
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: Setup/Install
description: Learn the deployment steps to get the correct firmware, update it if needed, assign licences, and configure settings for Skype for Business online phones
ms.collection: Adm_Skype4B_Online
ms.technology:
- Office 365 Enterprise
- Office 365 Enterprise admin
- Office 365 Midsize Business admin
- Office 365 Small Business admin
- Skype for Business admin center
- Skype for Business Online
ms.set-free-tag: Adm_O365_FullSet
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
---


# Implementación de teléfonos de Skype Empresarial Online

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la  [declinación de responsabilidades](faa17eb3-7483-4984-87f2-815d981b68ae.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo  [aquí](https://support.office.com/en-us/article/faa17eb3-7483-4984-87f2-815d981b68ae). 
  
    
    


Esta guía de implementación le ayudará a implementar teléfonos IP para Skype Empresarial Online.
  
    
    


En todo tipo de empresas, tener un número de teléfono permite a los usuarios hacer y recibir llamadas de voz, lo cual es un requisito importante para lograr los objetivos empresariales. Los usuarios con números de teléfono pueden hacer llamadas de voz con cualquier dispositivo con Skype Empresarial, como teléfonos IP, equipos y dispositivos móviles. Para obtener más información sobre los teléfonos IP para Skype Empresarial, consulte  [Obtener teléfonos con Skype Empresarial Online](getting-phones-for-skype-for-business-online.md).
  
    
    


## Pasos para la implementación de teléfonos IP


  
    
    

### Paso 1: descargar las guías para administradores y los manuales de los teléfonos del fabricante

Antes de comenzar, es recomendable descargar las guías para administradores y los manuales de usuario de los teléfonos que proporciona el fabricante.
  
    
    

- Para los teléfonos Polycom, consulte la  [Guía de implementación de Polycom](https://support.polycom.com/PolycomService/support/us/support/voice/polycom_uc/polycom_uc_software_for_lync.mdl).
    
  
- Para los teléfonos Yealink, consulte la  [Solución de teléfonos IP HD para Skype Empresarial® de Yealink](http://www.yealink.com/solution_info.aspx?ProductsCateID=1471&amp;parentcateid=1471&amp;cateid=1471&amp;BaseInfoCateId=1328&amp;Cate_Id=1471).
    
  
- Para teléfonos AudioCodes, consulte la  [Guía de administración del aprovisionamiento de AudioCodes](https://www.audiocodes.com/products/ems).
    
  

### Paso 2: asegurarse de que los teléfonos que va a comprar o a los que va a realizar la migración son teléfonos IP compatibles con Skype Empresarial y tienen el firmware adecuado

Los teléfonos y el firmware compatibles con Skype Empresarial Online también lo son con Skype Empresarial Server, pero no siempre sucede lo mismo a la inversa. Para asegurarse de que los teléfonos y el firmware que va a comprar o aprovisionar son compatibles, consulte la guía  [Obtener teléfonos con Skype Empresarial Online](getting-phones-for-skype-for-business-online.md).
  
    
    

### Paso 3: comprobar que está instalado el firmware correcto y actualizarlo si es necesario

Proceda de la siguiente manera, según corresponda, para comprobar la versión del firmware de sus teléfonos:
  
    
    

- **Teléfonos Polycom VVX:** vaya a **Ajustes** > **Estado** > **Plataforma** > **Aplicación** > **Principal**.
    
  
- **Teléfonos Yealink:** vaya a **Estado** en la pantalla principal del teléfono.
    
  
- **Teléfonos AudioCodes:** desde la pantalla de inicio, vaya a **Menú** > **Estado del dispositivo** > **Versión de firmware**.
    
    > [!NOTE]
      > Para obtener los detalles para el acceso remoto a los teléfonos, consulte las guías de administración de los fabricantes. Consulte los enlaces anteriores para acceder a las guías de usuario y los manuales de los teléfonos. 
- **Teléfonos Lync Phone Edition (LPE):** desde la pantalla de inicio, vaya a **Menú** > **Información del sistema**.
    
  

### Paso 4: consideraciones con respecto a la actualización de los dispositivos


> [!NOTE]
> El firmware de Polycom anterior a 5.5.1.X tenía un mecanismo de bloqueo del dispositivo específico del fabricante que se ha reemplazado con una implementación del "bloqueo del teléfono" de Skype Empresarial. Al actualizar un teléfono con la versión 5.4.X.X que tuviera activado el "bloqueo del dispositivo" a la versión 5.5.1.X con "bloqueo del teléfono" no se conservará el código PIN de la característica de "bloqueo del dispositivo", lo que puede provocar que el teléfono quede desprotegido. Para los usuarios que tengan activado el "bloqueo del dispositivo", deberá activar el siguiente parámetro del perfil del dispositivo Polycom para permitir que los usuarios controlen cuándo realizar la actualización (lync.deviceUpdate.popUpSK.enabled=1). 
  
    
    

El servicio de Skype Empresarial administra las actualizaciones de firmware. El firmware de los teléfonos certificados para Skype Empresarial se carga en el servidor del servicio de actualización de Skype Empresarial. La actualización del dispositivo está activada de forma predeterminada en todos los teléfonos. Los teléfonos descargarán e instalarán automáticamente las compilaciones más recientes certificadas, teniendo en cuenta el tiempo de inactividad de cada teléfono y los intervalos de sondeo. Puede desactivar la opción de actualización del dispositivo usando el cmdlet  [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) y estableciendo el parámetro _EnableDeviceUpdate_ en `false`.
  
    
    

  
    
    
![Deploying phones.](images/be727622-1924-439f-96ca-89230739db9e.png)
  
    
    
Cuando haya un nuevo firmware disponible y preparado para la descarga y la instalación, el teléfono notificará al usuario. Los teléfonos Polycom notificarán al usuario y le permitirán elegir entre las acciones **Actualizar** y **Posponer**.
  
    
    

  
    
    
![Deploying phones.](images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
    
    
En un teléfono Polycom, puede actualizar el firmware desde el teléfono seleccionando **ActualizaciónSw**.
  
    
    

  
    
    
![Deploying phones.](images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
    
    
También puede optar por administrar las actualizaciones de firmware usando un sistema de aprovisionamiento de nuestros socios. Para obtener información sobre la administración de los sistemas de aprovisionamiento de nuestros socios y la personalización avanzada de teléfonos, consulte las guías de administración del fabricante.
  
    
    

    
> [!CAUTION]
> Asegúrese de que solo tiene una autoridad de actualización de dispositivos (actualización de dispositivos en banda o un servidor de aprovisionamiento de terceros) para evitar los bucles de actualizaciones. 
  
    
    


### Paso 5: establecer los ajustes de configuración e infraestructura de los teléfonos

Puede configurar las opciones y políticas más utilizadas de los teléfonos usando los cmdlets de Windows PowerShell para la administración en banda de Skype Empresarial. Consulte  [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obtener más información sobre estos parámetros y ajustes.
  
    
    
Para planificar la infraestructura de red, consulte  [Skype Operations Framework](https://www.skypeoperationsframework.com/) e [Implementar, migrar y desplegar](https://www.skypeoperationsframework.com/Offers?pageState=DeploymentGuidance).
  
    
    

### Paso 6: prepararse para el inicio de sesión de los usuarios

Para permitir a los usuarios correctamente inicio de sesión en un Skype para teléfono empresarial Online y realizar llamadas, debe asegurarse de que los usuarios se asignan las licencias correctas. Como mínimo debe asignar una licencia de sistema telefónico y un plan de llamadas. Para obtener información adicional puede ver  [Skype para Business y Microsoft Teams licencias de complemento](skype-for-business-and-microsoft-teams-add-on-licensing.md) y [Asignar Skype para Business y Microsoft Teams licencias](assign-skype-for-business-and-microsoft-teams-licenses.md) .
  
    
    
Puede encontrar más información sobre los planes de llamada mirando  [¿Qué planes de llamada en Office 365?](what-are-calling-plans-in-office-365.md)
  
    
    

- Las ** opciones de inicio de sesión** disponibles para los usuarios en línea son:
    
  - Los usuarios con teléfonos **Polycom VVX 5XX/6XX** verán:
    
  - 
     ![Deploying phones.](images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  

  

  
  - Los usuarios con teléfonos **Yealink T48G/T46G** verán:
    
     ![Yealink phones logon.](images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  

  

  

    Para obtener información sobre las opciones de inicio de sesión que admite cada fabricante, consulte  [Obtener teléfonos con Skype Empresarial Online](getting-phones-for-skype-for-business-online.md).
    
  
- **Id. de usuario**: usando el teclado del teléfono o el teclado en pantalla (si está disponible), los usuarios pueden usar el nombre de usuario y la contraseña de su organización para iniciar sesión en el teléfono. Por ejemplo, deben usar el formato UPN, como *amosm@contoso.com*  , en el nombre de usuario.
    
     ![Deploying phones.](images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  

    
    > [!NOTE]
      > La autenticación con PIN no se admite en Skype Empresarial Online con teléfonos LPE y teléfonos IP de socios. 
- **Usando un equipo**: si en el equipo del usuario está instalado y habilitado el software Better Together over Ethernet (BToE), este puede iniciar sesión en el teléfono usando la ventana de autenticación de su aplicación de Skype Empresarial de Windows. Consulte [Paso 7 (opcional): si se dispone de emparejamiento de dispositivos y Better Together over Ethernet (BToE)](faa17eb3-7483-4984-87f2-815d981b68ae.md#BK_BTOE) para obtener más información.
    
    > [!NOTE]
      > Los usuarios deben usar el nombre de usuario y la contraseña de su organización para iniciar sesión en el teléfono. Por ejemplo, deben usar el formato UPN, como  *amosm@contoso.com*  , en el nombre de usuario.

     ![Deploying phones.](images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  

  

  
- **Usando un** **inicio de sesión web**: esta es una nueva forma de autenticación que permite a los usuarios en línea realizar el proceso a través de un explorador web estándar. Los usuarios recibirán una serie de instrucciones que deben seguir para iniciar sesión a través del explorador.
    
  - Los usuarios con teléfonos **Polycom VVX 5XX/6XX** verán:
    
     ![Deploying phones.](images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  

  

  
  - Los usuarios con teléfonos **Yealink T48G/T46G** verán:
    
     ![Yealink phone logon.](images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  

  

  

    El código que se genera expira en 15 minutos. Una vez expirado, en función del teléfono, el usuario tendrá que hacer clic en **Reintentar** o en **Aceptar** para generar un código nuevo.
    
  - Los usuarios con teléfonos **Polycom VVX 5XX/6XX** verán:
    
     ![PIN code expired.](images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  

  

  
  - Los usuarios con teléfonos **Yealink T48G/T46G** verán:
    
     ![Yealink phones logon.](images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  

  

  

    Usando un explorador, vaya a la dirección que se muestra en el teléfono e introduzca su nombre de usuario de Skype Empresarial.
    
     ![Deploying phones.](images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  

    Introduzca el código que se muestra en el teléfono.
    
     ![Deploying phones.](images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  

    Compruebe que en el sitio se muestra " **Teléfono certificado para Skype Empresarial** de [nombre del fabricante del teléfono]" y haga clic en **Continuar**.
    
     ![Deploying phones.](images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  

    Haga clic en las credenciales de usuario o en **Usar otra cuenta**:
    
     ![Deploying phones.](images/8415028b-7924-4747-b639-052d9b0b961e.png)
  

    En cuanto se muestre la página siguiente, será seguro cerrar el explorador.
    
     ![Deploying phones.](images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  

    
    > [!NOTE]
      > Los teléfonos LPE para Skype Empresarial Online solo admiten el inicio de sesión mediante tethering USB. 
- **Implementaciones admitidas**: la siguiente tabla muestra los tipos de autenticación compatibles con los modelos de implementación que se admiten actualmente, incluidos la integración de Exchange, la autenticación moderna con Multi-factor Authentication (MFA) y Skype Empresarial Online y local.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype Empresarial** <br/> |**Exchange** <br/> |**Método de inicio de sesión en el teléfono** <br/> |**Acceso a Skype Empresarial** <br/> |**Acceso a Exchange con autenticación moderna y MFA desactivados** <br/> |**Acceso a Exchange con autenticación moderna y MFA activados** <br/> |
|En línea  <br/> |En línea  <br/> |Inicio de sesión web  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|En línea  <br/> |En línea  <br/> |Nombre de usuario y contraseña  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|En línea  <br/> |Local  <br/> |Inicio de sesión web  <br/> |Sí  <br/> |No  <br/> |No  <br/> |
|En línea  <br/> |Local  <br/> |Nombre de usuario y contraseña  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|Local  <br/> |En línea/local  <br/> |Autenticación con PIN  <br/> |Sí  <br/> |No  <br/> |No  <br/> |
|Local  <br/> |En línea/local  <br/> |Nombre de usuario y contraseña  <br/> |Sí  <br/> |Sí  <br/> |N/D  <br/> |
|Local  <br/> |En línea/local  <br/> |Inicio de sesión vía equipo (BTOE)  <br/> |Sí  <br/> |Sí  <br/> |N/D  <br/> |
   
- **Características de los teléfonos**: el conjunto de características puede variar ligeramente en función del socio de telefonía IP. Para ver la lista completa de características, consulte [Obtener teléfonos con Skype Empresarial Online](getting-phones-for-skype-for-business-online.md), donde encontrará más información sobre las características de cada fabricante de teléfonos.
    
  
- **Bloqueo del teléfono**: esta es una característica que se ha incorporado a los teléfonos certificados para Skype Empresarial recientemente como medida de protección del teléfono. Si está activada, se pedirá a los usuarios que creen un PIN después de autenticarse correctamente. Una vez creado, el teléfono se bloqueará cuando transcurra el tiempo de inactividad definido, o si el usuario bloquea manualmente el teléfono o sincroniza el bloqueo del teléfono con el de su equipo mediante la característica de emparejamiento del teléfono. Si se introduce un PIN de desbloqueo del teléfono incorrecto varias veces, el teléfono cerrará la sesión del usuario o le pedirá un código de administrador para desbloquearlo, pero este comportamiento varía en función del socio de telefonía. El PIN del usuario debe tener entre 6 y 15 dígitos.
    
    Puede desactivar para su organización la característica de bloqueo del teléfono, que está activada por defecto, cambiar el tiempo de espera de inactividad y elegir si los usuarios pueden hacer o no llamadas durante el bloqueo usando la configuración en banda. Consulte  [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obtener más detalles sobre esta configuración.
    
  

## Paso 7 (opcional): si se dispone de emparejamiento de dispositivos y Better Together over Ethernet (BToE)
<a name="BK_BTOE"> </a>

BToE es un mecanismo de emparejamiento de teléfonos para teléfonos IP de nuestros socios que empareja el teléfono del usuario con su aplicación de Skype Empresarial para Windows. BToE permite a los usuarios:
  
    
    

- Iniciar sesión en el teléfono IP usando la aplicación de escritorio de Skype Empresarial (mediante un equipo).
    
  
- Sincronizar el bloqueo del teléfono con el del equipo.
    
  
- Hacer clic para llamar.
    
  
BToE se puede configurar en 2 modos de funcionamiento:  *Automático*  (predeterminado) y *Manual*  . También se puede activar (opción predeterminada) y desactivar para los usuarios con configuración en banda de Skype Empresarial. En el modo *Manual*  , los usuarios tendrán que realizar un paso adicional para emparejar sus teléfonos con la aplicación para Windows.
  
    
    
 **Para implementar BToE a los usuarios**
  
    
    

1. Conecte los equipos con los teléfonos usando el puerto de los equipos.
    
     ![Deploying phones.](images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  

  

  
2. Descargue el software BToE más reciente desde el sitio web del fabricante utilizando los vínculos que se ofrecen a continuación e instálelo. Para obtener una mejor experiencia de usuario, puede distribuir e instalar el software BToE usando una solución de distribución para administradores, como System Center Configuration Manager (SCCM). Para obtener ayuda sobre el uso de SCCM, consulte  [Paquetes y programas en System Center Configuration Manager](https://docs.microsoft.com/es-es/sccm/apps/deploy-use/packages-and-programs).
    
  -  [Sitio de descarga del software BToE de Polycom:](https://support.polycom.com/PolycomService/support/us/support/voice/polycom_uc/polycom_uc_software_for_lync.mdl)
    
  
  -  [Descarga del software BToE de Yealink](http://www.yealink.com/solution_info.aspx?ProductsCateID=1471&amp;parentcateid=1471&amp;cateid=1471&amp;BaseInfoCateId=1328&amp;Cate_Id=1471)
    
  
  -  [Descarga del software BToE de AudioCodes](ftp://VoP-C12:IPPLync@ftp.audiocodes.com/Release/3.0.0.Beta/BToE_1.1.8/)
    
  
3. La configuración del servidor para BToE está ajustada de forma predeterminada en **Activado** y **Modo automático**. Para cambiarla, consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).
    
  

> [!NOTE]
> Actualmente BToE no es compatible con Mac ni plataformas VDI. 
  
    
    


## 
<a name="MT_Footer"> </a>


> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  
    
    


