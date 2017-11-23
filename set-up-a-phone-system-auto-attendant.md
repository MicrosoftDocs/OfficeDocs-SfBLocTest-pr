---
title: Configurar un operador automático de sistema telefónico
ms.author: tonysmit
author: tonysmit
ms.date: 11/7/2017
description: Learn how to set up and test Phone System (Cloud PBX) auto attendents for efficient call handling for your organization. 
ms.technology:
- Office 365 Enterprise admin
- Office 365 Midsize Business admin
- Office 365 Small Business admin
- Skype for Business
- Skype for Business admin center
- Skype for Business Online
ms.set-free-tag: Strat_SB_PSTN
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
---



# Configurar un operador automático de sistema telefónico

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la  [declinación de responsabilidades](6fc2687c-0abf-43b8-aa54-7c3b2a84b67c.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo  [aquí](https://support.office.com/en-us/article/6fc2687c-0abf-43b8-aa54-7c3b2a84b67c). 
  
    
    


Los operadores automáticos son muy útiles y permiten que las personas que llaman a su organización naveguen por un sistema de menús para acceder al departamento, la cola de llamadas, la persona o el operador correctos. Puede crear un operador automático para su organización usando el Centro de administración de Skype Empresarial. Para crear un operador automático nuevo, vaya a **Enrutamiento de llamadas** en el panel de navegación izquierdo y seleccione **Operadores automáticos** > **Agregar nuevo**.
  
    
    


Si desea obtener más información sobre los operadores automáticos, consulte  [¿Cuáles son los operadores automáticos de sistema telefónico?](what-are-phone-system-auto-attendants.md).
  
    
    


## Paso 1: tareas iniciales


- Antes de crear y configurar sus operadores automáticos, deberá obtener los números de servicio de pago o gratuitos, o transferir los existentes. Después de obtener los números de servicio de pago o gratuitos, estos se mostrarán en el **Centro de administración de Skype Empresarial** > **Voz** > ficha **Números de teléfono** y en el **Tipo de número** se indicará **Servicio - Número gratuito**. Para obtener los números de servicio, consulte  [Obtener números de teléfono de servicio de Skype Empresarial](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) o, si desea transferir un número de servicio existente, consulte [Números de teléfono de transferencia a Office 365](transfer-phone-numbers-to-office-365.md). Los números de **Usuario (suscriptor)** no se pueden asignar a los operadores automáticos. Si se encuentra fuera de EE. UU., no podrá usar el Centro de administración de Skype Empresarial para obtener números de servicio. En su lugar, vaya [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization.md) para ver cómo realizar esta acción desde fuera de EE. UU.
    
    > [!CAUTION]
      > Para obtener y utilizar números de teléfono gratuitos, debe configurar créditos de comunicaciones. Para ello, consulte  [¿Qué son créditos de comunicaciones?](what-are-communications-credits.md) y [Configurar comunicaciones créditos para su organización](set-up-communications-credits-for-your-organization.md). 
- Licencia Enterprise E5 o una licencia Enterprise E3 plus **Sistema telefónico**, debe tener su organización (como mínimo). El número de licencias de usuario de **Sistema de teléfono** asignados desventajas el número del servicio de números que está disponible para usarse con operadores automáticos. Los números de los operadores automáticos que puede tener depende de las licencias de **Sistema telefónico** y **Conferencias de Audio de** número que se asignan en su organización. Para obtener más información sobre licencias, vaya [Skype para Business y Microsoft Teams licencias de complemento](skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
      > Para desviar llamadas a un operador o una opción de menú que es un usuario en línea con una licencia de **Sistema telefónico**, necesitará habilitarlos para telefonía IP empresarial o asignarles llamar a los planes de Office 365. Vea  [Asignar Skype para Business y Microsoft Teams licencias](assign-skype-for-business-and-microsoft-teams-licenses.md). También puede usar Windows PowerShell. Ejecutar por ejemplo:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## Paso 2: crear un operador automático nuevo

En el **Centro de administración de Skype Empresarial**, haga clic en **Enrutamiento de llamadas** > **Operadores automáticos**, y después en **Agregar nuevo**:
  
    
    

### Página Editar información general

En la página Editar información general, introduzca o seleccione:
  
    
    

  
    
    
![New auto attendant page 1.](images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
    
    

  
    
    

|||
|:-----|:-----|
|**1** <br/> |**Nombre**: escriba un nombre para mostrar descriptivo para el operador automático. El nombre es obligatorio, y puede contener hasta 64 caracteres, espacios incluidos. Se enumerará en la columna **Nombre** en la ficha **Operadores automáticos**.  <br/> |
|**2** <br/> |**Número de teléfono** Esta opción es opcional. Si lo desea, seleccione un número de teléfono para el operador automático. Puede seleccionar cualquier pago de servicio disponible o el número de teléfono gratuito que tiene para su organización. Si no hay ningún números de teléfono, debe obtener un pago de servicio o un teléfono gratuito número. Vaya [Obtener números de teléfono de servicio de Skype Empresarial](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) para acceder a ellos. <br/> > [!NOTE]> Los números de **Usuario (suscriptor)** no se pueden asignar a los operadores automáticos.          |
|**3** <br/> |**Zona horaria**: debe establecer la zona horaria para el operador automático, pero no es necesario que se corresponda con la zona horaria de la dirección principal que se muestra para su organización. Cada operador automático puede tener una zona horaria diferente, y el horario laboral establecido para el operador automático se ajustará en función de la zona horaria seleccionada.  <br/> |
|**4** <br/> |**Idioma**: seleccione el idioma que quiere usar para su operador automático de entre los idiomas disponibles enumerados. El idioma que defina aquí será el idioma que usará el operador automático para interactuar con los autores de las llamadas que este reciba. Todos los mensajes del sistema se reproducirán en este idioma.  <br/> |
|**5** <br/> |**Reconocimiento de voz**: el reconocimiento de voz es una opción disponible que, si se activa, permite que los autores de llamadas usen la voz en el idioma que especifique. Puede desactivar el reconocimiento de voz borrando la marca de esta opción si desea que las personas utilicen solo el teclado del teléfono.  <br/> |
|**6** <br/> |**Operador**: este ajuste es opcional y no es necesario activarlo para el operador automático. Sin embargo, puede establecer la opción **Operador** para que los autores de llamadas puedan salir de los menús para hablar con una persona que les proporcione asistencia. <br/>  Automáticamente se asigna la tecla 0 a Operador. <br/>  Si configura esta opción, también deberá informar a los autores de llamadas de su disponibilidad en **Editar las opciones de menú** en la página **Administración de llamadas en horario laboral**. Si define un operador para su operador automático, deberá introducir el texto del mensaje correspondiente en el cuadro **Las personas que llaman escucharán** o cambiar el archivo de audio para incluir esta opción. Por ejemplo, "Para hablar con el operador, pulse cero." <br/>  Puede elegir entre las siguientes opciones para designar un operador: <br/>  Una **persona de la empresa** con una licencia de **Sistema telefónico** que está habilitada para telefonía IP empresarial o asignada llamar a los planes de Office 365. <br/> > [!NOTE]> **Persona de su empresa** puede ser un usuario en línea o un usuario hospedado en local con Skype para empresarial Server 2015 o Lync Server 2013. Lync Server 2010 no es compatible.           Una **cola de llamadas** que haya creado. <br/>  Puede establecer que el autor de la llamada se derive a un correo de voz. Para hacerlo, seleccione una **persona de su empresa** y establezca que las llamadas de esta persona se desvíen directamente al correo de voz. <br/> |
   

### Página Seleccionar horas de funcionamiento

De manera predeterminada el horario laboral está configurado en 24 horas al día, los 7 días de la semana, por lo que todas las horas se consideran laborales. Todas las horas que no se incluyan en el horario laboral se consideran no laborales. Si selecciona la opción **Personalizado** y ajusta su horario laboral, se agregará una nueva página llamada **Administración de llamadas fuera del horario laboral** y tendrá que configurar la administración de llamadas recibidas fuera del horario laboral para el operador automático.
  
    
    

  
    
    
![New auto attendant Hours of operation.](images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)
  
    
    

  
    
    

|||
|:-----|:-----|
|**1** <br/> |Seleccione la opción **Personalizado** para seleccionar horas laborales específicas en el calendario. Al seleccionar **Personalizado**, el horario laboral se ajusta de forma predeterminada al intervalo de lunes a viernes, de 9:00 a 17:00.  <br/> |
|**2** <br/> |Para cambiar el horario laboral, resalte las horas laborales que quiera ajustar usando el calendario. El calendario le permite seleccionar horas laborales en intervalos de 30 minutos. El horario laboral que seleccione aquí se basará en la zona horaria de la página **Información general**. Para establecer una pausa (para comer, por ejemplo), anule la selección de las horas correspondientes en el calendario o arrástrelas para anular su selección. Puede definir varias pausas dentro del horario laboral.  <br/> |
   

### Seleccione las horas de trabajo llamar a la página de administración


> [!TIP]
> Si utiliza una programación personalizada para el horario laboral, también deberá configurar la administración de llamadas para las horas fuera del horario laboral. Para que pueda establecer los ajustes correspondientes, se agregará una página **Administración de llamadas fuera del horario laboral**, donde encontrará las mismas opciones que en **Administración de llamadas en horario laboral**. 
  
    
    

Puede configurar saludos, indicaciones y menús para las personas que escuchará llamada en número de teléfono de operador automático de su organización durante el horario laboral.
  
    
    

  
    
    
![Business hours call handling.](images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
    
    

  
    
    

|||
|:-----|:-----|
|**1**|**Saludo de la empresa**: el saludo para el horario laboral es opcional y se puede ajustar en **Ninguno**. En este caso, el autor de la llamada no oirá ningún saludo antes de que una de las opciones seleccionadas administre la llamada. También puede cargar un archivo de audio (en formato .wav, mp3 o .wma) o crear un saludo personalizado usando la característica Texto a voz. **Ninguno** Saludo no se reproducirá cuando personas llaman al número de teléfono de operador automático. **Crear un personalizado de saludo** Si elige esta opción, escriba el texto que desea que el sistema lea (hasta 1000 caracteres). Por ejemplo, puede escribir "Bienvenido a Contoso. La llamada es importante para nosotros."en el cuadro **escucharán las personas que llaman**. **Cargar un archivo de audio** Si selecciona esta opción, grabar el saludo y, a continuación, cargue el archivo de audio (en un formato .wav,. mp3 o .wma).|
|**2**| Puede seleccionar qué ocurre con las llamadas que llegan durante el horario comercial. Puede elegir entre las siguientes opciones: **Desconectar**: si selecciona esta opción, la llamada se desconectará después de reproducir el saludo del horario laboral. **Redirigir llamada**: puede usar esta opción para enviar la llamada automáticamente a: **Persona de su empresa** con una licencia de **Sistema telefónico** que está habilitada para telefonía IP empresarial o asignada llamar a los planes de Office 365. Puede configurarlo para que la persona que llama se pueden enviar al correo de voz. Para ello, seleccione la **persona de su empresa** y establezca esta persona a sus llamadas reenvía directamente al correo de voz.> [!NOTE]> **Persona de su empresa** puede ser un usuario en línea o un usuario hospedado en local con Skype para empresarial Server 2015 o Lync Server 2013. Lync Server 2010 no es compatible.           Una **cola de llamadas**: esta opción le permite transferir la llamada a una cola de llamadas existente que ya haya configurado.  Otro **operador automático**: puede usar un operador automático existente para crear un segundo nivel de opciones de menú que contenga un submenú. Estos operadores automáticos se conocen como operadores automáticos anidados. **Reproducir el texto de las opciones de menú**: puede usar esta opción para configurar el mensaje que quiera que se reproduzca. |
|**3**|**Texto del menú**: para crear un mensaje para el menú principal puede usar la característica Texto a voz o cargar un archivo de audio (.wav, .mp3 o .wma). Puede escribir el mensaje en el cuadro **Las personas que llaman escucharán** o grabar un archivo de audio y decir, por ejemplo: "Pulse o diga 1 para Ventas. Pulse o diga 2 para Servicios. Pulse o diga 3 para Atención al cliente. Para hablar con el operador, pulse o diga 0. Para escuchar este mensaje de nuevo, pulse la tecla de asterisco o diga Repetir". **Crear un mensaje de asistencia por voz personalizado**: si elige esta opción, debe introducir el texto que desea que lea el sistema (hasta 1000 caracteres). **Cargar un archivo de audio**: si elige esta opción, deberá grabar el saludo y cargar el archivo de audio (en formato .wav, .mp3 o .wma). |
|**4**|**Marcado por nombre** Si elige esta opción, se permitirá la personas que llaman para buscar personas en su organización mediante la búsqueda en el directorio. Puede seleccionar las personas que se mostrarán como disponible o no está disponible para acceso telefónico por nombre mediante la configuración de estas opciones en la página de **ámbito de marcado**. Cualquier usuario en línea con una licencia de **Sistema telefónico** o todos los usuarios alojados en local usando Skype empresarial Server 2015 o Lync Server 2013, puede encontrarse con acceso telefónico por su nombre.> [!CAUTION]> Los usuarios alojados en local con Lync 2010 **no se puede llegar** con acceso telefónico por su nombre.          |
|**5**|**Editar las opciones de menú**: puede agregar o eliminar opciones de menú usando las teclas del teclado. Para agregar una opción de menú, pulse la tecla correspondiente en el teclado. Las teclas en uso cambiarán de color y la línea de opciones correspondiente se mostrará debajo. Para eliminar una opción de menú, pulse la tecla adecuada en el control del teclado para eliminar la selección de esa tecla. Se eliminará la línea de asignación con la tecla.> [!TIP]> Deberá actualizar el texto de los mensajes de instrucciones del menú o volver a grabar el archivo de audio por separado si va a agregar o eliminar opciones, dado que los mensajes de instrucciones del menú no se actualizarán automáticamente.           Puede agregar y eliminar cualquier opción de menú en cualquier orden; las teclas asignadas no tienen que ser sucesivas. Es posible crear, por ejemplo, un menú con las teclas 0, 1 y 3 asignadas a opciones, y dejar la tecla 2 sin usar.> [!NOTE]> El sistema tiene reservadas las teclas * (Repetir) y # (Volver) y no se pueden reasignar. Si el reconocimiento de voz está activado, pulsar * equivaldrá al comando de voz "Repetir" y # a "Volver".           |
|| Para configurar sus opciones de menú, después de seleccionar la(s) teclas(s), deberá: **Escribir el nombre de la opción**: este nombre puede tener hasta 64 caracteres y contener varias palabras, como "Atención al cliente" u "Operaciones y territorios". Si está activado el reconocimiento de voz, el nombre se reconocerá automáticamente, y la persona que llame podrá pulsar 3, decir "Tres" o decir "Atención al cliente" para seleccionar la opción asignada a la tecla 3. El siguiente paso consiste en seleccionar dónde debe enviarse la llamada si se pulsa la tecla correspondiente o si se selecciona la opción mediante reconocimiento de voz. La llamada puede enviarse a: Un **operador**: si ya tiene configurado el operador, este se asigna automáticamente a la tecla 0, pero puede eliminar o cambiar esta asignación a una tecla diferente. Si todavía no ha vinculado el operador con ninguna tecla, el comando de voz "Operador" estará también desactivado.  Una **persona de la empresa** con una licencia de **Sistema telefónico** que está habilitada para telefonía IP empresarial o asignada a un Plan de llamada en Office 365. Puede configurarlo para que la persona que llama se pueden enviar al correo de voz. Para ello, seleccione la **persona de su empresa** y establezca esta persona a sus llamadas reenvía directamente al correo de voz.> [!NOTE]> **Persona de su empresa** puede ser un usuario en línea o un usuario hospedado en local con Skype para empresarial Server 2015 o Lync Server 2013. Lync Server 2010 no es compatible.           Una **cola de llamadas**: esta opción le permite transferir la llamada a una cola de llamadas existente que ya haya configurado.  Un **operador automático**: puede usar un operador automático existente para crear un segundo nivel de opciones de menú que contenga un submenú. Estos operadores automáticos se conocen como operadores automáticos anidados. > [!NOTE]>  El **horario laboral** de los operadores automáticos anidados (o de segundo nivel) se usará también para las llamadas que enviadas a través de otro operador automático configurado.          |
   

### Seleccione página de días festivos (disponible para los clientes de vista previa)

Puede agregar hasta 20 días festivos programadas para cada operador automático.
  
    
    
![Setting up Holidays in auto attendant](images/50a5ce88-7f39-4210-808a-da7ced969854.png)
  
    
    

  
    
    

  
    
    

|||
|:-----|:-----|
|**1**|**Agregue un día festivo** Escriba un nombre para el nuevo día festivo en el campo **nombre de vacaciones**.Nombres de vacaciones pueden constar de un máximo de 64 caracteres y deben ser únicos para el mismo operador automático. Por ejemplo, no puede tener dos días festivos denominadas "Acción de gracias" en el mismo operador automático.|
|**2**|**Saludo de vacaciones** El saludo de vacaciones es opcional y puede establecer en **ninguna**. En este caso, el llamador no escuchará ningún mensaje o saludo antes de la llamada se controla mediante una de las opciones que seleccione. También puede cargar un archivo de audio (en formatos WAV, mp3 o .wma) o crear un saludo personalizado mediante la característica texto a voz. **Ninguno** Saludo no se reproducirá cuando personas llaman al número de teléfono de operador automático. **Crear un personalizado de saludo** Si elige esta opción, escriba el texto que desea que el sistema lea (hasta 1000 caracteres). ¡Por ejemplo, puede escribir "feliz año nuevo! Nuestras oficinas están actualmente cerrados."en el cuadro **escucharán las personas que llaman**. **Cargar un archivo de audio** Si selecciona esta opción, grabar el saludo de vacaciones y, a continuación, cargue el archivo de audio (en un formato .wav,. mp3 o .wma).|
|**3**|**¿Qué sucede con las llamadas después el saludo?** Puede seleccionar qué ocurre con las llamadas que llegan durante este vacaciones. Puede elegir entre las siguientes opciones: **Desconectar** La persona que llama se desconectarán tras escuchar el saludo de vacaciones. **Redirigir llamada**: puede usar esta opción para enviar la llamada automáticamente a:  Una **persona de la empresa** con una licencia de **Sistema telefónico** que está habilitada para telefonía IP empresarial o asignada llamar a los planes de Office 365. Puede configurarlo para que la persona que llama se pueden enviar al correo de voz. Para ello, seleccione la **persona de su empresa** y establecer esta persona a sus llamadas reenvía directamente al correo de voz.> [!NOTE]> **Persona de su empresa** puede ser un usuario en línea o un usuario hospedado en local con Skype para empresarial Server 2015 o Lync Server 2013. Lync Server 2010 no es compatible.           Una **Cola de llamadas** para transferir la llamada a una cola de llamadas existente que ha configurado Otro **operador automático**, para crear un segundo nivel de opciones de menú que contiene un submenú. Se denominan a operadores automáticos anidada. > [!NOTE]>  De forma predeterminada, todas las llamadas que llegan durante un período de vacaciones se establecen en Desconectar después el saludo (si existe), por lo que debe especificar una redirección si se desea un comportamiento diferente.          |
|**4**|**Cuando quiera las vacaciones para iniciar y terminar?** Especifique la fecha de inicio de vacaciones en formato mm/dd/aaaa y, a continuación, seleccione una hora de inicio, la fecha de finalización y la hora de finalización, cuando se le solicite en la tabla de intervalo de fechas.Puede especificar hasta 10 diferentes rangos de fecha para un día festivo. Por ejemplo, puede agregar intervalos de fechas para las vacaciones de fin de año de hasta 10 años. Un día festivo puede abarcar varios días.Para agregar nuevas vacaciones fecha rangos (por ejemplo, para el próximo año), haga clic en **Agregar otra** y, a continuación, escriba un nuevo conjunto de fechas de inicio y finalización de las vacaciones.Días festivos anidadas también son compatibles. Por ejemplo, puede anidar varios días festivos dentro de un período de tiempo de "salto de vacaciones": **· 24 de diciembre a través 3 de enero:** "Feliz Navidad Nuestras oficinas actualmente están cerrados. Nos se vuelva a abrir el 4 de enero." **· 25 de diciembre:** "Feliz Navidad! Nuestras oficinas actualmente están cerrados. Nos se vuelva a abrir el 4 de enero." **· 1 de enero:** "feliz año nuevo! Nuestras oficinas actualmente están cerrados. Nos se vuelva a abrir el 4 de enero."|
   
Después de guardar al operador automático, los días festivos aparecen en la pestaña de **vacaciones**, donde puede editar, agregar o modificar la configuración de vacaciones.
  
    
    

### Página Seleccionar ámbito de marcado

En esta página puede configurar qué usuarios de su organización se deben enumerar en el directorio y estarán disponibles para Marcado por nombre para las personas que llamen a su organización.
  
    
    

  
    
    
![Dial scope for searching with dial by name.](images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
    
    

  
    
    

|||
|:-----|:-----|
|**1** <br/> | La opción **Incluir** ofrece dos posibilidades: <br/> **Online todos los usuarios** Uso de esta opción permite todas las personas de su organización que desea incluir en la búsqueda en el directorio. Todos los usuarios en línea con una licencia de **Sistema telefónico**, así como los usuarios alojados en local con Skype para empresarial Server 2015 o Lync Server 2013, que tiene que llama planes en Office 365 se mostrarán.  <br/> **Personalizado** Si usa esta opción, puede buscar un grupo de Office 365, lista de distribución o grupo de seguridad que ha creado en su organización y las personas que agregan a este grupo de Office 365, lista de distribución o grupo de seguridad que están en **usuarios en línea con un Licencia de sistema de teléfono** u hospedado en local usa Skype para empresarial Server 2015 o Lync Server 2013 se incluirán en la búsqueda en el directorio. Puede agregar varios grupos de Office 365, listas de distribución y grupos de seguridad. <br/> > [!CAUTION]>  Los usuarios locales de implementaciones de Lync Server 2010 no aparecerá cuando alguien busca en el directorio mediante acceso telefónico por su nombre.          |
|**2** <br/> | La opción **Excluir** ofrece dos posibilidades: <br/> **Ninguno**: esta opción indica que no se debe excluir a ningún usuario de la búsqueda en directorios.  <br/> **Personalizado** Si usa esta opción, puede buscar un grupo de Office 365, grupo de seguridad o lista de distribución que se ha creado en su organización y todas las personas que se agregan a este grupo de Office 365, grupos de seguridad o lista de distribución se pueden excluir de la búsqueda en el directorio. Puede agregar varios grupos de Office 365, listas de distribución y grupos de seguridad. <br/> > [!CAUTION]>  Los usuarios locales de implementaciones de Skype empresarial 2015 o Lync Server 2013 y 2010 no aparecerá cuando alguien busca en el directorio mediante acceso telefónico por su nombre.          |
   

    
> [!NOTE]
> El nombre del nuevo usuario podría tardar hasta 36 horas en aparecer en el directorio cuando alguien use el Marcado por nombre con reconocimiento de voz. 
  
    
    


  
    
    
Después de completar todos los campos necesarios y configurar los menús y las opciones de administración de llamadas, haga clic en **Guardar**.
  
    
    

## Editar y probar un operador automático

Después de guardar un operador automático, este se mostrará en la página **Operadores automáticos**. Esto le permitirá ver rápidamente algunas de las opciones que ha configurado, como el nombre, el número de teléfono, el idioma y el estado.
  
    
    
Si desea hacer cambios en un operador automático, haga clic en él para resaltarlo y, en el panel lateral, haga clic en **Editar**.
  
    
    
Puede realizar rápidamente una llamada de prueba a su operador automático mediante el botón **Probar** del panel lateral.
  
    
    

## ¿Desea obtener más información?

También puede usar Windows PowerShell para crear y configurar operadores automáticos.
  
    
    

### Cmdlets para operadores automáticos

Estos son los cmdlets que necesita para administrar un operador automático.
  
    
    

||||
|:-----|:-----|:-----|
| [New-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796493.aspx) <br/> | [Get-CsOrganizationalAutoAttendantSupportedTimeZone]( https://technet.microsoft.com/en-us/library/mt796483.aspx) <br/> | [New-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/en-us/library/mt796488.aspx ) <br/> |
| [Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796486.aspx) <br/> | [Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/en-us/library/mt796481.aspx) <br/> | [New-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/en-us/library/mt796489.aspx) <br/> |
| [Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796482.aspx ) <br/> | [New-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/en-us/library/mt796480.aspx) <br/> | [New-CsOnlineTimeRange](https://technet.microsoft.com/en-us/library/mt796491.aspx ) <br/> |
| [Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796492.aspx) <br/> | [New-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/en-us/library/mt796484.aspx ) <br/> | [New-CsOnlineSchedule](https://technet.microsoft.com/en-us/library/mt796490.aspx) <br/> |
| [New- CsOnlineAudioFile](https://technet.microsoft.com/en-us/library/mt796479.aspx) <br/> | [New-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/en-us/library/mt796485.aspx ) <br/> | [New-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/en-us/library/mt796487.aspx ) <br/> |
| [Exportar-CsOrganizationalAutoAttendantHolidays (solo para clientes de vista previa)](https://docs.microsoft.com/en-us/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) <br/> | [Get-CsOrganizationalAutoAttendantHolidays (solo para clientes de vista previa)](https://docs.microsoft.com/en-us/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps) <br/> | [Importar-CsOrganizationalAutoAttendantHolidays (solo para clientes de vista previa)](https://docs.microsoft.com/en-us/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) <br/> |
| [Nuevo-CsOnlineDateTimeRange (solo para clientes de vista previa)](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) <br/> |||
   

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
  
    
    

