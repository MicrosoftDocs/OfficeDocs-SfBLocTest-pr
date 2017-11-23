---
title: Flujo de llamadas con ExpressRoute
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 9/25/2017
ms.audience: Admin
ms.prod: SKYPEFORBUSINESS
ms.collection: Adm_Skype4B_Online
ms.technology: Skype for Business Online
ms.set-free-tag: Adm_O365_FullSet
ms.assetid: 413acb29-ad83-4393-9402-51d88e7561ab
---


# Flujo de llamadas con ExpressRoute

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la  [declinación de responsabilidades](413acb29-ad83-4393-9402-51d88e7561ab.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo  [aquí](https://support.office.com/en-us/article/413acb29-ad83-4393-9402-51d88e7561ab). 
  
    
    


Con este artículo tratamos de explicar el flujo de llamadas básico para Skype Empresarial Online y ExpressRoute, y darle algunos ejemplos detallados de flujos de llamada para que pueda entenderlo y planificarlo correctamente.
  
    
    


Si va a implementar Skype Empresarial Online como parte de Office 365, la implementación híbrida de Skype Empresarial Server o Skype Empresarial Cloud Connector Edition, tendrá que comprender cómo se produce la comunicación entre el cliente de Skype Empresarial y los servidores para poder planificar, implementar y operar el flujo de llamadas de forma efectiva, así como solucionar los problemas que puedan surgir. 
  
    
    


## Información general sobre el flujo de llamadas

En este documento se describen los segmentos de red que pueden transportar datos en estos flujos de llamadas y se explica qué tráfico permanecerá como local en su red frente al tráfico que se desplazará por Internet o a través de ExpressRoute. Al saber qué trafico utiliza ExpressRoute, podrá evaluar las ventajas que recibirá su empresa si decide usarlo, y podrá comprender la guía de implementación de ExpressRoute para validar y solucionar los problemas de su implementación una vez que haya decidido usarlo.
  
    
    
Hay diferentes factores que puede controlar y que pueden repercutir en los flujos de llamada que se describen aquí; entre ellos, por ejemplo, las reglas de firewall, la configuración NAT, los servidores proxy y la configuración del enrutador. En este documento se da por hecho que se ha aplicado la configuración recomendada. Esta configuración recomendada se describe en:
  
    
    

-  [Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)
    
  
-  [URL de Office 365 e intervalos de direcciones IP](http://technet.microsoft.com/library/8548a211-3fe7-47cb-abb1-355ea5aa88a2%28Office.14%29.aspx)
    
  
-  [Azure ExpressRoute para Office 365](http://technet.microsoft.com/library/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd%28Office.14%29.aspx)
    
  
-  [Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/)
    
  
Las configuraciones que no hayan seguido los pasos que se describen en la documentación anterior pueden tener unos flujos de llamada distintos a los que se registran aquí. Además, podrían surgir problemas en la configuración, como rutas de red asimétricas y rutas de red que no son óptimas, o protocolos de transporte que no son los óptimos. El enrutamiento asimétrico es un punto muy importante que se debe tener en cuenta cuando ExpressRoute está involucrado, dado que introduce una segunda ruta a Office 365 que crea la posibilidad de una ruta que derive el tráfico mediante Internet en una dirección y otra ruta que use ExpressRoute en la otra dirección. Esta situación puede provocar que se bloquee el tráfico en la dirección de retorno si atraviesa un firewall con estado.
  
    
    

## Segmentos de red y tipos de tráfico


### Segmentos de red

Antes de que podamos explicar el flujo de llamada, necesitamos definir algunos términos que le ayudarán a comprender los segmentos de red y los tipos de soporte que se utilizan en Skype Empresarial Online. 
  
    
    
Los diagramas de flujos de llamada que se muestran a continuación reflejan cuatro segmentos de red diferentes, gestionados cada uno de ellos por diversas organizaciones (su red interna, su proveedor de servicios de red y sus socios igualitarios de Internet, y Microsoft), que tienen distintas características de rendimiento. Para obtener directrices sobre los destinos de rendimiento de red, consulte  [Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md).
  
    
    
A continuación puede ver cada segmento de red del que hablaremos.
  
    
    

  
    
    
![Call Flow Network Segments.](images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)
  
    
    
 **Su red** Este es el segmento de red que forma parte de la red general que controla y administra. Incluye todas las conexiones dentro de sus oficinas, tanto con cable como sin cable, entre edificios de oficinas, a centros de datos en local y sus conexiones a proveedores de Internet o socios de ExpressRoute.
  
    
    
Por lo general, el perímetro de su red tiene una o varias redes perimetrales con firewalls o servidores proxy que exigen el cumplimiento de las directivas de seguridad de su organización y que solo permiten determinado tráfico de red que haya configurado. Dado que es usted quien administra esta red, tiene control directo sobre su rendimiento. Es muy recomendable que realice las evaluaciones de red necesarias para validar el rendimiento tanto dentro de los sitios de su red como desde la red a Skype Empresarial Online. Para ver los requisitos de rendimiento, consulte  [Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md).
  
    
    
 **Internet** Este es el segmento de red que forma parte de su red general y que emplearán los usuarios que se conecten a Skype Empresarial Online desde fuera de su red. Se utilizará para todas las conexiones cuando ExpressRoute no esté configurado. Ni usted ni Microsoft son los encargados de administrar Internet ni todas sus conexiones, por lo que el rendimiento y las rutas de enrutamiento no se pueden determinar. Todo esto influirá enormemente en la calidad y el flujo de llamada en general.
  
    
    
 **ExpressRoute** Este es el segmento de red que forma parte de su red general. Le proporcionará una conexión dedicada y privada a la red de Microsoft. Esta es la opción recomendada para conectar su red a la red de Microsoft (centros de datos de Office 365) para todas las cargas de trabajo que dependan de la velocidad de red y el rendimiento, como la comunicación en tiempo real de Skype Empresarial Online. Las conexiones de ExpressRoute se establecen entre su red y la red de Microsoft utiliza los [proveedores de conectividad de ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/) para proporcionar una red privada y administrada, con un 99,9 % de tiempo activo y soporte para la calidad de servicio (QoS) que pueda mejorar el rendimiento para medios en tiempo real en los períodos de congestión en la red.
  
    
    
 **Red de Microsoft** Este es el segmento de red que forma parte de la red general que admite los servicios de Office 365. Aquí se incluyen todas las comunicaciones entre los servidores Online para Office 365 y podría incluir el tráfico que atraviesa la red troncal de Microsoft y se transmite entre las regiones geográficas.
  
    
    

### Tipos de tráfico

El tráfico de red de Skype Empresarial Online se divide en dos amplias categorías, cada una de las cuales se muestra como una ruta independiente en el flujo de llamadas:
  
    
    
Los **medios en tiempo real** son los datos encapsulados dentro de RTP (protocolo de transporte en tiempo real) que admiten audio, vídeo, uso compartido de aplicaciones y cargas de trabajo de transferencia de archivos. En general, el tráfico multimedia es muy sensible a la latencia, por lo que sería mejor que este tráfico tomara la ruta más directa posible y que usara UDP como el protocolo de capa de transporte, puesto que con el protocolo TCP se introduciría una latencia mayor.
  
    
    
La **señalización** es el vínculo de comunicación entre el cliente y el servidor, u otros clientes, que se usa para controlar actividades (por ejemplo, cuando se inicia una llamada) y entregar mensajes instantáneos. La mayor parte del tráfico de señalización utiliza el protocolo SIP, aunque algunos clientes emplean interfaces REST basadas en HTTP. Para simplificarlo, estamos considerando una variedad de señalizaciones que puedan viajar por conexiones HTTP y HTTPS o TLS en este tipo de tráfico. Es importante comprender que este tráfico es mucho menos sensible a la latencia, pero puede originar cortes en el servicio o tiempos de espera en las llamadas si la latencia entre los puntos de conexión sobrepasa varios segundos.
  
    
    
Los destinos de este tráfico se encuentran en  [URL de Office 365 e intervalos de direcciones IP](http://technet.microsoft.com/library/8548a211-3fe7-47cb-abb1-355ea5aa88a2%28Office.14%29.aspx) para todos los servicios de Office 365. Para cada dirección URL, indica si esa porción de tráfico puede atravesar ExpressRoute para Office 365. En el caso de los diagramas que muestran que Internet se sigue usando para algún tráfico cuando ExpressRoute está habilitado, consulte [Azure ExpressRoute para Office 365](http://technet.microsoft.com/library/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd%28Office.14%29.aspx). Es importante comprender que incluso las direcciones URL que aparecen como enrutables a través de ExpressRoute también lo son a través de Internet. Esto quiere decir que, en algunas circunstancias, determinar si se utilizará Internet o ExpressRoute dependerá de la ubicación del cliente y la configuración de los servidores proxy y los firewalls. Asimismo, es importante comprender que, puesto que no todas las direcciones URL asociadas a Office 365 pueden usar ExpressRoute, es necesario contar con una conexión a Internet, incluso si compra ExpressRoute de un socio de ExpressRoute. 
  
    
    
El tráfico que solo se puede enviar por Internet incluye dependencias de Internet comunes, como Listas de revocación de certificados (listas CRL), búsquedas de DNS y resolución de nombres, direcciones URL para servicios de Office 365 compartidos, como para el centro de administración de Office 365, y algunas funciones de comunicación que no se producen en tiempo real de Skype Empresarial Online, como la telemetría y la federación para la interoperabilidad con el consumidor de Skype, así como los medios que se transmiten por la Difusión de reunión de Skype. Para ayudarle a tomar decisiones, consulte  [Enrutamiento con ExpressRoute para Office 365](http://technet.microsoft.com/library/e1da26c6-2d39-4379-af6f-4da213218408%28Office.14%29.aspx) para ver más consideraciones a la hora de planificar su enrutamiento de red.
  
    
    

## Principios para los flujos de llamadas con Skype Empresarial

Antes de entrar en los detalles de los escenarios concretos de los flujos de llamada, hay seis principios generales que le ayudarán a comprender los flujos de llamada para Skype Empresarial.
  
    
    

1. Una conferencia de Skype Empresarial se hospeda en la misma región en la que se aloja el organizador de la conferencia. Se trata de la nube de Office 365 si el organizador es un usuario en línea o de un centro de datos local si el organizador de la reunión es un usuario local.
    
  
2. El tráfico multimedia que se envía desde un cliente a una conferencia hospedada siempre se dirige al servidor en el que se aloja la conferencia. Puede ser un servidor local dentro de un centro de datos que usted administre o un servidor en línea dentro de la nube de Office 365. Sin embargo, siempre se utiliza un servidor perimetral para el flujo multimedia de las conferencias en línea.
    
  
3. El tráfico multimedia de las llamadas de punto a punto toma la ruta más directa que esté disponible. La ruta preferida va directa al equipo remoto (cliente), pero si esa ruta no está disponible porque el firewall está bloqueando el tráfico o existe algún otro problema de este tipo, entonces uno o varios servidores perimetrales retransmitirán el tráfico.
    
  
4. El tráfico de señalización siempre se dirige al servidor en el que se aloja el usuario, ya sea en línea o local. Se utilizará un servidor perimetral si el servidor front-end no se puede conectar directamente.
    
  
5. Los usuarios que se unen a una conferencia hospedada en línea siempre usarán un servidor perimetral (o dos si es necesario por las configuraciones del firewall para cliente).
    
  
6. Los usuarios que se unen a una conferencia hospedada en local no utilizarán, por lo general, un servidor perimetral si se conectan desde dentro de la misma red que contiene la implementación local, y utilizarán uno o dos servidores perimetrales cuando se conectan desde fuera de la red. 
    
  
Para obtener más información sobre los detalles de la ruta multimedia que se elige, consulte  [ICE: conectividad multimedia perimetral](https://aka.ms/AVEdge). Aunque en este vídeo se hable de Lync Server 2013, los principios y protocolos siguen aplicándose en Skype Empresarial.
  
    
    

## Los flujos de llamada de Skype Empresarial con ExpressRoute

Ahora que ya conoce los cuatro segmentos de red que existen y algunos principios generales de los flujos de llamada de Skype Empresarial, puede usar esta información para comprender qué tráfico de Skype Empresarial atravesará un segmento de red de ExpressRoute.
  
    
    
En general, el tráfico de red cruzará la conexión de ExpressRoute si un punto de conexión está en su red y el otro está en el centro de datos de Office 365. Esto incluirá el tráfico de señalización entre el cliente y el servidor, el tráfico multimedia usado durante las llamadas de conferencia o las llamadas de punto a punto que usan un servidor perimetral en línea.
  
    
    
El tráfico no cruzará la conexión de ExpressRoute si los dos puntos de conexión se pueden comunicar directamente a través de Internet o si están situados dentro de su red. Incluirá los elementos multimedia en las llamadas de punto a punto, el tráfico desde Internet que va destinado a una implementación local o cualquier tráfico entre Internet y los servidores perimetrales de Office 365. Un ejemplo sería un usuario que se une a una conferencia en línea desde un hotel.
  
    
    

## Flujo de llamadas básico de Skype Empresarial

Para ayudarle a aplicar los principios generales de los flujos de llamada de Skype Empresarial que se han descrito anteriormente, la próxima sección de este artículo contiene diagramas como referencia. No se trata de una lista exhaustiva de todos los posibles flujos de llamadas, sino de un intento de ayudarle a aplicar los principios detallados anteriormente. Además, los escenarios de los diagramas se han seleccionado para cubrir los tipos de implementación más comunes; entre ellos, en línea, híbrida, conector de nube y, en un caso especial, la Difusión de reunión de Skype.
  
    
    

> [!NOTE]
> Un subconjunto de tráfico que utiliza Skype Empresarial no se enruta a través de ExpressRoute y siempre tomará la ruta de Internet. Consulte  [URL de Office 365 e intervalos de direcciones IP](http://technet.microsoft.com/library/8548a211-3fe7-47cb-abb1-355ea5aa88a2%28Office.14%29.aspx) para determinar las direcciones URL que se pueden ver afectadas.
  
    
    


### Llamada de punto a punto para usuarios de Office 365 desde el interior de la red del cliente
<a name="bk_Figure2"> </a>

En las llamadas de punto a punto, el tráfico multimedia siempre toma la ruta más directa a su destino. No obstante, el tráfico de señalización va a un centro de datos de Office 365 en el que está alojado el usuario en línea. Puesto que ambos usuarios están en la misma WAN y nada impide que los clientes se comuniquen directamente, los elementos multimedia fluyen directamente entre ellos. El tráfico de señalización, en el caso de ambos usuarios, atraviesa la conexión de ExpressRoute que se destina al centro de datos de cada organización. Para mostrarle el flujo de llamadas en este escenario, vea esto.
  
    
    
 **Flujo de llamadas de punto a punto**
  
    
    

  
    
    
![Call Flow with Peer to Peer call.](images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)
  
    
    

  
    
    

  
    
    

### Usuario en línea de su red que se une a una conferencia hospedada en línea
<a name="bk_Figure3"> </a>

En el ejemplo de punto a punto, el tráfico multimedia siempre toma la ruta más directa a su destino; sin embargo, en el caso de una conferencia en línea, el destino está en la nube de Office 365. Esto significa que el tráfico multimedia de todos los usuarios que se unen a la conferencia desde su red atravesará la conexión de ExpressRoute y el tráfico de señalización viajará hasta la nube de Office 365. En el gráfico siguiente se muestra que ambos gráficos, multimedia y de señalización, atravesarán la conexión ExpressRoute para un usuario que se encuentre en su red y que atravesarán directamente Internet en el caso de los usuarios que se conecten a Internet desde fuera de su red. Por ejemplo, desde una cafetería o un hotel.
  
    
    
Recuerde que la ubicación de una conferencia la define el organizador de la reunión y no los participantes. Esto significa que, si la reunión la programó un cliente local, el tráfico multimedia no fluirá a la nube de Office 365 sobre ExpressRoute, pero, en su lugar, atravesaría Internet hacia el centro de datos local del organizador de la reunión.
  
    
    
El destino de los elementos multimedia en el caso de las conferencias en línea será un centro de datos en la nube de Office 365, pero este se puede encontrar en una región geográfica distinta a la de los usuarios que se están uniendo a la conferencia. Esta situación se da de una de estas dos formas:
  
    
    

- Si el organizador de la reunión pertenece a una empresa distinta a la de los asistentes o participantes, y la organización del organizador está hospedada en una ubicación geográfica, o país o región, distinta.
    
  
- Si un usuario se une desde un país o región distinto al de la organización de la empresa, ya sea porque es una empresa multinacional o porque el usuario esté viajando.
    
  
La buena noticia que tiene usar ExpressRoute en este escenario es que, con el complemento Premium de ExpressRoute, los datos que siguen la ruta de ExpressRoute pasarán automáticamente por la red troncal de Microsoft al centro de datos de la organización, independientemente de la región geográfica del organizador de la reunión.
  
    
    
 **Flujo de llamadas de un usuario en línea con una reunión en línea**
  
    
    

  
    
    
![Call flow for an online hosted conference call.](images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)
  
    
    

  
    
    

  
    
    

### Unirse a una conferencia hospedada por un usuario local en una implementación híbrida
<a name="bk_Figure3"> </a>

Recuerde que los servidores de conferencia que admiten conferencias hospedadas se determinan por el lugar en el que se encuentra el organizador de la reunión. En este escenario, los elementos multimedia de todos los usuarios que se unen a una conferencia programada por un usuario local en una implementación híbrida fluirán hasta un centro de datos local. La señalización para los usuarios alojados en línea se establecerá a través de su organización en la nube de Office 365, mientras que los elementos multimedia intentarán establecer una conexión directa. Así, en este caso, como ambos usuarios se conectan desde dentro de su red, se puede establecer una conexión multimedia directa, de manera que ExpressRoute se utiliza solo para el tráfico de señalización del usuario alojado en línea. Si un usuario alojado en línea se conecta desde Internet, el elemento multimedia podría atravesar ExpressRoute si se utilizara un servidor perimetral en línea para realizar la conexión.
  
    
    
 **Flujo de llamadas de una conferencia organizada por usuario híbrido**
  
    
    

  
    
    
![Call flow hosted onprem.](images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)
  
    
    

  
    
    

  
    
    

### Servidor perimetral local con conferencias hospedadas en Office 365
<a name="bk_Figure5"> </a>

Cuando un usuario híbrido se une a una conferencia hospedada en línea, sabemos que la señalización y los elementos multimedia se destinarán a la nube de Office 365 y que, dado que el usuario se une desde Internet, normalmente se emplearía una ruta de Internet directa. Sin embargo, en algunos casos como aquellos en los que se producen restricciones por el firewall, la ruta de Internet directa no es posible. Entonces, un servidor perimetral local podrá retransmitir el tráfico multimedia, lo que hará que este vuelva a su red local antes de atravesar el circuito de ExpressRoute hacia la nube de Office 365.
  
    
    
 **Usuario local que se une a una llamada de conferencia en línea con un servidor perimetral local**
  
    
    

  
    
    
![Call flow for a conference call going through an edge server.](images/0178c170-5837-430d-84f1-582784bfef55.png)
  
    
    

  
    
    

  
    
    

### Llamada RTC con Skype Empresarial Cloud Connector Edition
<a name="bk_Figure6"> </a>

Uso de la  [Skype para Business Online nube conector Edition](https://aka.ms/CloudConnectorInstaller) ofrece conectividad de RTC con recursos locales como un tronco SIP o una puerta de enlace de RTC, o mediante un dispositivo de hardware mínimas integrar con Skype empresarial. Con la edición de conector de nube, los usuarios alojados en línea y actúen como normales usuarios en línea cuando no implican llamar a los planes. Señalización para escenarios de RTC se viaja entre el cliente y la nube a través de una conexión de ExpressRoute si está disponible y, a continuación, el tráfico de medios permanezca dentro de su WAN. En este caso, señalización gira alrededor de la nube de Office 365 y finaliza en el conector de la nube.
  
    
    
 **Llamada de RTC mediante el sistema telefónico en Office 365 y conector de nube**
  
    
    

  
    
    
![Call flow for a PSTN call using Cloud PBX Cloud Connector.](images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)
  
    
    

  
    
    

  
    
    

### Difusión de reunión de Skype con usuarios que se unen desde la red del cliente
<a name="bk_Figure6"> </a>

La Difusión de reunión de Skype es un caso de uso especial que consiste en una reunión de dos partes en la que cada parte tiene diferentes perfiles de transporte de red. La primera parte, que es la más importante desde el punto de vista del rendimiento de la red, es la reunión interna. Se trata de la parte en tiempo real de la reunión que incluye uno o varios puntos de conexión de cliente que se conectan al servidor de conferencias de la nube de Office 365. Los datos que se transmiten mediante esta parte de la reunión son exactamente los mismos que en el ejemplo anterior, en el que un usuario de Office 365 se unía a una conferencia en línea. 
  
    
    
Lo que distingue exclusivamente a la Difusión de reunión de Skype es que la reunión se distribuye a un gran número de asistentes a la conferencia mediante un servicio de streaming de difusión. Este servicio de streaming de difusión no es enrutable a través de ExpressRoute, pero en su lugar usa Internet con el soporte opcional de los servicios de red de entrega de contenido (CDN). Resulta muy útil a la hora de reconocer que el streaming de difusión es un flujo multimedia unidireccional, porque los asistentes escuchan pero no hablan, y admite el almacenamiento en búfer, por lo que le afecta mucho menos los problemas de rendimiento de la red, como la latencia, la pérdida de paquetes y las vibraciones. En lugar de optimizar el tráfico de difusión para abordar estos problemas, se optimiza para el uso del ancho de banda, puesto que hay, potencialmente, un gran número de asistentes recibiendo el elemento multimedia transmitido.
  
    
    
 **Difusión de reunión de Skype con usuarios desde la red del cliente**
  
    
    

  
    
    
![Call flow for Skype Meeting Broadcast.](images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)
  
    
    

  
    
    

  
    
    

## Patrones de flujos de llamadas según el tipo de implementación

En los ejemplos anteriores de flujos de llamadas comunes, y comprendiendo los principios generales que controlan los patrones del tráfico, las tablas siguientes ofrecen un resumen de los patrones de tráfico para una gran combinación de escenarios de implementaciones y usos. En estas tablas no se trata de capturar todas las posibles combinaciones de flujos de llamadas, sino que se han creado como una ayuda para comprender mejor sus principios generales.
  
    
    
Los datos se transmiten y aparecen en la lista como locales para la organización, no abandonan la red del cliente, Internet o ExpressRoute. Los patrones que aparecen a continuación se basan en las configuraciones de red más comunes (por ejemplo, los firewalls, la federación e Internet) y asumen que todas las organizaciones involucradas en los flujos federados o de varias partes tienen ExpressRoute. En la práctica, tener diferentes configuraciones podría derivar en otros patrones de tráfico, distintos a los que se indican a continuación.
  
    
    

### Flujos de llamadas para Skype Empresarial Online

Los escenarios de uso de Skype Empresarial Online implica usuarios que están alojados en línea y que pueden llamar desde su red interna o Internet. Los servidores locales no forman parte de estos escenarios, por lo que todas las conferencias o elementos multimedia relacionados con RTC fluirán hasta la nube de Office 365 y el servidor perimetral de los usuarios en línea también estará en la nube.
  
    
    
 **Resumen de los flujos de llamadas para Skype Empresarial Online**
  
    
    

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Escenario de uso** <br/> |**Puntos de conexión** <br/> |**Ruta de señalización** <br/> |**Ruta multimedia** <br/> |**Ejemplo de flujo** <br/> |**Notas** <br/> |
|Llamada de punto a punto  <br/> |Dos clientes, ambos en su red.  <br/> |ExpressRoute  <br/> |Local  <br/> | [Llamada de punto a punto para usuarios de Office 365 desde el interior de la red del cliente](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> ||
|Llamada de punto a punto  <br/> |Dos clientes, uno en su red (interno) y el otro en Internet (externo).  <br/> |Usuario interno: ExpressRoute  <br/> Usuario externo: Internet  <br/> |Usuario interno: ExpressRoute  <br/> Usuario externo: De Internet al servidor perimetral de Office 365.  <br/> | [Llamada de punto a punto para usuarios de Office 365 desde el interior de la red del cliente](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> |Asume que el firewall bloquea las conexiones directas entre clientes, que requiere un servidor perimetral en línea. El tráfico desde el usuario interno al servidor perimetral en línea sigue una ruta similar a la del servidor de conferencias para la llamada de conferencia.  <br/> |
|La llamada de punto a punto a un usuario en una organización federada  <br/> |Dos clientes, en su red (interno) y el usuario en línea en la red de la organización federada (federado).  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> | [Usuario en línea de su red que se une a una conferencia hospedada en línea](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> |Asume que un firewall bloquea las conexiones directas entre clientes, por lo que requiere un servidor perimetral en línea. El tráfico desde el usuario interno al servidor perimetral en línea sigue una ruta similar a la de un servidor de conferencias para la llamada de conferencia.  <br/> |
|Unirse a la llamada de conferencia por usuario en la red del cliente  <br/> |El cliente en su red y el servidor de conferencias en la nube de Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> | [Usuario en línea de su red que se une a una conferencia hospedada en línea](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> ||
|Unirse a la llamada de conferencia por usuario en Internet  <br/> |El cliente está en Internet y el servidor de conferencias en la nube de Office 365.  <br/> |Internet  <br/> |Internet  <br/> | [Usuario en línea de su red que se une a una conferencia hospedada en línea](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> ||
|Unirse a una conferencia hospedada por el servidor local de otra empresa  <br/> |El cliente en su red y el servidor de conferencias en el centro de datos de terceros.  <br/> |Internet  <br/> |Internet  <br/> |No aplicable  <br/> |Dado que el servidor de conferencias que hospeda la conferencia está en una red local de otro cliente, ningún dato pasará por la nube de Microsoft.  <br/> |
|Llamada RTC  <br/> |Cliente en red de clientes y los servidores de sistema de teléfono en la nube de Office 365  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> | [Usuario en línea de su red que se une a una conferencia hospedada en línea](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> ||
|Llamada RTC  <br/> |Cliente de internet y servidores de sistema de teléfono en la nube de Office 365  <br/> |Internet  <br/> |Internet  <br/> |No aplicable  <br/> |Los elementos multimedia y la señalización fluirán hasta el centro de datos de Office 365. Como el punto de conexión del cliente está en Internet, todos los datos fluirán hasta el centro de datos de Microsoft a través de Internet (incluso si se necesita un servidor perimetral en línea para la conectividad).  <br/> |
   

  
    
    

> [!NOTE]
> ExpressRoute se usará en una ruta multimedia desde el usuario ubicado en una red corporativa hasta un servidor perimetral en línea, pero no se usará si el servidor perimetral se utiliza en una implementación local de otro cliente. 
  
    
    


### Flujos de llamadas para la implementación híbrida de Skype Empresarial

Los flujos de llamadas híbridos se aplican cuando tiene una implementación de Skype Empresarial que incluye al menos algunos usuarios que están hospedados en local. Los flujos de llamadas de esta sección incluyen tanto conferencias locales como llamadas punto a punto o RTC con, al menos, un usuario alojado en local.
  
    
    

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Escenario de uso** <br/> |**Puntos de conexión** <br/> |**Ruta de señalización** <br/> |**Ruta multimedia** <br/> |**Ejemplo de flujo** <br/> |**Notas** <br/> |
|Llamada de punto a punto  <br/> |Dos clientes, en la red del cliente y alojados en local.  <br/> |Local  <br/> |Local  <br/> | [Llamada de punto a punto para usuarios de Office 365 desde el interior de la red del cliente](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> |Como los usuarios se alojan en local, la señalización fluye en local al centro de datos local en lugar de a la nube de Office 365.  <br/> |
|Llamada de punto a punto  <br/> |Dos clientes, ambos conectados desde la red del cliente. Uno está alojado en línea y el otro en local.  <br/> |Usuario en línea: ExpressRoute  <br/> Usuario local: local  <br/> |Local  <br/> | [Llamada de punto a punto para usuarios de Office 365 desde el interior de la red del cliente](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> |Solo el usuario alojado en línea envía tráfico de señalización a la nube de Office 365.  <br/> |
|La llamada de punto a punto a un usuario en una organización federada  <br/> |Dos clientes, uno local en la red del cliente (interno) y un usuario en línea en la red de la organización federada (federado).  <br/> |Usuario interno: local  <br/> Usuario federado: ExpressRoute  <br/> |Internet o ExpressRoute (depende de si se usa el servidor en línea o perimetral local)  <br/> | [Usuario en línea de su red que se une a una conferencia hospedada en línea](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) y parte de [Servidor perimetral local con conferencias hospedadas en Office 365](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure5) (para el tráfico multimedia). <br/> |Asume que un firewall bloquea las conexiones directas entre clientes, por lo que requiere un servidor perimetral en línea. La negociación de ICE ofrecerá tanto servidores en línea (por el usuario en línea) como servidores perimetrales en local (por el usuario local) para la conectividad.  <br/> |
|Unirse a la llamada de conferencia por usuario en la red del cliente (conferencia programada por el usuario en línea)  <br/> |El usuario en local en su red y el servidor de conferencias en la nube de Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> | [Usuario en línea de su red que se une a una conferencia hospedada en línea](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> |Los recursos de servidor para la llamada de conferencia se define por el organizador de reuniones. En este caso, la programó un usuario en línea, por lo que los recursos están en la nube de Office 365.  <br/> |
|Llamada RTC  <br/> |Usuario en local en su red y centro de datos Skype Empresarial local.  <br/> |Local  <br/> |Local  <br/> | [Llamada RTC con Skype Empresarial Cloud Connector Edition](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure6) <br/> |Similar escenario para usar Cloud Connector Edition, con la diferencia de que el usuario está alojado en local, de modo que la señalización permanece dentro de la red.  <br/> |
   

  
    
    

### Flujos de llamadas de Skype Empresarial con Cloud Connector

Todos los usuarios que se conectarán a Cloud Connector Edition están alojados en línea. Esto significa que las conferencias serán en línea y que la señalización sigue los mismos patrones que los usuarios en línea. Para otros escenarios distintos de las llamadas RTC, el flujo de llamadas será exactamente el mismo que el descrito anteriormente para Skype Empresarial Online.
  
    
    

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Escenario de uso** <br/> |**Puntos de conexión** <br/> |**Ruta de señalización** <br/> |**Ruta multimedia** <br/> |**Ejemplo de flujo** <br/> |**Notas** <br/> |
|Llamada RTC  <br/> |Usuario en línea en su red con Cloud Connector Edition.  <br/> |Local  <br/> |Local  <br/> | [Llamada RTC con Skype Empresarial Cloud Connector Edition](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure6) <br/> ||
|Llamada RTC  <br/> |Usuario en línea que usa Internet con Cloud Connector Edition.  <br/> |Internet  <br/> |Internet  <br/> |Combinación de  [Servidor perimetral local con conferencias hospedadas en Office 365](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure5) y [Llamada RTC con Skype Empresarial Cloud Connector Edition](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure6).  <br/> |Los usuarios de Internet se conectarán a través del servidor perimetral que se incluye en Cloud Connector y Cloud Connector se conectará a la red RTC.  <br/> |
   

## 
<a name="MT_Footer"> </a>


> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  
    
    


