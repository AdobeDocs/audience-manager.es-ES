---
description: Con las reglas de combinación de perfiles obtiene el control sobre los conjuntos de datos utilizados para la segmentación y puede dirigirse a una persona de forma precisa en varios dispositivos.
seo-description: Con las reglas de combinación de perfiles obtiene el control sobre los conjuntos de datos utilizados para la segmentación y puede dirigirse a una persona de forma precisa en varios dispositivos.
seo-title: Información general sobre las reglas de combinación de perfiles
solution: Audience Manager
title: Información general sobre las reglas de combinación de perfiles
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Información general sobre las reglas de combinación de perfiles {#profile-merge-rules-overview}

Con [!UICONTROL Profile Merge Rules] usted obtiene el control de los conjuntos de datos utilizados para la segmentación y puede dirigirse a una persona con precisión en varios dispositivos.

## Recopilación y segmentación de datos con perfiles anónimos y autenticados {#data-collection-targeting}

Normalmente, la segmentación y el targeting de audiencia dependen de los datos recopilados de todos los usuarios en un dispositivo. La recopilación de datos y la determinación de objetivos en función de los datos a nivel de dispositivo tienen algunas desventajas. Por ejemplo, no puede distinguir entre varios usuarios que comparten un dispositivo o que se dirigen a usuarios con precisión en varios dispositivos. La recopilación de datos centrada en el dispositivo ya no es suficiente para campañas de marketing digital o objetivos entre dispositivos.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] cambia fundamentalmente la forma en que [!DNL Audience Manager] recopila datos y segmenta a los usuarios para la segmentación. Le permite trabajar con dos tipos distintos de perfiles, un perfil de dispositivo y un perfil autenticado.

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
   <td colname="col2"> <p>Un perfil de dispositivo está vinculado a un ID de un dispositivo determinado, como un ID de cookie o un ID de dispositivo móvil. Incluye: </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">Características basadas en reglas realizadas cuando un usuario no está autenticado. </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">Características integradas vinculadas a un ID de dispositivo, como datos de terceros basados en cookies. </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> Perfil autenticado </td> 
   <td colname="col2"> <p>El perfil autenticado está vinculado a un ID de usuario que se pasa cuando una persona inicia sesión en el sitio. Incluye </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">Características basadas en reglas recopiladas en distintos dispositivos cuando se autentica a un usuario. </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">Características integradas en un archivo sin conexión vinculado al mismo ID de usuario. </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

Estos diferentes perfiles controlan los datos que puede utilizar para la segmentación. Por ejemplo, con un perfil autenticado, puede generar segmentos precisos basados en datos de varios dispositivos para una sola persona. Esto significa que puede ofrecer una experiencia de marca uniforme a los clientes en varios dispositivos. Además, la autenticación entre dispositivos permite [!DNL Audience Manager] asignar las diferentes plataformas que una persona utiliza para sus actividades en línea. Esto se llama el [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Ventajas {#advantages}

Con [!UICONTROL Profile Merge Rules] usted puede:

* Establezca como objetivo a los usuarios en función de perfiles autenticados, perfiles anónimos o combinaciones de ambos.
* Diríjase a un cliente específico en sus dispositivos.
* Cree un gráfico de dispositivos basado en datos determinísticos.
* Ajuste los datos de los segmentos en función de diferentes perfiles.
* Obtenga una perspectiva adicional sobre su audiencia.

## Primeros pasos {#getting-started}

Consulte las secciones siguientes y las [preguntas más frecuentes](../../faq/faq-profile-merge.md) para obtener más información sobre [!UICONTROL Profile Merge Rules].

* [Introducción a las reglas de combinación de perfiles](/help/using/features/profile-merge-rules/merge-rules-start.md)
* [Tablero de reglas de combinación de perfiles](/help/using/features/profile-merge-rules/merge-rules-dashboard.md)
* [Opciones de regla de combinación de perfiles definidas](/help/using/features/profile-merge-rules/merge-rule-definitions.md)
* [Casos generales de uso de reglas de combinación de perfiles](/help/using/features/profile-merge-rules/merge-rule-targeting-options.md)
* [Casos de uso de Device Graph de vínculo de perfil](/help/using/features/profile-merge-rules/profile-link-use-case.md)
* [Ejemplos de uso de los Gráficos de dispositivos externos](/help/using/features/profile-merge-rules/external-graph-use-cases.md)
* [Métricas de informes para reglas de combinación de perfiles](/help/using/features/profile-merge-rules/profile-link-metrics.md)
* [Reglas de combinación de perfiles y procesos de dessegmentación de dispositivos](/help/using/features/profile-merge-rules/merge-rule-unsegment.md)
* [Eliminación instantánea entre dispositivos](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md)
* [Consideraciones importantes para las reglas de combinación de perfiles con gráficos de dispositivos](/help/using/features/profile-merge-rules/considerations-pmr-device-graph.md)
