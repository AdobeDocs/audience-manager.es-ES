---
description: Una visión general de alto nivel de cómo el Audience Manager intercambia información con otros proveedores y sistemas de datos.
seo-description: Una visión general de alto nivel de cómo el Audience Manager intercambia información con otros proveedores y sistemas de datos.
seo-title: Métodos de integración de datos
solution: Audience Manager
title: Métodos de integración de datos
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
feature: Third-party Integration
exl-id: 26225461-c35c-4db1-9517-99e82ce163b9
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 1%

---

# Métodos de integración de datos {#data-integration-methods}

Una visión general de alto nivel de cómo el Audience Manager intercambia información con otros proveedores y sistemas de datos.

## Métodos de integración de datos compatibles: Tiempo real y [!DNL Server-to-Server] {#supported-methods}

La elección del método de integración correcto depende de una combinación de requisitos comerciales y de las capacidades técnicas de su socio de datos. Audience Manager intercambia información de visitantes con otros proveedores de datos mediante cualquiera de los métodos siguientes:

* **Tiempo real:** transfiere los datos inmediatamente cuando un usuario visita el sitio. Este método también se conoce como integración *`synchronous`*.
* **Lote ([!DNL Server-to-Server]):** transfiere datos entre servidores según una programación establecida después de que un visitante haya abandonado la página. Este método también se conoce como integración *`out-of-band`* o *`asynchronous`*.

## Requisitos previos: Crear una taxonomía de características {#prereqs}

Antes de que comience el proceso de integración, recuerde [crear características](../features/traits/create-onboarded-rule-based-traits.md) y una [estructura de carpetas](../features/traits/trait-storage.md#create-trait-storage-folder) en la interfaz de usuario de [!DNL Audience Manager]. La taxonomía contendrá todos los [!UICONTROL traits] organizados en una jerarquía lógica.

## Casos de uso de integración {#integration-use-cases}

Resumen de casos de uso de los métodos de integración de datos de Audience Manager junto con las ventajas y desventajas de cada uno.

### Integraciones [!DNL Server-to-Server] en tiempo real

<!-- c_int_types_use_cases.xml -->

Una integración de datos [!DNL server-to-server] en tiempo real sincroniza rápidamente los datos de usuario entre los servidores del Audience Manager y otro sistema de segmentación. En la mayoría de los casos, el intercambio de datos se produce en segundos o minutos, según la tasa de actualización del sistema de determinación de objetivos. No obstante, tenga en cuenta que el sistema de destino determina este intervalo de actualización, no el Audience Manager. Además, la tasa de actualización puede variar entre diferentes sistemas. La integración [!UICONTROL server-to-server] en tiempo real es el tipo de integración preferido para los intercambios de datos. Audience Manager utiliza este método siempre que los socios de destino puedan admitirlo.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Ventajas: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Le permite calificar a los usuarios para segmentos sin verlos de nuevo en la página, en un reproductor de vídeo, etc. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Reduce el número de llamadas HTTP desde la página. Un menor número de llamadas ayuda a preservar la experiencia del usuario. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">Ayuda con la segmentación según el tiempo, de modo que puede realizar acciones rápidamente en un usuario cualificado. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">Resulta útil cuando se cambia a un DSP para la segmentación fuera del sitio. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Desventajas:</td>
  <td class="stentry"> Menos útil para la segmentación en el sitio cuando necesita dirigirse al usuario en la misma página o en la página siguiente, en función de si califica a un usuario para ese segmento.</td>
 </tr>
</table>

### [!DNL Server-to-Server] Integraciones por lotes

Una integración en lote [!DNL server-to-server] agrupa los datos y los envía a otros sistemas a intervalos establecidos en lugar de en tiempo casi real. Los intervalos de transferencia de datos comienzan a partir de 24 horas. Algunos proveedores de datos solo admiten este tipo de integración. Sin embargo, hemos observado una tendencia general de las integraciones por lotes hacia las metodologías de integración en tiempo real.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>Ventajas: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">Le permite calificar a los usuarios para segmentos sin verlos de nuevo en la página, en un reproductor de vídeo, etc. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">Útil para la segmentación que no distingue entre horas. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Desventajas:</td>
  <td class="stentry"> El intervalo de sincronización puede retrasar la segmentación con los datos más actuales.</td>
 </tr>
</table>

### Llamadas en tiempo real

Las llamadas en tiempo real intercambian datos con el Audience Manager inmediatamente, ya que un usuario visita el sitio o realiza acciones en la página. Con este método, los sistemas de segmentación obtienen los datos de clasificación de segmentos más actualizados y pueden tener en cuenta esa información durante una decisión de entrega de contenido o publicidad. Además, este proceso funciona con servidores de publicidad de editor en los que actualizamos segmentos cualificados a una cookie de origen que se lee en una llamada de publicidad como pares clave-valor. Actualmente, Audience Manager utiliza llamadas en tiempo real para integrarse con [!DNL Adobe Target] y otros sistemas de administración de contenido.

<table> 
 <tr>
  <td> <p>Ventajas: </p></td>
  <td> <p> Le permite dirigir la página, el área de contenido o la impresión de publicidad siguientes en función de la clasificación de segmentos más reciente. </p></td> 
 </tr> 
 <tr>
  <td> <p>Desventajas: </p></td>
  <td> <p>Agrega una llamada al Audience Manager desde la página.</p></td>
 </tr> 
</table>


### Píxeles sincronizados con sistemas de segmentación

La sincronización de píxeles asigna segmentos a píxeles en la página. El píxel se activa y transmite datos cuando un usuario cumple los requisitos para un segmento determinado. La sincronización de píxeles es un mecanismo rudimentario y poco fiable de transferencia de datos. Los proveedores y sistemas de datos de nivel superior rara vez lo utilizan.

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
    <li id="li_CD91F3DC92F2429293787D61506E5E04">No es fiable para la transmisión de datos. La pérdida del 5% al 20% es normal. </li>
   </ul></td>
 </tr> 
</table>

## Cómo elegir un método de envío de datos {#data-delivery-choices}

Describe motivos técnicos y empresariales para enviar datos mediante metodologías sincrónicas (en tiempo real) o asincrónicas (de servidor a servidor).

<!-- c_int_delivery_choices.xml -->

### Selección de un tipo de envío de datos

* **Consideraciones técnicas:** la entrega de datos depende de las capacidades técnicas del socio de datos. El Audience Manager puede enviar y recibir datos en tiempo real desde el explorador o mediante actualizaciones por lotes a través de procesos de comunicación sin conexión y servidor a servidor.
* **Consideraciones empresariales:** las razones comerciales para seleccionar un método de envío u otro dependen de las capacidades técnicas de su socio de destino y de cómo desee utilizar estos datos. Normalmente, las transferencias de datos sincrónicas son útiles cuando necesita tomar medidas sobre los datos del usuario inmediatamente. Las transferencias asincrónicas de datos pueden resultar útiles cuando no se requiere una acción inmediata y cuando tiene tiempo de crear perfiles de usuario más profundos para su uso posterior.

## Proceso de transferencia de datos en tiempo real {#real-time-data-transfer-process}

Información general sobre cómo realiza el Audience Manager un intercambio sincrónico de datos con un proveedor de terceros.

### Transferencia de datos en tiempo real

<!-- c_int_overview_sync.xml -->

Las transferencias de datos en tiempo real envían y reciben ID de segmento a medida que un usuario visita el sitio o realiza una acción en él. Normalmente, las transferencias de datos sincrónicas son útiles cuando necesita clasificar o segmentar a los usuarios de inmediato, ya que navegan por su inventario.

### Pasos de la integración de datos en tiempo real

El proceso de integración de datos en tiempo real funciona de la siguiente manera:

1. Un usuario visita el sitio de un cliente que contiene código de Audience Manager.
1. El Audience Manager carga un Iframe y realiza una llamada a [!UICONTROL Data Collection Server] ([!DNL DCS]).
1. El [!DNL DCS] llama al servidor de terceros (en tiempo real) para comprobar si el proveedor tiene información de segmento sobre el usuario.
1. El tercero devuelve al Audience Manager información de segmento sobre ese usuario.
1. El Audience Manager ingesta información de segmentos y la pone a disposición de los destinatarios.

![](assets/rt_reduce70.png)

## Proceso de transferencia de datos por lotes {#batch-data-transfer-process}

Información general sobre cómo el Audience Manager intercambia datos sincrónicamente (en tiempo real) con un proveedor de terceros.

### Integración de datos por lotes

<!-- c_int_overview_async.xml -->

El proceso de integración de datos por lotes ([!DNL server-to-server]) sigue la mayoría de los pasos descritos en el proceso de transferencia de datos en tiempo real. Sin embargo, en lugar de devolver los ID de segmento inmediatamente, la información del usuario se guarda en nuestros servidores y se sincroniza con un proveedor de datos de terceros a intervalos regulares. El proceso asincrónico de transferencia de datos resulta útil cuando:

* No se requieren transferencias de datos inmediatas.
* Recopilación de datos para crear un grupo grande de usuarios segmentados.
* Desea reducir las discrepancias de datos y las `HTTP` llamadas desde el explorador.

### Pasos de integración de datos por lotes

1. Un usuario visita un sitio del cliente.
1. El Audience Manager y el proveedor de datos de terceros asignan al visitante un ID único (normalmente con una cookie).
1. El Audience Manager llama al proveedor de datos de terceros para que coincida con los ID de visitante.
1. Las solicitudes programadas, normalmente con intervalos diarios, intercambian datos de segmentos del visitante entre el Audience Manager y el proveedor de datos de terceros.

![](assets/s2s_70.png)

Para obtener información sobre los lapsos de tiempo en los que el Audience Manager procesa las transferencias de archivos entrantes y salientes [!DNL Server-to-Server] ([!UICONTROL S2S]), consulte [Directrices de lapso de tiempo de informes y transferencia de archivos](../reference/reporting-file-transfer-timeframe.md).
