---
description: La opción Conversión entre Canales de los informes Optimización de Audiencias permite atribuir conversiones sin conexión a impresiones o clics en línea servidos.
seo-description: La opción Conversión entre Canales de los informes Optimización de Audiencias permite atribuir conversiones sin conexión a impresiones o clics en línea servidos.
seo-title: Conversión en diferentes canales
solution: Audience Manager
title: Conversión en diferentes canales
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 4%

---


# Conversión en diferentes canales{#cross-channel-conversion}

La opción Conversión entre Canales de los informes Optimización de Audiencias permite atribuir conversiones sin conexión a impresiones o clics en línea servidos.

Los [!UICONTROL Cross Channel Conversion] informes combinan los resultados de la plataforma [!DNL DoubleClick Campaign Manager] (DCM) con las características [!DNL Audience Manager] de conversión. Esto le permite vincular conversiones sin conexión a impresiones o clics en línea.

Puede utilizar [!UICONTROL Cross Channel Conversion] para los informes Rendimiento [del](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) segmento y Frecuencia [](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) óptima.

Para vista de los [!UICONTROL Cross Channel Conversion] informes, seleccione el **[!UICONTROL AAM+DCM]** elemento en la lista **[!UICONTROL Platform]** desplegable.

La tabla siguiente lista aspectos importantes a la hora de configurar [!UICONTROL Cross Channel Conversion]:

<table id="table_62590B4AB7624B619EC9AA8FF89722C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Consideración </th> 
   <th class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>Número mínimo de características de conversión </p> </td> 
   <td colname="col1"> <p>Se debe asignar al menos una característica de conversión a un origen de datos para que se ejecuten los informes de conversión <span class="wintitle"></span> de Canales cruzados. Consulte <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Información básica para características</a> para obtener más información sobre características. </p> </td> 
  </tr>
  <tr> 
   <td> <p>Ventana Atribución </p> </td> 
   <td> <p> <b><span class="uicontrol"> La ventana de atribución AAM+DCM</span></b> es de 14 días, lo que significa que solo se tienen en cuenta las características de conversión exhibidas en las dos últimas semanas. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Metodología de último toque </p> </td> 
   <td> <p>El elemento creativo que el usuario vio por última vez antes de la conversión es el que recibe la conversión. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Clics frente a impresiones </p> </td> 
   <td> <p>Un clic tiene prioridad sobre una impresión al decidir la atribución si se produce exactamente al mismo tiempo. Por ejemplo, en una página en la que se muestran varios elementos creativos, la página en la que se hace clic recibe la conversión. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Actualización de datos </p> </td> 
   <td> <p>Los informes siempre se calculan para los datos disponibles el día anterior. </p> </td> 
  </tr> 
 </tbody> 
</table>
