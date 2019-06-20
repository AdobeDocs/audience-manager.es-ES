---
description: Información general de alto nivel sobre cómo Audience Manager intercambia información con otros proveedores de datos y sistemas.
seo-description: Información general de alto nivel sobre cómo Audience Manager intercambia información con otros proveedores de datos y sistemas.
seo-title: Métodos de integración de datos
solution: Audience Manager
title: Métodos de integración de datos
uuid: 17 a 4179 a-e 99 b -49 eb -8 f 45-f 2946 afbd 27 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Métodos de integración de datos {#data-integration-methods}

Información general de alto nivel sobre cómo Audience Manager intercambia información con otros proveedores de datos y sistemas.

## Supported Data Integration Methods: Real-Time and Server-to-Server {#supported-methods}

Elegir el método de integración correcto depende de una combinación de requisitos comerciales y de las capacidades técnicas del socio de datos. Audience Manager intercambia información de visitantes con otros proveedores de datos mediante cualquiera de los métodos siguientes:

* **Tiempo real:** Transfiere datos inmediatamente cuando un usuario visita su sitio. This method is also known as a *`synchronous`* integration.
* **Lote (servidor a servidor):** Transfiere datos entre servidores de una programación establecida después de que un visitante abandonó la página. This method is also known as an *`out-of-band`* or *`asynchronous`* integration.

## Prerequisites: Create a Trait Taxonomy {#prereqs}

Before the integration process begins, remember to [create traits](../features/traits/create-onboarded-rule-based-traits.md) and a [folder structure](../features/traits/trait-storage.md#create-trait-storage-folder) in the [!DNL Audience Manager] UI. La taxonomía contendrá todas las características organizadas en una jerarquía lógica.

## Integration Use Cases {#integration-use-cases}

Un resumen de uso de mayúsculas y minúsculas de los métodos de integración de datos de Audience Manager junto con las ventajas y desventajas de cada uno.

### Integraciones de servidor a servidor en tiempo real

<!-- c_int_types_use_cases.xml -->

La integración de datos servidor a servidor en tiempo real sincroniza rápidamente los datos de usuario entre servidores de Audience Manager y otro sistema de segmentación. En la mayoría de los casos, el intercambio de datos se realiza en segundos o minutos, según la frecuencia de actualización del sistema de determinación de objetivos. Sin embargo, tenga en cuenta que el sistema de destino determina este intervalo de actualización, no Audience Manager. Además, la tasa de actualización puede variar entre diferentes sistemas. La integración servidor a servidor es el tipo de integración preferido para intercambios de datos. Audience Manager utiliza este método siempre que los socios de destino puedan admitirlo.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Ventajas: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Permite calificar a los usuarios para segmentos sin volver a verlos en la página, en un reproductor de vídeo, etc. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Reduce el número de llamadas HTTP desde la página. Menos llamadas ayudan a preservar la experiencia del usuario. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">Ayuda con objetivos sensibles a la hora para que pueda realizar acciones con un usuario cualificado rápidamente. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">Útil al pasar a un DSP para objetivos fuera del sitio. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Desventajas:</td>
  <td class="stentry"> Menos útil para la segmentación en el sitio cuando necesita dirigirse al usuario en la misma página o en la página siguiente, según la cualificación de un usuario para ese segmento.</td>
 </tr>
</table>

### Integraciones de lotes de servidor a servidor

Una integración de lotes de servidor a servidor crea datos y la envía a otros sistemas a intervalos establecidos en lugar de hacerlo en tiempo real. Los intervalos de transferencia de datos comienzan desde 24 horas. Algunos proveedores de datos solo admiten este tipo de integración. Sin embargo, hemos observado una tendencia general de las integraciones por lotes hacia las metodologías de integración en tiempo real.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>Ventajas: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">Permite calificar a los usuarios para segmentos sin volver a verlos en la página, en un reproductor de vídeo, etc. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">Resulta útil para objetivos que no dependen del tiempo. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Desventajas:</td>
  <td class="stentry"> El intervalo de sincronización puede retrasar el establecimiento de objetivos con los datos más actuales.</td>
 </tr>
</table>

### Llamadas en tiempo real

Las llamadas en tiempo real intercambian datos con Audience Manager inmediatamente, ya que un usuario visita su sitio o realiza acciones en la página. Con este método, los sistemas de determinación de objetivos obtienen los datos de cualificación de segmentos más actualizados y pueden tener en cuenta dicha información durante una decisión de entrega de publicidad o contenido. Además, este proceso funciona con servidores de publicidad del editor, donde actualizamos segmentos cualificados a una cookie de origen que se leen en una llamada de publicidad como pares clave-valor. Currently, Audience Manager uses real-time calls to integrate with [!DNL Target] and other content management systems.

<table> 
 <tr>
  <td> <p>Ventajas: </p></td>
  <td> <p> Permite dirigir la siguiente página, área de contenido o impresión de publicidad a partir de la calificación de segmentos más reciente. </p></td> 
 </tr> 
 <tr>
  <td> <p>Desventajas: </p></td>
  <td> <p>Agrega una llamada a Audience Manager desde la página.</p></td>
 </tr> 
</table>


### Sincronización de píxeles con sistemas de segmentación

La sincronización de píxeles asigna segmentos a píxeles en la página. El píxel activa y transmite datos cuando un usuario califica para un segmento en particular. La sincronización de píxeles es un mecanismo rudimable y poco fiable de transferencia de datos. Los proveedores y sistemas de datos de nivel superior raramente la utilizan.

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>Ventajas: </p></td>
  <td class="stentry"> <p> Transferencias de datos en tiempo real. </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>Desventajas: </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">Puede agregar muchas llamadas al lado del cliente desde la página. </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">No es confiable para la transmisión de datos. La pérdida del 5% al 20% es normal. </li>
   </ul></td>
 </tr> 
</table>

## How to Choose a Data Delivery Method {#data-delivery-choices}

Describe motivos técnicos y comerciales para enviar datos a través de metodologías sincrónicas (en tiempo real) o asincrónicas (servidor a servidor).

<!-- c_int_delivery_choices.xml -->

### Selección de un tipo de envío de datos

* **Consideraciones técnicas:** La entrega de datos depende de las capacidades técnicas del socio de datos. Audience Manager puede enviar y recibir datos en tiempo real desde el navegador o mediante actualizaciones por lotes mediante procesos de comunicación de servidor a servidor.
* **Consideraciones empresariales:** Las razones comerciales para seleccionar un método de entrega u otro dependen de las capacidades técnicas de su socio de destino y de cómo desee utilizar estos datos. Normalmente, las transferencias de datos sincrónicas son útiles cuando se necesita realizar acciones en los datos de usuario inmediatamente. Las transferencias de datos asincrónicas pueden resultar útiles cuando no se necesita acción inmediata y cuando tiene tiempo para generar perfiles de usuario más profundos para usarlos posteriormente.

## Real-Time Data Transfer Process {#real-time-data-transfer-process}

Descripción general general de cómo Audience Manager realiza un intercambio de datos sincrónico con un proveedor de terceros.

### Transferencia de datos en tiempo real

<!-- c_int_overview_sync.xml -->

Las transferencias de datos en tiempo real envían y reciben ID de segmento como visitas del usuario o realizan acciones en su sitio. Normalmente, las transferencias de datos sincrónicas resultan útiles cuando se necesita calificar o segmentar a los usuarios inmediatamente, ya que navegan por el inventario.

### Pasos de integración de datos en tiempo real

El proceso de integración de datos en tiempo real funciona de la siguiente manera:

1. Un usuario visita el sitio de un cliente que contiene el código de Audience Manager.
1. Audience Manager loads an Iframe and makes a call to the [!UICONTROL Data Collection Server] ([!UICONTROL DCS]).
1. [!UICONTROL DCS] Llama al servidor de terceros (en tiempo real) para comprobar si el proveedor tiene información de segmento sobre el usuario.
1. El tercero devuelve información de segmentos sobre ese usuario a Audience Manager.
1. Audience Manager ingesta la información del segmento y la pone a disposición para la segmentación.

![](assets/rt_reduce70.png)

## Batch Data Transfer Process {#batch-data-transfer-process}

Información general general sobre cómo Audience Manager intercambia datos sincrónicamente (en tiempo real) con un proveedor de terceros.

### Integración de datos por lotes

<!-- c_int_overview_async.xml -->

El proceso de integración de datos por lotes (servidor a servidor) sigue la mayoría de los pasos descritos en el proceso de transferencia de datos en tiempo real. Sin embargo, en lugar de devolver ID de segmento inmediatamente, la información del usuario se guarda en nuestros servidores y se sincroniza con un proveedor de datos de terceros a intervalos regulares. El proceso asincrónico de transferencia de datos es útil cuando:

* No se requieren transferencias de datos inmediatas.
* Recopilación de datos para crear un gran grupo de usuarios segmentados.
* You want to reduce data discrepancies and `HTTP` calls from the browser.

### Pasos de integración de datos por lotes

1. Un usuario visita un sitio de clientes.
1. Audience Manager y el proveedor de datos de terceros asignan al visitante un ID único (generalmente con una cookie).
1. Audience Manager llama al proveedor de datos de terceros para que coincida con las ID de los visitantes.
1. Una solicitud programada, generalmente en intervalo diario, intercambia los datos de segmento de visitantes entre Audience Manager y el proveedor de datos de terceros.

![](assets/s2s_70.png)

For information describing the time frames when Audience Manager processes inbound and outbound Server-to-Server ([!UICONTROL S2S]) file transfers, see [Reporting and File Transfer Time-Frame Guidelines](../reference/reporting-file-transfer-timeframe.md).
