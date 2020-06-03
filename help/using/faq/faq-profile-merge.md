---
description: Respuestas a preguntas comunes sobre la regla de combinación de Perfiles y el gráfico de dispositivos.
keywords: Organization ID
seo-description: Respuestas a preguntas comunes sobre la regla de combinación de Perfiles y el gráfico de dispositivos.
seo-title: Preguntas más frecuentes sobre las reglas de combinación de Perfiles y Device Graph
solution: Audience Manager
title: Preguntas más frecuentes sobre las reglas de combinación de Perfiles y Device Graph
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
translation-type: tm+mt
source-git-commit: 6876ca5ee0bc5f50c2aa1acd5c683b151a07fd59
workflow-type: tm+mt
source-wordcount: '1548'
ht-degree: 2%

---


# Preguntas más frecuentes sobre las reglas de combinación de Perfiles y Device Graph{#profile-merge-rules-and-device-graph-faq}

Respuestas a preguntas comunes sobre la regla de combinación de Perfiles y el gráfico de dispositivos.

<!-- profile-merge-faq.xml -->

## Conceptos básicos de Device Graph {#device-graph-basics}

**¿Qué es un gráfico de dispositivos?**

Un gráfico de dispositivo es un conjunto de asignaciones de ID que define grupos de dispositivos anónimos. Asocia estos dispositivos a una persona o familia basándose en elementos comunes de las señales recopiladas de cada dispositivo. Estas señales ayudan a identificar dispositivos a nivel individual o doméstico.

 

**¿Qué es un gráfico de dispositivos externos?**

Un gráfico de dispositivo externo es cualquier gráfico de dispositivo en el [!DNL Audience Manager] que no se haya creado exclusivamente a partir de sus propias fuentes de datos entre dispositivos. Por ejemplo, al crear una regla [de combinación de](../features/profile-merge-rules/merge-rules-start.md) Perfiles y elegir las opciones de gráfico de dispositivos [!UICONTROL Co-op Device Graph] o de terceros, se está trabajando con un gráfico de dispositivos externo. Consulte Opciones [de dispositivo](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

 

**¿Cuáles son algunos casos de uso comunes para usar un gráfico de dispositivos externos en un[!UICONTROL Profile Merge Rule]?**

El objetivo principal de utilizar un gráfico de dispositivos en un [!UICONTROL Profile Merge Rule] es evaluar y calificar varios dispositivos pertenecientes a una sola persona o familia para un segmento específico. El propio segmento puede tener varios usos, por ejemplo, dirigir una audiencia de clientes potenciales con una publicidad ofrecida por un DSP o personalizar la experiencia en el sitio de un cliente mediante una plataforma de personalización en el sitio. See [External Device Graph Use Cases](../features/profile-merge-rules/external-graph-use-cases.md).

 

**¿Proporciona el Administrador de Audiencias compatibilidad global con los gráficos de dispositivos externos?**

No. Los gráficos de dispositivos externos solo están disponibles en Estados Unidos y Canadá.

 

**¿Con qué frecuencia se actualizan[!DNL Audience Manager]los datos del gráfico de dispositivos externos?**

Una vez a la semana.

 

## Gráficos de dispositivo y reglas de combinación de Perfil {#device-graph-profile-merge-rules}

**¿Cómo[!DNL Audience Manager]se usa un gráfico de dispositivos?**

En [!DNL Audience Manager], los gráficos de dispositivo aparecen como opciones de configuración al [crear una regla](../features/profile-merge-rules/merge-rules-start.md)de combinación de Perfiles. A través de su [!UICONTROL Profile Merge Rules], estos gráficos de dispositivos ayudan [!DNL Audience Manager]:

* Combine varios perfiles de dispositivo juntos. Esto crea un único superconjunto de características.
* Evalúe el superconjunto de características para la calificación de segmentos (en lugar de evaluar cada perfil de dispositivo individualmente).
* Añada dispositivos cualificados en segmentos disponibles.

 

**¿Cuántos[!UICONTROL Profile Merge Rules]puedo crear?**

Actualmente, puede crear un máximo de 4 [!UICONTROL Profile Merge Rules]. La cuarta regla de combinación de Perfiles ([!UICONTROL All Cross-Device Profiles]) solo está disponible para los clientes que compran el [!UICONTROL People-Based Destinations] complemento.

 

**¿Cuántos perfiles de dispositivo[!DNL Audience Manager]se combinan y leen al usar un gráfico de dispositivo en un[!UICONTROL Profile Merge Rule]?**

Al calificar un dispositivo para un segmento mediante un [!UICONTROL Profile Merge Rule], el Administrador de Audiencias combina y lee el perfil actual del dispositivo y un máximo de 99 perfiles adicionales del dispositivo vinculados por la opción de gráfico del dispositivo seleccionada.

 

**¿Qué dispositivos cumplen los requisitos para un segmento cuando se utiliza un gráfico de dispositivos en un[!UICONTROL Profile Merge Rule]?**

Los dispositivos [!DNL Audience Manager] se combinan y lecturas son los mismos que se califican para un segmento.

 

**¿Dónde puede[!DNL Audience Manager]enviar segmentos que hayan sido calificados por un[!UICONTROL Profile Merge Rule]usuario que utilice un gráfico de dispositivos?**

[!DNL Audience Manager] Puede enviar segmentos a un destino en archivos por lotes o en tiempo real.

 

## Segmentos, gráficos de dispositivos y reglas de combinación de Perfiles {#segments-device-graphs-rules}

**¿Cómo se dessegmenta[!DNL Audience Manager]un dispositivo cuando ya no se califica para un segmento con un[!UICONTROL Profile Merge Rule]que utiliza un gráfico de dispositivo?**

El Administrador de Audiencias combina hasta 100 dispositivos al evaluar segmentos con un [!UICONTROL Profile Merge Rule] gráfico de dispositivos. Si se emite la señal de dessegmentación, el dispositivo actual y hasta 99 dispositivos adicionales se eliminarán del segmento en el destino. Para obtener más información sobre la dessegmentación, consulte Reglas de combinación de [Perfiles y Procesos](../features/profile-merge-rules/merge-rule-unsegment.md)de dessegmentación de dispositivos.

 

**Si un destino puede dessegmentar dispositivos, ¿se eliminarán los dispositivos de los segmentos mediante[!UICONTROL Profile Merge Rules]el uso de un gráfico de dispositivos?**

Sí. Véase la explicación anterior.

 

**Si genero un segmento con un[!UICONTROL Profile Merge Rule]gráfico de dispositivo y el segmento utiliza datos en tiempo real y en el tablero, ¿se actualizará mi segmento a medida que cambien los datos en el tablero?**

Sí.

 

**¿Incluyen las estimaciones de tamaño de segmento dispositivos que cumplen los requisitos para un segmento en función de las conexiones proporcionadas por un[!UICONTROL Profile Merge Rule]usuario que utiliza una opción de gráfico de dispositivo?**

No. Consulte las definiciones de los datos de población de [!UICONTROL Estimated Real-Time Population] características y [!UICONTROL Estimated Total Population] de [características y segmentos en el Generador](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/segments/segment-builder-data.html)de segmentos.

 

**¿[!UICONTROL Addressable Audiences]Incluye dispositivos que cumplen los requisitos para un segmento en función de las conexiones proporcionadas por un[!UICONTROL Profile Merge Rule]usuario que utiliza una opción de gráfico de dispositivos?**

Sí.

 

**Si un segmento utiliza un[!UICONTROL Profile Merge Rule]con[!UICONTROL No Cross-Device Profile]y las características que califican los dispositivos para el segmento se almacenan solamente en el perfil entre dispositivos, ¿la población total del segmento será 0?**

Sí. El Administrador de Audiencias no contará las características almacenadas en el perfil entre dispositivos en la evaluación de segmentos cuando la regla de combinación de Perfiles esté establecida en [!UICONTROL No Cross-Device Profile].

 

## Frecuencia de características, gráficos de dispositivos y reglas de combinación de Perfiles {#trait-freq-device-rules}

**¿Cómo[!DNL Audience Manager]calcula la frecuencia de rasgo con un[!UICONTROL Profile Merge Rule]gráfico de dispositivo?**

La frecuencia de características se define mediante la suma del número de cualificaciones para una característica específica en varios dispositivos. Para ayudarle a comprender esto, consulte el siguiente caso de uso.

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
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">Tiene una regla <span class="wintitle"> de combinación de</span> Perfiles que utiliza una opción de gráfico de dispositivos. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">Un solo segmento (segmento 1) compuesto por una única característica (característica 1), donde la característica 1 tiene una frecuencia de 8. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Acciones</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> El Administrador</span> de Audiencias lee y combina los perfiles del dispositivo para el dispositivo A y el dispositivo B. A partir de esto, vemos lo siguiente: </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">El dispositivo A se ha clasificado para la característica 1 tres veces. Tiene una frecuencia de 3 para la característica 1. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">El dispositivo B se ha clasificado para la característica 1 cinco veces. Tiene una frecuencia de 5 para la característica 1. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> El Administrador</span> de Audiencias resume la frecuencia de la característica 1 y utiliza 8 (3 + 5 = 8) para decidir la calificación del segmento. El dispositivo A y el dispositivo B cumplen los requisitos para el segmento 1 porque tiene una frecuencia de 8. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## Informes, gráficos de dispositivos y reglas de combinación de Perfiles {#reports-device-graphs-rules}

**¿Puedo ver el número de dispositivos a los que se puede acceder mediante un[!UICONTROL Profile Merge Rule]gráfico de dispositivos?**

Sí. Los informes devuelven datos en el [!UICONTROL Profile Merge Rule] nivel. Los datos del informe se actualizan diariamente. Los datos se basan en los dispositivos que se ven en la cuenta, no en los vinculados por un gráfico de dispositivos. Consulte Métricas [de informes para ver las reglas](../features/profile-merge-rules/profile-link-metrics.md)de combinación de Perfiles.

 

**¿Puedo ver el número de dispositivos calificados para un segmento específico en tiempo **real con[!UICONTROL Profile Merge Rules]un gráfico de dispositivos?**

Sí. La métrica de población en tiempo real captura las cualificaciones de los segmentos para el dispositivo actual (el dispositivo visto en tiempo real) mediante los perfiles de todos los dispositivos vinculados por un gráfico de dispositivos.

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
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">El segmento 1 se basa en estas características y lógica de calificación: Segmento 1 = Característica A y Características B y Característica C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 perfiles de dispositivo: Dispositivo 1 (dispositivo actual), Dispositivo 2 (gráfico de dispositivos), Dispositivo 3 (gráfico de dispositivos). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Acciones</b> </p> </td> 
   <td colname="col2"> <p>Cada característica disponible está asociada con un dispositivo: </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">Dispositivo 1: Rasgo A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">Dispositivo 2: Rasgo B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">Dispositivo 3: Característica C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p>Dados los elementos anteriores, la población total del segmento 1 es una. </p> <p>En este caso, la regla <span class="wintitle"> de combinación de</span> Perfiles utiliza todos los dispositivos y sus características para decidir la cualificación del segmento. Esto significa que los dispositivos 1, 2 y 3 cumplen los requisitos para el segmento 1, pero, como se ha indicado anteriormente, solo se incluye el dispositivo 1 en la población de segmentos en tiempo real. Esto se debe a que: </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">El dispositivo 1 es el dispositivo actual que interactúa en tiempo real con los servidores <span class="wintitle"> de recopilación de datos (</span> DCS<span class="wintitle"> ) del Administrador de Audiencias</span>. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">Los dispositivos 2 y 3 están asociados al Dispositivo 1 mediante un gráfico de dispositivos, pero no interactúan con el DCS al mismo tiempo que el Dispositivo 1. </li> 
     </ul> </p> <p>Como resultado, los dispositivos 2 y 3 no se incluyen en la métrica de población de segmentos en tiempo real. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**¿Puedo ver el número total de dispositivos calificados para un segmento específico con un[!UICONTROL Profile Merge Rule]gráfico de dispositivos?**

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
   <td colname="col2"> <p>Supongamos que tenemos: </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">El segmento 1 se basa en estas características y lógica de calificación: Segmento 1 = Característica A y Características B y Característica C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 perfiles de dispositivo: Dispositivo 1 (dispositivo actual), Dispositivo 2 (gráfico de dispositivos), Dispositivo 3 (gráfico de dispositivos). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Asociaciones</b> </p> </td> 
   <td colname="col2"> <p>Cada característica disponible está asociada con un dispositivo: </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">Dispositivo 1: Rasgo A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">Dispositivo 2: Rasgo B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">Dispositivo 3: Característica C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultados</b> </p> </td> 
   <td colname="col2"> <p>Dados los elementos anteriores, la población total del segmento 1 es de tres (3). </p> <p>En este caso, la regla <span class="wintitle"> de combinación de</span> Perfiles utiliza todos los dispositivos y sus características para decidir la cualificación del segmento. Esto significa que los dispositivos 1, 2 y 3 cumplen los requisitos para el segmento 1 y los tres están incluidos en la población total. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**¿Los dispositivos que cumplen los requisitos para un segmento con un[!UICONTROL Profile Merge Rule]que usa un gráfico de dispositivos se incluyen en los[!UICONTROL Interactive]informes,[!UICONTROL Overlap]informes y[!UICONTROL Audience Optimization]informes?**

No.

**¿Por qué veo una población de segmentos cero para las exportaciones de segmentos al Adobe Campaign después del 16 de marzo de 2020?**

A finales de 2019, hemos lanzado una serie de mejoras en las reglas de combinación de Perfiles para mejorar la precisión de los archivos por lotes generados mediante ID entre dispositivos. Estas mejoras se respetarán estrictamente en la instancia del Administrador de Audiencias a partir del lunes 16 de marzo de 2020. Por lo tanto, los segmentos asignados a un destino mediante ID de varios dispositivos dejarán de producir exportaciones en algunas configuraciones de reglas de combinación de Perfil.

Para garantizar la integración correcta entre la instancia del Administrador de Audiencias y los destinos que utilizan ID entre dispositivos, como Adobe Campaign, asegúrese de cumplir los siguientes requisitos:

1. Revise la regla de combinación de Perfiles utilizada por los segmentos asignados a su destino de ID declarados de Adobe Campaign. La regla de combinación de Perfiles debe utilizar la [!UICONTROL Last Authenticated Profile] opción, por lo que todos los perfiles autenticados se pueden incluir en las exportaciones. Si la regla de combinación de Perfiles utiliza una opción diferente, cambie a [!UICONTROL Last Authenticated Profile].
2. Seleccione el origen de datos de ID declarados de Adobe Campaign en la configuración de la regla de combinación de Perfiles.

>[!NOTE]
>
> Hemos aumentado el límite de reglas de combinación de Perfiles en 1 para los clientes que se enfrentan a esta situación, de modo que puede crear una regla de combinación de Perfiles dedicada para los segmentos asignados al destino de ID declarado de Adobe Campaign, sin cambiar las reglas de combinación de Perfiles para otros casos de uso.

>[!MORELIKETHIS]
>
>* [Vínculo de perfil](../features/profile-merge-rules/profile-link-use-case.md)

