---
description: Una visión general de alto nivel de cómo Audience Manager intercambia información con otros proveedores y sistemas de datos.
seo-description: A high-level overview of how Audience Manager exchanges information with other data providers and systems.
seo-title: Data Integration Methods
solution: Audience Manager
title: Métodos de integración de datos
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
feature: Third-party Integration
exl-id: 26225461-c35c-4db1-9517-99e82ce163b9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 0%

---

# Métodos de integración de datos {#data-integration-methods}

Una visión general de alto nivel de cómo Audience Manager intercambia información con otros proveedores y sistemas de datos.

## Métodos de integración de datos admitidos: tiempo real y [!DNL Server-to-Server] {#supported-methods}

La elección del método de integración adecuado depende de una combinación de requisitos empresariales y de las capacidades técnicas de su socio de datos. El Audience Manager intercambia información del visitante con otros proveedores de datos mediante cualquiera de los siguientes métodos:

* **Tiempo real:** transfiere datos inmediatamente a medida que un usuario visita el sitio. Este método también se conoce como integración de *`synchronous`*.
* **Lote ([!DNL Server-to-Server]):** Transfiere datos entre servidores según una programación establecida después de que un visitante haya abandonado la página. Este método también se conoce como integración de *`out-of-band`* o *`asynchronous`*.

## Requisitos previos: Crear una taxonomía de rasgos {#prereqs}

Antes de comenzar el proceso de integración, recuerde [crear características](../features/traits/create-onboarded-rule-based-traits.md) y una [estructura de carpetas](../features/traits/trait-storage.md#create-trait-storage-folder) en la interfaz de usuario de [!DNL Audience Manager]. La taxonomía contendrá todos sus [!UICONTROL traits] organizados en una jerarquía lógica.

## Casos de uso de integración {#integration-use-cases}

Un caso de uso que resume los métodos de integración de datos de Audience Manager, junto con las ventajas y desventajas de cada uno.

### Integraciones en tiempo real de [!DNL Server-to-Server]

<!-- c_int_types_use_cases.xml -->

Una integración de datos de [!DNL server-to-server] en tiempo real sincroniza rápidamente los datos de usuario entre los servidores de Audience Manager y otro sistema de segmentación. En la mayoría de los casos, el intercambio de datos se produce en segundos o minutos, según la velocidad de actualización del sistema de destino. Sin embargo, tenga en cuenta que el sistema de destino determina este intervalo de actualización, no el Audience Manager. Además, la frecuencia de actualización puede variar entre los distintos sistemas. Una integración de [!UICONTROL server-to-server] en tiempo real es el tipo de integración preferido para los intercambios de datos. El Audience Manager utiliza este método siempre que los socios de segmentación pueden admitirlo.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Ventajas: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Permite clasificar a los usuarios para segmentos sin verlos de nuevo en la página, en un reproductor de vídeo, etc. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Reduce el número de llamadas HTTP desde la página. Menos llamadas ayuda a preservar la experiencia del usuario. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">Ayuda con la segmentación con distinción de tiempo, de modo que puede realizar acciones con un usuario cualificado rápidamente. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">DSP Útil cuando se mueve a un sitio para la segmentación fuera del sitio de un grupo de destinatarios. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Desventajas:</td>
  <td class="stentry"> Menos útil para la segmentación en el sitio cuando necesita segmentar al usuario en la misma página o en la página siguiente, según si el usuario cumple los requisitos para ese segmento.</td>
 </tr>
</table>

### [!DNL Server-to-Server] integraciones por lotes

Una integración por lotes de [!DNL server-to-server] agrupa datos y los envía a otros sistemas a intervalos establecidos en lugar de hacerlo en tiempo casi real. Los intervalos de transferencia de datos comienzan a partir de 24 horas. Algunos proveedores de datos solo admiten este tipo de integración. Sin embargo, hemos visto una tendencia general que se aleja de las integraciones por lotes hacia metodologías de integración en tiempo real.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>Ventajas: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">Permite clasificar a los usuarios para segmentos sin verlos de nuevo en la página, en un reproductor de vídeo, etc. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">Útil para direccionamientos que no son sensibles al tiempo. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Desventajas:</td>
  <td class="stentry"> El intervalo de sincronización puede retrasar el direccionamiento para los datos más actuales.</td>
 </tr>
</table>

### Llamadas en tiempo real

Las llamadas en tiempo real intercambian datos con Audience Manager inmediatamente, a medida que un usuario visita su sitio o realiza acciones en la página. Con este método, los sistemas de segmentación obtienen los datos de calificación de segmentos más actualizados y pueden tener en cuenta esa información durante una decisión de entrega de contenido o publicidad. Además, este proceso funciona con servidores de publicidad de editores en los que actualizamos segmentos calificados a una cookie de origen que se lee en una llamada de anuncio como pares clave-valor. Actualmente, Audience Manager usa llamadas en tiempo real para integrarse con [!DNL Adobe Target] y otros sistemas de administración de contenido.

<table> 
 <tr>
  <td> <p>Ventajas: </p></td>
  <td> <p> Permite segmentar la página, el área de contenido o la impresión de publicidad siguiente en función de la calificación de segmentos más reciente. </p></td> 
 </tr> 
 <tr>
  <td> <p>Desventajas: </p></td>
  <td> <p>Agrega una llamada al Audience Manager desde la página.</p></td>
 </tr> 
</table>


### Píxeles sincronizados con sistemas de segmentación

La sincronización de píxeles asigna segmentos a píxeles en la página. El píxel se activa y transmite datos cuando un usuario cumple los requisitos para un segmento en particular. La sincronización de píxeles es un mecanismo de transferencia de datos rudimentario y poco fiable. Los principales proveedores y sistemas de datos rara vez lo utilizan.

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>Ventajas: </p></td>
  <td class="stentry"> <p> Transferencias de datos en tiempo real. </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>Desventajas: </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">Puede agregar muchas llamadas del lado del cliente desde la página. </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">No fiable para la transmisión de datos. 5% a 20% de pérdida es normal. </li>
   </ul></td>
 </tr> 
</table>

## Cómo elegir un método de entrega de datos {#data-delivery-choices}

Describe motivos técnicos y empresariales para enviar datos mediante metodologías sincrónicas (tiempo real) o asincrónicas (servidor a servidor).

<!-- c_int_delivery_choices.xml -->

### Selección de un tipo de entrega de datos

* **Consideraciones técnicas:** La entrega de datos depende de las capacidades técnicas del socio de datos. El Audience Manager puede enviar y recibir datos en tiempo real desde el explorador o mediante actualizaciones por lotes a través de procesos de comunicación sin conexión de servidor a servidor.
* **Consideraciones comerciales:** Las razones comerciales para seleccionar un método de envío u otro dependen de las capacidades técnicas de su socio de destino y de cómo desee utilizar estos datos. Normalmente, las transferencias de datos sincrónicas son útiles cuando necesita realizar acciones en los datos de usuario inmediatamente. Las transferencias asincrónicas de datos pueden resultar útiles cuando no se requiere una acción inmediata y cuando tiene tiempo para crear perfiles de usuario más profundos para su uso posterior.

## Proceso de transferencia de datos en tiempo real {#real-time-data-transfer-process}

Información general sobre cómo Audience Manager realiza un intercambio sincrónico de datos con un proveedor de terceros.

### Transferencia de datos en tiempo real

<!-- c_int_overview_sync.xml -->

Las transferencias de datos en tiempo real envían y reciben ID de segmento a medida que un usuario visita su sitio o realiza alguna acción en él. Normalmente, las transferencias sincrónicas de datos son útiles cuando necesita calificar o segmentar a los usuarios de inmediato, a medida que navegan por el inventario.

### Pasos de integración de datos en tiempo real

El proceso de integración de datos en tiempo real funciona de la siguiente manera:

1. Un usuario visita el sitio de un cliente que contiene código de Audience Manager.
1. El Audience Manager carga un Iframe y realiza una llamada a [!UICONTROL Data Collection Server] ([!DNL DCS]).
1. El [!DNL DCS] llama al servidor de terceros (en tiempo real) para comprobar si el proveedor tiene información de segmento sobre el usuario.
1. El tercero devuelve al Audience Manager la información del segmento sobre ese usuario.
1. El Audience Manager ingiere información del segmento y la pone a disposición de la segmentación.

![](assets/rt_reduce70.png)

## Proceso de transferencia de datos por lotes {#batch-data-transfer-process}

Una visión general de cómo Audience Manager intercambia datos sincrónicamente (en tiempo real) con un proveedor de terceros.

### Integración de datos por lotes

<!-- c_int_overview_async.xml -->

El proceso de integración de datos por lotes ([!DNL server-to-server]) sigue la mayoría de los pasos descritos en el proceso de transferencia de datos en tiempo real. Sin embargo, en lugar de devolver los ID de segmento inmediatamente, la información de los usuarios se guarda en nuestros servidores y se sincroniza con un proveedor de datos de terceros a intervalos regulares. El proceso asincrónico de transferencia de datos es útil cuando:

* No se requieren transferencias de datos inmediatas.
* Recopilación de datos para crear un gran grupo de usuarios segmentados.
* Desea reducir las discrepancias en los datos y las llamadas de `HTTP` desde el explorador.

### Pasos de integración de datos por lotes

1. Un usuario visita un sitio de cliente.
1. El Audience Manager y el proveedor de datos de terceros asignan al visitante un ID único (normalmente con una cookie).
1. El Audience Manager llama al proveedor de datos de terceros para buscar coincidencias con los ID de visitante.
1. Una solicitud programada, normalmente a intervalos diarios, intercambia datos de segmentos del visitante entre Audience Manager y el proveedor de datos de terceros.

![](assets/s2s_70.png)

Para obtener información que describe los lapsos de tiempo en los que el Audience Manager procesa las transferencias de archivos entrantes y salientes de [!DNL Server-to-Server] ([!UICONTROL S2S]), consulte [Directrices para el intervalo de tiempo para la creación de informes y la transferencia de archivos](../reference/reporting-file-transfer-timeframe.md).
