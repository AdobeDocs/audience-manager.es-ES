---
description: La opción Conversión entre Canales de los informes de Audience Optimization permite atribuir conversiones sin conexión a impresiones o clics en línea servidos.
seo-description: La opción Conversión entre Canales de los informes de Audience Optimization permite atribuir conversiones sin conexión a impresiones o clics en línea servidos.
seo-title: Conversión en diferentes canales
solution: Audience Manager
title: Conversión en diferentes canales
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 97129b435ab8e13def14bc85dcaab8254b2c4bda
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 4%

---


# Conversión en diferentes canales{#cross-channel-conversion}

La opción Conversión entre Canales de los informes de Audience Optimization permite atribuir conversiones sin conexión a impresiones o clics en línea servidos.

Los informes [!UICONTROL Cross Channel Conversion] combinan resultados de la plataforma [!DNL Google Campaign Manager] con características de conversión [!DNL Audience Manager]. Esto le permite vincular conversiones sin conexión a impresiones o clics en línea.

Puede utilizar [!UICONTROL Cross Channel Conversion] para los informes [Rendimiento del segmento](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) y [Frecuencia óptima](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md).

Para vista de los informes [!UICONTROL Cross Channel Conversion], seleccione el elemento **[!UICONTROL AAM + Ad Server Name]** en la lista desplegable **[!UICONTROL Platform]**.

La siguiente tabla lista consideraciones importantes al configurar [!UICONTROL Cross Channel Conversion]:

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
   <td colname="col1"> <p>Se debe asignar al menos una característica de conversión a un origen de datos para que se ejecuten los informes de conversión de <span class="wintitle"> Canales cruzados</span>. Consulte <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Información básica para características</a> para obtener más información sobre características. </p> </td> 
  </tr>
  <tr> 
   <td> <p>Ventana Atribución </p> </td> 
   <td> <p> <b><span class="uicontrol"> La ventana de atribución de </span></b> Administración de Campañas AAM+Google es de 14 días, lo que significa que solo se tienen en cuenta las características de conversión exhibidas en las dos últimas semanas. </p> </td> 
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
