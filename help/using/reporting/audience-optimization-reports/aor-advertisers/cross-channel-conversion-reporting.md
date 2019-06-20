---
description: La opción Conversión en varios canales de los informes de Optimización de audiencias permite atribuir conversiones sin conexión a impresiones o clics en línea.
seo-description: La opción Conversión en varios canales de los informes de Optimización de audiencias permite atribuir conversiones sin conexión a impresiones o clics en línea.
seo-title: Conversión en diferentes canales
solution: Audience Manager
title: Conversión en diferentes canales
uuid: 0 fecec 23-e 502-490 b-b 7 dd -47 a 3753 a 3 f 75
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Conversión en diferentes canales{#cross-channel-conversion}

La opción Conversión en varios canales de los informes de Optimización de audiencias permite atribuir conversiones sin conexión a impresiones o clics en línea.

[!UICONTROL Cross Channel Conversion] Los informes combinan resultados de la plataforma [!DNL DoubleClick Campaign Manager] (DCM) con características [!DNL Audience Manager] de conversión. Esto le permite vincular conversiones sin conexión a impresiones o clics en línea.

You can use the [!UICONTROL Cross Channel Conversion] for the [Segment Performance](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) and [Optimal Frequency](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) reports.

To view the [!UICONTROL Cross Channel Conversion] reports, select the **[!UICONTROL AAM+DCM]** item in the **[!UICONTROL Platform]** drop-down list.

The following table lists important considerations when setting up [!UICONTROL Cross Channel Conversion]:

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
   <td colname="col1"> <p>At least one conversion trait must be assigned to a data source in order for the <span class="wintitle"> Cross Channel Conversion</span> reports to run. See <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Basic Information for Traits</a> for more information on traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>Número máximo de características de conversión </p> </td> 
   <td colname="col1"> <p>The reports pull in a <i>maximum</i> of 50 conversion traits from the user. Si llega al máximo, los informes utilizan las primeras 50 características de conversión basadas en ID de características, en orden ascendente. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Ventana Atribución </p> </td> 
   <td> <p> <b><span class="uicontrol"> La ventana</span></b> de atribución de AAM + DCM es de 14 días, lo que significa que solo se consideran las características de conversión mostradas en las últimas dos semanas. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Metodología de último toque </p> </td> 
   <td> <p>El elemento creativo que el usuario ha visto antes antes de la conversión es el que ha concedido la conversión. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Clics frente a impresiones </p> </td> 
   <td> <p>Un clic tiene prioridad sobre la impresión cuando se decide la atribución si se producen al mismo tiempo. Por ejemplo, en una página en la que se muestran varios elementos creativos, se otorga la conversión a la que se hace clic. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Creación de datos </p> </td> 
   <td> <p>Los informes siempre se calculan para los datos disponibles del día anterior. </p> </td> 
  </tr> 
 </tbody> 
</table>
