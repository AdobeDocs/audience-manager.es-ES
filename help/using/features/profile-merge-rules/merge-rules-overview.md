---
description: Con Reglas de combinación de perfiles obtiene control sobre los conjuntos de datos utilizados para la segmentación y puede dirigirse a una persona de forma precisa en varios dispositivos.
seo-description: Con Reglas de combinación de perfiles obtiene control sobre los conjuntos de datos utilizados para la segmentación y puede dirigirse a una persona de forma precisa en varios dispositivos.
seo-title: Información general sobre reglas de combinación de perfiles
solution: Audience Manager
title: Información general sobre reglas de combinación de perfiles
uuid: 9 e 7988 cc -9145-432 b -840 a -54 fbd 8657 b 3 b
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Profile Merge Rules Overview {#profile-merge-rules-overview}

With [!UICONTROL Profile Merge Rules] you get control over the data sets used for segmentation and can target a person accurately across multiple devices.

## Data collection and targeting with anonymous and authenticated profiles {#data-collection-targeting}

Normalmente, la segmentación de audiencia y la segmentación dependen de los datos recopilados de todos los usuarios en un dispositivo. La recopilación de datos y los objetivos basados en datos de nivel de dispositivo presentan algunas desventajas. Por ejemplo, no puede distinguir entre varios usuarios que comparten un dispositivo o que se dirijan con precisión a los usuarios en varios dispositivos. La recopilación de datos centrada en el dispositivo ya no es suficiente para campañas de marketing digital o para segmentación entre dispositivos.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] cambia fundamentalmente cómo [!DNL Audience Manager] recopila datos y segmentos para segmentación. Permite trabajar con 2 tipos distintos de perfiles, un perfil de dispositivo y un perfil autenticado.

<table id="table_CE98C0E32A964B27804736A896233869"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de perfil </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Device perfil </td> 
   <td colname="col2"> <p>Un perfil de dispositivo está vinculado a un ID para un dispositivo determinado, como un ID de cookie o ID de dispositivo móvil. Incluye: </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">Características basadas en reglas cuando un usuario no está autenticado. </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">Características integradas vinculadas a un ID de dispositivo, como datos de terceros basados en cookies. </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> Perfil autenticado </td> 
   <td colname="col2"> <p>El perfil autenticado está ligado a un ID de usuario pasado cuando una persona inicia sesión en el sitio. Incluye </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">Características basadas en reglas recopiladas entre dispositivos cuando se autentica a un usuario. </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">Características integradas en un archivo sin conexión vinculado al mismo ID de usuario. </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

Estos distintos perfiles controlan los datos que se pueden utilizar para la segmentación. Por ejemplo, con un perfil autenticado, puede crear segmentos precisos basados en datos de varios dispositivos para una sola persona. Esto significa que puede ofrecer una experiencia de marca uniforme a los clientes en varios dispositivos. Additionally, cross-device authentication allows [!DNL Audience Manager] to map the different platforms a person uses for their online activities. This is called the [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Ventajas {#advantages}

With [!UICONTROL Profile Merge Rules] you can:

* Diríjase a usuarios en función de perfiles autenticados, perfiles anónimos o combinaciones de ambos.
* Diríjase a un cliente específico en sus dispositivos.
* Cree un gráfico de dispositivos basado en datos determinísticos.
* Ajuste los datos de los segmentos según los distintos perfiles.
* Obtenga perspectivas adicionales en la audiencia.

## Primeros pasos {#getting-started}

See the following sections and the [FAQ](../../faq/faq-profile-merge.md) for more information about [!UICONTROL Profile Merge Rules].

* [Introducción a las reglas de combinación de perfiles](/help/using/features/profile-merge-rules/merge-rules-start.md)
* [Panel de reglas de combinación de perfiles](/help/using/features/profile-merge-rules/merge-rules-dashboard.md)
* [Opciones de regla de combinación de perfiles definidas](/help/using/features/profile-merge-rules/merge-rule-definitions.md)
* [Casos de uso generales para reglas de combinación de perfiles](/help/using/features/profile-merge-rules/merge-rule-targeting-options.md)
* [Casos de uso del gráfico de dispositivos de vínculo de perfil](/help/using/features/profile-merge-rules/profile-link-use-case.md)
* [Ejemplos de uso de los Gráficos de dispositivos externos](/help/using/features/profile-merge-rules/external-graph-use-cases.md)
* [Métricas de informe para reglas de combinación de perfiles](/help/using/features/profile-merge-rules/profile-link-metrics.md)
* [Procesos de combinación de perfiles y de segmentación de dispositivos](/help/using/features/profile-merge-rules/merge-rule-unsegment.md)
* [Eliminación instantánea entre dispositivos](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md)
* [Consideraciones importantes para las reglas de combinación de perfiles con los gráficos de dispositivos](/help/using/features/profile-merge-rules/considerations-pmr-device-graph.md)
