---
description: Respuestas a preguntas comunes sobre la combinación de perfiles y el gráfico de dispositivos.
keywords: Identificador de organización
seo-description: Respuestas a preguntas comunes sobre la combinación de perfiles y el gráfico de dispositivos.
seo-title: Preguntas frecuentes sobre las reglas de combinación de perfiles y Device Graph
solution: Audience Manager
title: Preguntas frecuentes sobre las reglas de combinación de perfiles y Device Graph
uuid: ba 7986 f 1-078 f -4162-aef 3-b 5 c 8740 cebf 4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Merge Rules and Device Graph FAQ{#profile-merge-rules-and-device-graph-faq}

Respuestas a preguntas comunes sobre la combinación de perfiles y el gráfico de dispositivos.

<!-- 

profile-merge-faq.xml

 -->

## Device Graph Basics {#device-graph-basics}

**¿Qué es un gráfico de dispositivos?**

Un gráfico de dispositivo es un conjunto de asignaciones de ID que define grupos de dispositivos anónimos. Asocia estos dispositivos a una persona o un hogar en función de elementos comunes en las señales recopiladas de cada dispositivo. Estas señales ayudan a identificar dispositivos a nivel individual o doméstico.

<br> 

**¿Qué es un gráfico de dispositivos externo?**

An external device graph is any device graph in [!DNL Audience Manager] that has not been created exclusively from your own cross-device data sources. For example, when you create a [Profile Merge Rule](../features/profile-merge-rules/merge-rules-start.md) and choose the [!UICONTROL Co-op Device Graph] or third-party device graph options, you're working with an external device graph. See [Device Options](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

<br> 

**¿Cuáles son algunos casos de uso común para utilizar un gráfico de dispositivos externo en un[!UICONTROL Profile Merge Rule]?**

The main objective of using a device graph in a [!UICONTROL Profile Merge Rule] is to evaluate and qualify multiple devices belonging to a single person or household for a specific segment. El segmento mismo puede tener varios usos, por ejemplo, segmentar una audiencia de perspectivas y anuncios ofrecidos por un DSP o personalizando la experiencia en el sitio de un cliente a través de una plataforma de personalización en el sitio. See [External Device Graph Use Cases](../features/profile-merge-rules/external-graph-use-cases.md).

<br> 

**¿Audience Manager proporciona compatibilidad global con los gráficos de dispositivos externos?**

No. Los gráficos de dispositivos externos solo están disponibles en Estados Unidos y Canadá.

<br> 

**¿Con qué frecuencia[!DNL Audience Manager]actualiza los datos de gráficos de dispositivos externos?**

Una vez a la semana.

<br> 

## Device Graphs and Profile Merge Rules {#device-graph-profile-merge-rules}

**¿Cómo[!DNL Audience Manager]utiliza un gráfico de dispositivo?**

In [!DNL Audience Manager], device graphs appear as configuration options when you [create a Profile Merge Rule](../features/profile-merge-rules/merge-rules-start.md). Through your [!UICONTROL Profile Merge Rules], these device graphs help [!DNL Audience Manager]:

* Combine varios perfiles de dispositivo juntos. Esto crea un solo superconjunto de características.
* Evalúe el superconjunto de características para la cualificación de segmentos (en lugar de evaluar individualmente cada perfil de dispositivo).
* Agregue dispositivos cualificados a los segmentos disponibles.

<br> 

**¿Cuántos[!UICONTROL Profile Merge Rules]puedo crear?**

Currently, you can create a maximum of 3 [!UICONTROL Profile Merge Rules].

<br> 

**¿Cuántos perfiles de dispositivo[!DNL Audience Manager]se combinan y leen al utilizar un gráfico de dispositivos en[!UICONTROL Profile Merge Rule]una?**

When qualifying a device for a segment using a [!UICONTROL Profile Merge Rule], Audience Manager merges and reads the current device profile and a maximum of 3 additional device profiles linked by your selected device graph option.

<br> 

**¿Qué dispositivos cumplen los requisitos de un segmento al utilizar un gráfico de dispositivos en[!UICONTROL Profile Merge Rule]una?**

The devices [!DNL Audience Manager] merges and reads are the same devices that are qualified for a segment.

>[!NOTE]
>
>For external device graphs, [!DNL Audience Manager] stores the mapping between devices at the platform level and selects 3 without evaluating their relationship to the devices seen in your instance of [!DNL Audience Manager].

<br> 

**¿Qué dispositivos **pueden calificarse para un segmento con un[!UICONTROL Profile Merge Rule]gráfico de dispositivos?**

To qualify for a segment, devices must have been seen by Audience Manager on our [edge data servers](../reference/system-components/components-edge.md) after the segment was created. Además, los servidores Edge:

* Almacenar datos de perfil para un máximo de 14 días.
* Elimine un perfil de dispositivo si ha estado inactivo durante más de 14 días. Nota: Esta acción solo elimina datos del borde. Otros sistemas conservarán los registros para intervalos de tiempo más largos. See the [Privacy and Data Retention FAQ](../faq/faq-privacy.md).
* Reset the 14-day interval if [!DNL Audience Manager] records any activity for that profile across the entire platform.

See also, [Data Collection Components](../reference/system-components/components-data-collection.md).

<br> 

**¿Dónde[!DNL Audience Manager]se pueden enviar segmentos que se hayan calificado con[!UICONTROL Profile Merge Rule]un gráfico de dispositivos?**

[!DNL Audience Manager] puede enviar segmentos a un destino en archivos por lotes o en tiempo real. And, as noted in the FAQ entry above, To qualify for a segment, devices must have been seen by [!DNL Audience Manager] on our [edge data servers](../reference/system-components/components-edge.md) after the segment was created.

<br> 

## Segments, Device Graphs, and Profile Merge Rules {#segments-device-graphs-rules}

**¿Cómo[!DNL Audience Manager]dessegmenta un dispositivo cuando ya no está cualificado para un segmento con una[!UICONTROL Profile Merge Rule]gráfica de dispositivo?**

Audience Manager merges up to four devices when evaluating segments with a [!UICONTROL Profile Merge Rule] that uses a device graph. Si se emite la señal de cancelación de segmento, el dispositivo actual y tres dispositivos adicionales vistos en tiempo real se eliminarán del segmento en el destino. Por ejemplo, en un clúster de seis dispositivos, se combinan, evalúan y califican hasta cuatro dispositivos para un segmento. Del mismo modo, se combinan, evalúan y no segmentan hasta cuatro dispositivos.

<br> 

**Si un destino puede no ser de segmentos,¿se eliminarán los dispositivos de los segmentos que[!UICONTROL Profile Merge Rules]utilizan un gráfico de dispositivos?**

Sí. Consulte la explicación anterior.

<br> 

**Si creo un segmento con un[!UICONTROL Profile Merge Rule]gráfico de dispositivos y el segmento está usando datos en tiempo real y en el que se ha introducido,¿se actualizará mi segmento a medida que cambian los datos introducidos en el sistema?**

No. Currently, [!DNL Audience Manager] evaluates segments with a [!UICONTROL Profile Merge Rule] that uses a device graph in real-time only. Updates made to on-boarded traits after the segment has been evaluated will be used to qualify the segment when the device is next seen by our [edge data servers](../reference/system-components/components-edge.md). Esto supone que el perfil del dispositivo sigue activo en los servidores Edge y que los datos cargados están disponibles para esos sistemas. See also, the [Privacy and Data Retention FAQ](../faq/faq-privacy.md).

<br> 

**¿Incluyen las estimaciones de tamaño de segmento los dispositivos que cumplen los requisitos de un segmento en función de las conexiones proporcionadas por una[!UICONTROL Profile Merge Rule]opción de gráfico de dispositivos?**

No. See the definitions for the [!UICONTROL Estimated Real-Time Population] and [!UICONTROL Estimated Total Population] in [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

**[!UICONTROL Addressable Audiences]¿Incluye dispositivos que cumplen los requisitos de un segmento en función de las conexiones proporcionadas por un[!UICONTROL Profile Merge Rule]usuario que utiliza una opción gráfica de dispositivo?**

Sí.

<br> 

**Si un segmento utiliza y[!UICONTROL Profile Merge Rule][!UICONTROL No Authenticated Profile]las características que califican dispositivos para el segmento se almacenan únicamente en el perfil autenticado,¿será 0 la población total del segmento?**

No. Actualmente, Audience Manager cuenta los dispositivos asignados al perfil autenticado como elegibles para el segmento.

<br> 

## Trait Frequency, Device Graphs, and Profile Merge Rules {#trait-freq-device-rules}

**¿Cómo[!DNL Audience Manager]se calcula la frecuencia de características calculadas con un[!UICONTROL Profile Merge Rule]gráfico de dispositivos?**

La frecuencia de características se define por la suma del número de cualificaciones para un rasgo específico en varios dispositivos. Para ayudarle a comprender esto, observe el siguiente caso de uso.

<table id="table_DE7A308705C84B93B3089CAD2228569E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condiciones</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_52EA0F142E3F488CAAC7CF541E7F3472"> 
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">El dispositivo A y el dispositivo B están vinculados por un gráfico de dispositivos. </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">You have a <span class="wintitle"> Profile Merge Rule</span> that uses a device graph option. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">Un solo segmento (Segmento 1) compuesto por un solo rasgo (Trait 1), donde Trait 1 tiene una frecuencia de 8. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Acciones</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> lee y combina los perfiles de dispositivo para el Dispositivo A y el Dispositivo B. A continuación vemos lo siguiente: </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">El dispositivo A ha calificado para Trait 1 veces. Tiene una frecuencia de 3 para Trait 1. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">El dispositivo B ha calificado para características 1 cinco veces. Tiene una frecuencia de 5 para Trait 1. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> suma la frecuencia de Trait 1 y utiliza 8 (3 + 5 = 8) para decidir la cualificación de segmentos. El dispositivo A y el dispositivo B cumplen los requisitos del segmento 1 porque tienen una frecuencia de 8. </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

## Reports, Device Graphs, and Profile Merge Rules {#reports-device-graphs-rules}

**¿Puedo ver el número de dispositivos a los que se puede acceder[!UICONTROL Profile Merge Rule]mediante un gráfico de dispositivos?**

Sí. Reports return data at the [!UICONTROL Profile Merge Rule] level. Los datos del informe se actualizan diariamente. Los datos se basan en los dispositivos que se ven en su cuenta, no en los vinculados por un gráfico de dispositivos. See [Report Metrics for Profile Merge Rules](../features/profile-merge-rules/profile-link-metrics.md).

<br> 

**¿Puedo ver el número de dispositivos cualificados para un segmento específico en *tiempo real*con[!UICONTROL Profile Merge Rules]un gráfico de dispositivos?**

Sí. La métrica de población en tiempo real captura las calificaciones de segmentos del dispositivo actual (el dispositivo visto en tiempo real) utilizando los perfiles de todos los dispositivos vinculados por un gráfico de dispositivos.

<table id="table_D37A51E99B314C04A96A084491A5FEC7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento de caso de uso </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condiciones</b> </p> </td> 
   <td colname="col2"> <p>Supongamos que tenemos: </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">Segmento 1 basado en estas características y lógica de cualificación: Segmento 1 = Características A y rasgo B y rasgo C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 perfiles de dispositivo: Dispositivo 1 (dispositivo actual), Dispositivo 2 (gráfico de dispositivo), Dispositivo 3 (gráfico de dispositivo). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Acciones</b> </p> </td> 
   <td colname="col2"> <p>Cada característica disponible está asociada a un dispositivo: </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">Dispositivo 1: Rasgo A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">Dispositivo 2: Rasgo B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">Dispositivo 3: Rasgo C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p>Dados los elementos anteriores, la población total para el segmento 1 es una. </p> <p>In this case, the <span class="wintitle"> Profile Merge Rule</span> uses all the devices and their traits to decide segment qualification. Esto significa que los dispositivos 1, 2 y 3 cumplen los requisitos del segmento 1 pero, como se ha indicado anteriormente, solo se incluye el dispositivo 1 en la población de segmentos en tiempo real. Esto se debe a que: </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">Device 1 is the current device interacting with the Audience Manager <span class="wintitle"> Data Collection Servers</span> (<span class="wintitle"> DCS</span>) in real-time. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">Los dispositivos 2 y 3 están asociados al dispositivo 1 mediante un gráfico de dispositivos pero no interactúan con el DCS al mismo tiempo que el dispositivo 1. </li> 
     </ul> </p> <p>Como resultado, los dispositivos 2 y 3 no se incluyen en la métrica de población de segmentos en tiempo real. </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**¿Puedo ver el número total de dispositivos cualificados para un segmento específico con un[!UICONTROL Profile Merge Rule]gráfico de dispositivos?**

Sí. La métrica total de población de segmentos incluye los dispositivos adicionales que cumplen los requisitos de un segmento en función de las conexiones desde un gráfico de dispositivos.

<table id="table_932E61B1D4374DD58F673C3B35C365EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento de caso de uso </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condiciones</b> </p> </td> 
   <td colname="col2"> <p>Supongamos que tenemos: </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">Segmento 1 basado en estas características y lógica de cualificación: Segmento 1 = Características A y rasgo B y rasgo C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 perfiles de dispositivo: Dispositivo 1 (dispositivo actual), Dispositivo 2 (gráfico de dispositivo), Dispositivo 3 (gráfico de dispositivo). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Asociaciones</b> </p> </td> 
   <td colname="col2"> <p>Cada característica disponible está asociada a un dispositivo: </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">Dispositivo 1: Rasgo A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">Dispositivo 2: Rasgo B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">Dispositivo 3: Rasgo C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p>Dados los elementos anteriores, la población total para el Segmento 1 es de tres (3). </p> <p>In this case, the <span class="wintitle"> Profile Merge Rule</span> uses all the devices and their traits to decide segment qualification. Esto significa que los dispositivos 1, 2 y 3 cumplen los requisitos del segmento 1 y los tres se incluyen en la población total. </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**¿Son los dispositivos que cumplen los requisitos de un segmento con un[!UICONTROL Profile Merge Rule]gráfico de dispositivos incluido en[!UICONTROL Interactive]los informes,[!UICONTROL Overlap]informes e[!UICONTROL Audience Optimization]informes?**

No

>[!MORE_ LIKE_ THIS]
>
>* [Vínculo de perfil](../features/profile-merge-rules/merge-rules-overview.md)

