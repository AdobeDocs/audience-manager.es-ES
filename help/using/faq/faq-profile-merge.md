---
description: Respuestas a preguntas comunes sobre la regla de combinación de perfiles y el gráfico de dispositivos.
keywords: Identificador de organización
seo-description: Answers to common Profile Merge Rule and device graph questions.
seo-title: Profile Merge Rules and Device Graph FAQ
solution: Audience Manager
title: Preguntas frecuentes sobre las reglas de combinación de perfiles y el gráfico de dispositivos
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
feature: Profile Merge
exl-id: 03ad79b7-a111-437e-82c5-c7406bd33c39
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1583'
ht-degree: 81%

---

# Preguntas frecuentes sobre las reglas de combinación de perfiles y el gráfico de dispositivos{#profile-merge-rules-and-device-graph-faq}

Respuestas a preguntas comunes sobre la regla de combinación de perfiles y el gráfico de dispositivos.

<!-- profile-merge-faq.xml -->

## Conceptos básicos de Device Graph {#device-graph-basics}

**¿Qué es un gráfico de dispositivos?**

Un gráfico de dispositivo es un conjunto de asignaciones de ID que define grupos de dispositivos anónimos. Asocia estos dispositivos a una persona o unidad familiar basándose en elementos comunes de las señales recopiladas de cada dispositivo. Estas señales ayudan a identificar dispositivos a nivel individual o familiar.

 

**¿Qué es un gráfico de dispositivos externos?**

Un gráfico de dispositivos externos es cualquier gráfico de dispositivo en [!DNL Audience Manager] que no se haya creado exclusivamente a partir de sus fuentes de datos entre dispositivos. Por ejemplo, al crear una [regla de combinación de perfiles](../features/profile-merge-rules/merge-rules-start.md) y elegir las opciones de gráfico de dispositivos de terceros, está trabajando con un gráfico de dispositivos externos. Consulte [Opciones de dispositivos](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

 

**¿Cuáles son algunos casos de uso comunes para un gráfico de dispositivos externos en una [!UICONTROL Profile Merge Rule]?**

El objetivo principal de utilizar un gráfico de dispositivos en una [!UICONTROL Profile Merge Rule] es evaluar y clasificar varios dispositivos pertenecientes a una sola persona o unidad familiar para un segmento específico. DSP El propio segmento puede tener varios usos, por ejemplo, segmentar una audiencia de clientes potenciales con una publicidad ofrecida por un cliente o personalizar la experiencia en el sitio de un cliente mediante una plataforma de personalización en el sitio. Consulte [Ejemplos de uso de los Gráficos de dispositivos externos](../features/profile-merge-rules/external-graph-use-cases.md).

 

**¿Audience Manager es compatible de forma global con los gráficos de dispositivos externos?**

No. Los gráficos de dispositivos externos solo están disponibles en Estados Unidos y Canadá.

 

**¿Con qué frecuencia se actualizan los datos del gráfico de dispositivos externos de [!DNL Audience Manager]?**

Una vez a la semana.

 

## Gráficos de dispositivo y reglas de combinación de perfiles {#device-graph-profile-merge-rules}

**¿Cómo usa [!DNL Audience Manager] un gráfico de dispositivos?**

En [!DNL Audience Manager], los gráficos de dispositivo aparecen como opciones de configuración al [crear una regla de combinación de perfiles](../features/profile-merge-rules/merge-rules-start.md). Mediante [!UICONTROL Profile Merge Rules], estos gráficos de dispositivos ayudan a que [!DNL Audience Manager]:

* Combine varios perfiles de dispositivo. Esto crea un único superconjunto de rasgos.
* Evalúe el superconjunto de rasgos para la clasificación de segmentos (en lugar de evaluar cada perfil de dispositivo individualmente).
* Añada dispositivos cualificados en segmentos disponibles.

 

**¿Cuántas [!UICONTROL Profile Merge Rules] puedo crear?**

Actualmente, puede crear un máximo de 4 [!UICONTROL Profile Merge Rules]. La cuarta regla de combinación de perfiles ([!UICONTROL All Cross-Device Profiles]) solo está disponible para los clientes que tengan el complemento [!UICONTROL People-Based Destinations].

 

**¿Cuántos perfiles de dispositivo combina y lee [!DNL Audience Manager] al usar un gráfico de dispositivo en una [!UICONTROL Profile Merge Rule]?**

Al clasificar un dispositivo para un segmento mediante una [!UICONTROL Profile Merge Rule], Audience Manager combina y lee el perfil actual del dispositivo y un máximo de 99 perfiles adicionales del dispositivo vinculados por la opción de gráfico del dispositivo seleccionada.

 

**¿Qué dispositivos cumplen los requisitos para un segmento cuando se utiliza un gráfico de dispositivos en una [!UICONTROL Profile Merge Rule]?**

Los dispositivos que [!DNL Audience Manager] combina y lee son los mismos que se pueden usar en un segmento.

 

**¿Dónde puede [!DNL Audience Manager] enviar segmentos que puedan usar una [!UICONTROL Profile Merge Rule] que utiliza un gráfico de dispositivos?**

[!DNL Audience Manager] puede enviar segmentos a un destino en archivos por lotes o en tiempo real.

 

## Segmentos, gráficos de dispositivos y reglas de combinación de perfiles {#segments-device-graphs-rules}

**¿Cómo se deshace la segmentación de un dispositivo en [!DNL Audience Manager] cuando ya no se clasifica para un segmento con una [!UICONTROL Profile Merge Rule] que utilice un gráfico de dispositivo?**

Audience Manager combina hasta 100 dispositivos al evaluar segmentos con una [!UICONTROL Profile Merge Rule] que use un gráfico de dispositivos. Si se emite la señal para anular la segmentación, el dispositivo actual y hasta 99 dispositivos adicionales se eliminarán del segmento en el destino. Para obtener más información sobre la anulación de la segmentación, consulte [Reglas de combinación de perfiles y procesos anulación de segmentación de dispositivos](../features/profile-merge-rules/merge-rule-unsegment.md).

 

**Si un destino puede anular la segmentación de dispositivos, ¿se eliminarán los dispositivos de los segmentos mediante una [!UICONTROL Profile Merge Rules] que usen un gráfico de dispositivos?**

Sí. Consulte la explicación anterior.

 

**Si genero un segmento con una [!UICONTROL Profile Merge Rule] que usa un gráfico de dispositivo y el segmento utiliza datos en tiempo real e incorporados, ¿se actualizará mi segmento a medida que cambien los datos incorporados?**

Sí.

 

**¿Las estimaciones del tamaño del segmento incluyen los dispositivos que se clasifican como segmento basado en conexiones proporcionado por una [!UICONTROL Profile Merge Rule] que usa un gráfico de dispositivos?**

No. Consulte las definiciones de [!UICONTROL Estimated Real-Time Population] y [!UICONTROL Estimated Total Population] en [Rasgos y datos de población de segmentos en el Generador de segmentos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=es).

 

**¿[!UICONTROL Addressable Audiences] incluye dispositivos que cumplen los requisitos para un segmento en función de las conexiones proporcionadas por una [!UICONTROL Profile Merge Rule] que utiliza un gráfico de dispositivos?**

Sí.

 

**Si un segmento utiliza una [!UICONTROL Profile Merge Rule] con [!UICONTROL No Cross-Device Profile] y los rasgos que clasifican los dispositivos para el segmento se almacenan solamente en el perfil entre dispositivos, ¿la población total del segmento será 0?**

Sí. Audience Manager no contará los rasgos almacenados en el perfil entre dispositivos en la evaluación de segmentos cuando la regla de combinación de perfiles esté establecida en [!UICONTROL No Cross-Device Profile].

 

## Frecuencia de rasgos, gráficos de dispositivos y reglas de combinación de perfiles {#trait-freq-device-rules}

**¿Cómo calcula [!DNL Audience Manager] la frecuencia de rasgo con una [!UICONTROL Profile Merge Rule] que usa un gráfico de dispositivo?**

La frecuencia de rasgos se define mediante la suma del número de clasificaciones para un rasgo específico en varios dispositivos. Para comprender este proceso mejor, consulte el siguiente caso de uso.

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
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">Tiene una <span class="wintitle">regla de combinación de perfiles</span> que utiliza una opción de gráfico de dispositivos. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">Un solo segmento (segmento 1) compuesto por un único rasgo (rasgo 1), que tiene una frecuencia de 8. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Acciones</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> lee y combina los perfiles del dispositivo para el dispositivo A y el dispositivo B. A partir de esto, vemos lo siguiente: </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">El dispositivo A se ha clasificado para el rasgo 1 tres veces. Tiene una frecuencia de 3 para el rasgo 1. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">El dispositivo B se ha clasificado para el rasgo 1 cinco veces. Tiene una frecuencia de 5 para el rasgo 1. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> suma la frecuencia del rasgo 1 y utiliza la fórmula 8 (3 + 5 = 8) para decidir la clasificación del segmento. El dispositivo A y el dispositivo B cumplen los requisitos para el segmento 1 porque tiene una frecuencia de 8. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## Informes, gráficos de dispositivos y reglas de combinación de perfiles {#reports-device-graphs-rules}

**¿Puedo ver el número de dispositivos a los que se puede acceder mediante una [!UICONTROL Profile Merge Rule] que use un gráfico de dispositivos?**

Sí. Los informes devuelven datos a nivel de [!UICONTROL Profile Merge Rule]. Los datos del informe se actualizan diariamente. Los datos se basan en los dispositivos que se ven en la cuenta, no en los vinculados por un gráfico de dispositivos. Consulte [Métricas de informes para ver las reglas de combinación de perfiles](../features/profile-merge-rules/profile-link-metrics.md).

 

**¿Puedo ver el número de dispositivos clasificados para un segmento específico *en tiempo real* con [!UICONTROL Profile Merge Rules] que usan un gráfico de dispositivos?**

Sí. La métrica de población en tiempo real captura las clasificaciones de los segmentos para el dispositivo actual (el dispositivo visto en tiempo real) mediante los perfiles de todos los dispositivos vinculados por un gráfico de dispositivos.

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
   <td colname="col2"> <p>Supongamos que tenemos este caso: </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">El segmento 1 se basa en estos rasgos y lógica de clasificación: Segmento 1 = Rasgo A y Rasgo B y Rasgo C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 perfiles de dispositivo: Dispositivo 1 (dispositivo actual), Dispositivo 2 (gráfico de dispositivos) y Dispositivo 3 (gráfico de dispositivos). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Acciones</b> </p> </td> 
   <td colname="col2"> <p>Cada rasgo disponible está asociado con un dispositivo: </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">Dispositivo 1: Rasgo A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">Dispositivo 2: Rasgo B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">Dispositivo 3: Rasgo C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p>Dados los elementos anteriores, la población total del segmento 1 es una. </p> <p>En este caso, la <span class="wintitle">regla de combinación de perfiles</span> utiliza todos los dispositivos y sus rasgos para determinar la clasificación del segmento. Esto significa que los dispositivos 1, 2 y 3 cumplen los requisitos para el segmento 1, pero, como se ha indicado anteriormente, solo se incluye el dispositivo 1 en la población de segmentos en tiempo real. Esto se debe a lo siguiente: </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">El dispositivo 1 es el dispositivo actual que interactúa en tiempo real con los <span class="wintitle">servidores de recopilación de datos</span> (<span class="wintitle">DCS</span>) de Audience Manager. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">Los dispositivos 2 y 3 están asociados al Dispositivo 1 mediante un gráfico de dispositivos, pero no interactúan con el DCS al mismo tiempo que el Dispositivo 1. </li> 
     </ul> </p> <p>Como resultado, los dispositivos 2 y 3 no se incluyen en la métrica de población de segmentos en tiempo real. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**¿Puedo ver el número total de dispositivos clasificados para un segmento específico con una [!UICONTROL Profile Merge Rule] que usa un gráfico de dispositivos?**

Sí. La métrica de población total de segmentos incluye los dispositivos adicionales que se han clasificado para un segmento en función de las conexiones desde un gráfico de dispositivos.

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
   <td colname="col2"> <p>Supongamos que tenemos este caso: </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">El segmento 1 se basa en estos rasgos y lógica de clasificación: Segmento 1 = Rasgo A y Rasgo B y Rasgo C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 perfiles de dispositivo: Dispositivo 1 (dispositivo actual), Dispositivo 2 (gráfico de dispositivos) y Dispositivo 3 (gráfico de dispositivos). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Asociaciones</b> </p> </td> 
   <td colname="col2"> <p>Cada rasgo disponible está asociado con un dispositivo: </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">Dispositivo 1: Rasgo A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">Dispositivo 2: Rasgo B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">Dispositivo 3: Rasgo C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p>Dados los elementos anteriores, la población total del segmento 1 es de tres (3). </p> <p>En este caso, la <span class="wintitle">regla de combinación de perfiles</span> utiliza todos los dispositivos y sus rasgos para determinar la clasificación del segmento. Esto significa que los dispositivos 1, 2 y 3 cumplen los requisitos para el segmento 1 y los tres están incluidos en la población total. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**¿Los dispositivos que cumplen los requisitos para un segmento con una [!UICONTROL Profile Merge Rule] que usa un gráfico de dispositivos se incluyen en los informes [!UICONTROL Interactive], [!UICONTROL Overlap] y [!UICONTROL Audience Optimization]?**

No.

**¿Por qué veo una población de segmentos cero para las exportaciones de segmentos a Adobe Campaign después del 16 de marzo de 2020?**

A finales de 2019, publicamos una serie de mejoras en las reglas de combinación de perfiles para mejorar la precisión de los archivos por lotes generados mediante ID entre dispositivos. Estas mejoras se aplicarán estrictamente en la instancia de Audience Manager a partir del lunes, 16 de marzo de 2020. Por lo tanto, los segmentos asignados a un destino mediante ID entre dispositivos dejarán de producir exportaciones en algunas configuraciones de reglas de combinación de perfiles.

Para garantizar la correcta integración entre la instancia de Audience Manager y los destinos que utilizan ID entre dispositivos, como Adobe Campaign, asegúrese de cumplir los siguientes requisitos:

1. Revise la regla de combinación de perfiles utilizada por los segmentos asignados a su destino de ID declarados de Adobe Campaign. La regla de combinación de perfiles debe utilizar la opción [!UICONTROL Last Authenticated Profile], de modo que todos los perfiles autenticados se puedan incluir en las exportaciones. Si la regla de combinación de perfiles usa una opción diferente, cambie a [!UICONTROL Last Authenticated Profile].
2. Seleccione la fuente de datos de ID declarado de Adobe Campaign en la configuración de la regla de combinación de perfiles.

>[!NOTE]
>
> Hemos aumentado el límite de la regla de combinación de perfiles en 1 para los clientes que se enfrentan a esta situación, de modo que pueda crear una regla de combinación de perfiles específica para los segmentos asignados al destino de ID declarados de Adobe Campaign, sin cambiar las reglas de combinación de perfiles para otros casos de uso.

>[!MORELIKETHIS]
>
>* [Vínculo de perfil](../features/profile-merge-rules/profile-link-use-case.md)
