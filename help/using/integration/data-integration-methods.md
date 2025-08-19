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

## Métodos de integración de datos compatibles: Tiempo real y [!DNL Server-to-Server] {#supported-methods}

La elección del método de integración adecuado depende de una combinación de requisitos empresariales y de las capacidades técnicas de los socio de datos. Audience Manager intercambia información visitante con otros proveedores de datos mediante cualquiera de los siguientes métodos:

* **Tiempo real:** transfiere datos inmediatamente cuando un usuario visita su sitio. Este método también se conoce como integración *`synchronous`* .
* **Lote ([!DNL Server-to-Server]):** transfiere datos entre servidores siguiendo una programación determinada después de que un visitante haya abandonado el Página. Este método también se conoce como integración *`out-of-band`* de OR *`asynchronous`* .

## Requisitos previos: Crear una taxonomía de rasgos {#prereqs}

Antes de que comience el proceso de integración, recuerde [crear características](../features/traits/create-onboarded-rule-based-traits.md) y una [estructura](../features/traits/trait-storage.md#create-trait-storage-folder) de carpetas en el [!DNL Audience Manager] IU. La taxonomía contendrá todos sus [!UICONTROL traits] organizados en un jerarquía lógico.

## Casos de uso de integración {#integration-use-cases}

Un resumen de casos de uso de Audience Manager métodos de integración de datos junto con las ventajas y desventajas de cada uno.

### Integraciones en tiempo [!DNL Server-to-Server] real

<!-- c_int_types_use_cases.xml -->

Una integración de datos en tiempo [!DNL server-to-server] real sincroniza rápidamente usuario datos entre Audience Manager servidores y otro sistema direccionamiento. En la mayoría de los casos, el intercambio de datos tiene lugar en segundos o minutos, dependiendo de la frecuencia de actualización del sistema direccionamiento. Tenga en cuenta, sin embargo, que el sistema de destino determina este intervalo de actualización, no Audience Manager. Además, la frecuencia de actualización puede variar entre diferentes sistemas. Una integración en tiempo [!UICONTROL server-to-server] real es el tipo de integración preferido para el intercambio de datos. Audience Manager utiliza este método siempre que direccionamiento socios puedan admitirlo.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Ventajas: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Permite calificar usuarios para segmentos sin volver a verlos en la Página, en un reproductor de vídeo, etc. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Reduce el número de llamadas HTTP desde la Página. Menos llamadas ayuda a preservar el experiencia del usuario. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">Ayuda con las direccionamiento urgentes para que pueda tomar medidas sobre un usuario calificado rápidamente. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">Resulta útil cuando se cambia a una DSP para direccionamiento fuera del sitio. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Desventajas:</td>
  <td class="stentry"> Menos útil para direccionamiento en el sitio cuando necesita destino la usuario en el mismo Página o en la siguiente Página, en función de la calificación de un usuario para ese segmento.</td>
 </tr>
</table>

### [!DNL Server-to-Server] Integraciones Lote

Una [!DNL server-to-server] integración por lotes agrupa datos y los envía a otros sistemas a intervalos establecidos en lugar de casi en tiempo real. Los intervalos de transferencia de datos inicio de 24 horas. Algunos proveedores de datos solo admiten este tipo de integración. Sin embargo, hemos visto una tendencia general de alejarse de las integraciones por lotes hacia metodologías de integración en tiempo real.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>Ventajas: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">Permite calificar usuarios para segmentos sin volver a verlos en la Página, en un reproductor de vídeo, etc. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">Útil para direccionamiento que no son sensibles al tiempo. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Desventajas:</td>
  <td class="stentry"> El intervalo de sincronización puede retrasar la direccionamiento respecto a los datos más recientes.</td>
 </tr>
</table>

### Llamadas en tiempo real

Las llamadas en tiempo real intercambian datos con Audience Manager de forma inmediata, cuando un usuario visita su sitio o realiza una acción en el Página. Con este método, direccionamiento sistemas obtienen los datos de calificación de segmento más actualizados y pueden tomar esa información en cuenta durante una decisión contenido o envío anuncios. Además, este proceso funciona con publicador servidores anuncios donde actualizamos segmentos calificados a un cookie de origen que se lee en un llamada de anuncio como pares clave-valor. Actualmente, Audience Manager utiliza llamadas en tiempo real a integrar con [!DNL Adobe Target] y otros sistemas gestión de contenidos.

<table> 
 <tr>
  <td> <p>Ventajas: </p></td>
  <td> <p> Le permite destino el siguiente Página, contenido área o impresión de anuncios según la calificación segmento más reciente. </p></td> 
 </tr> 
 <tr>
  <td> <p>Desventajas: </p></td>
  <td> <p>Agrega una llamada al Audience Manager desde el Página.</p></td>
 </tr> 
</table>


### Los píxeles se sincronizan con los sistemas de destino

La sincronización de píxeles asigna segmentos a píxeles de la Página. El píxel activa y transmite datos cuando un usuario cumple los requisitos para un segmento concreto. La sincronización de píxeles es un mecanismo de transferencia de datos rudimentario y poco fiable. Los proveedores y sistemas de datos de primer nivel rara vez lo utilizan.

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>Ventajas: </p></td>
  <td class="stentry"> <p> Transferencias de datos en tiempo real. </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>Desventajas: </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">Puede agregar muchas llamadas lado del cliente desde el Página. </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">Poco fiable para la transmisión de datos. La pérdida del 5% al 20% es normal. </li>
   </ul></td>
 </tr> 
</table>

## Cómo elegir un método de envío de datos {#data-delivery-choices}

Describe los motivos técnicos y empresariales para enviar datos a través de metodologías sincrónicas (en tiempo real) o asincrónicas (de servidor a servidor).

<!-- c_int_delivery_choices.xml -->

### Selección de un tipo de envío de datos

* **Consideraciones técnicas:** la envío de datos depende de las capacidades técnicas de los socio de datos. Audience Manager puede enviar/recibir datos en tiempo real desde el explorador o mediante actualizaciones por lotes a través de procesos de comunicación sin conexión servidor a servidor.
* **Empresa Consideraciones:** Las razones comerciales para seleccionar un método de envío u otro dependen de las capacidades técnicas de su socio de destino y de cómo desea utilizar estos datos. Normalmente, las transferencias de datos sincrónicas son útiles cuando necesita tomar medidas sobre usuario datos inmediatamente. Las transferencias de datos asincrónicas pueden ser útiles cuando no se requiere una acción inmediata y cuando tiene tiempo para versión perfiles de usuario más profundos para su uso posterior.

## Proceso de transferencia de datos en tiempo real {#real-time-data-transfer-process}

Una descripción general de cómo Audience Manager realiza un intercambio de datos sincrónico con un proveedor terceros.

### Transferencia de datos en tiempo real

<!-- c_int_overview_sync.xml -->

Las transferencias de datos en tiempo real envían y reciben ID de segmento a medida que un usuario visita o realiza una acción en su sitio. Por lo general, las transferencias de datos sincrónicas son útiles cuando necesita calificar o segmento usuarios de inmediato, mientras navegan por su inventario.

### Pasos de integración de datos en tiempo real

El proceso de integración de datos en tiempo real funciona de la siguiente manera:

1. Un usuario visita el sitio de un cliente que contiene Audience Manager código.
1. Audience Manager carga un Iframe y realiza una llamada al [!UICONTROL Data Collection Server] ([!DNL DCS]).
1. El [!DNL DCS] llama al servidor terceros (en tiempo real) para verificar si el proveedor tiene alguna información segmento sobre el usuario.
1. El tercero devuelve segmento información sobre esa usuario a Audience Manager.
1. Audience Manager ingiere segmento información y la pone a disposición de direccionamiento.

![](assets/rt_reduce70.png)

## Lote proceso de transferencia de datos {#batch-data-transfer-process}

Descripción general de cómo Audience Manager intercambia datos sincrónicamente (en tiempo real) con un proveedor terceros.

### Integración de datos de Lote

<!-- c_int_overview_async.xml -->

El proceso de integración de datos por lotes ([!DNL server-to-server]) sigue la mayoría de los pasos descritos en el proceso de transferencia de datos en tiempo real. Sin embargo, en lugar de devolver segmento ID inmediatamente, usuario información se guarda en nuestros servidores y se sincroniza con un proveedor de datos de terceros a intervalos regulares. El proceso asincrónico de transferencia de datos resulta útil cuando:

* No se requieren transferencias de datos inmediatas.
* La recopilación de datos para versión un grupo grande de usuarios segmentados.
* Desea reducir las discrepancias en los datos y `HTTP` las llamadas desde la explorador.

### Pasos de integración de datos de Lote

1. Un usuario visita el sitio de un cliente.
1. Audience Manager y el proveedor de datos del terceros asignan al visitante un ID único (normalmente con un cookie).
1. Audience Manager llama al proveedor de datos de terceros para que coincida con visitante ID.
1. Un solicitud programado, normalmente en un intervalo diario, intercambia datos visitante segmento entre Audience Manager y el proveedor de datos del terceros.

![](assets/s2s_70.png)

Para obtener información sobre los intervalos de tiempo en los que Audience Manager procesa las transferencias de archivos entrantes y salientes [!DNL Server-to-Server] ([!UICONTROL S2S]), consulte [Directrices para la elaboración de informes y la](../reference/reporting-file-transfer-timeframe.md) transferencia de Archivo.
