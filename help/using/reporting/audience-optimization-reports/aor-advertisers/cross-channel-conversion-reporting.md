---
description: La opción Conversión en diferentes canales de los informes Audience Optimization permite atribuir sin conexión conversiones a impresiones en línea o clics servidos.
seo-description: The Cross Channel Conversion option in the Audience Optimization reports allows you to attribute offline conversions to served online impressions or clicks.
seo-title: Cross Channel Conversion
solution: Audience Manager
title: Conversión en todos los canales
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: Audience Optimization Reports
exl-id: 7412a43f-81b5-477e-8acf-89d6c8661f1e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---

# Conversión en todos los canales{#cross-channel-conversion}

La opción Conversión en diferentes canales de los informes Audience Optimization permite atribuir sin conexión conversiones a impresiones en línea o clics servidos.

Los [!UICONTROL Cross Channel Conversion] informes combinan los resultados de la [!DNL Google Campaign Manager] plataforma con [!DNL Audience Manager] Conversión características. Esto le permite vincular sin conexión conversiones a en línea impresiones o clics.

Puede utilizar para [!UICONTROL Cross Channel Conversion] los informes de rendimiento[&#x200B; de &#x200B;](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md)segmento y [frecuencia](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) óptima.

Para vista los [!UICONTROL Cross Channel Conversion] informes, seleccione el **[!UICONTROL AAM + Ad Server Name]** elemento en la **[!UICONTROL Platform]** lista desplegable.

La siguiente tabla enumera los aspectos importantes a la hora de configurar [!UICONTROL Cross Channel Conversion]:

<table id="table_62590B4AB7624B619EC9AA8FF89722C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Consideración </th> 
   <th class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>Número mínimo de rasgos Conversión </p> </td> 
   <td colname="col1"> <p>Se debe asignar al menos una característica Conversión a una fuente de datos para que se ejecuten los informes de <span class="wintitle"> conversión</span> entre canales. Consulte <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Información básica para rasgos</a> para obtener más información sobre los rasgos. </p> </td> 
  </tr>
  <tr> 
   <td> <p>Ventana de atribución </p> </td> 
   <td> <p> <b><span class="uicontrol"> La ventana de atribución de AAM+Google Campaign Manager</span></b> es de 14 días, lo que significa que solo se consideran Conversión rasgos exhibidos en las últimas dos semanas. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Metodología de último toque </p> </td> 
   <td> <p>El creativa que el usuario ha visto por última vez antes de convertir es el que recibe el Conversión. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Clics frente a impresiones </p> </td> 
   <td> <p>Un clic tiene prioridad sobre un impresión a la hora de decidir atribución si se producen al mismo tiempo. Por ejemplo, en un Página en el que se muestran varios elementos creativos, el elemento en el que se hace clic recibe el Conversión. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Creación de los datos </p> </td> 
   <td> <p>Los informes siempre se calculan a partir de los datos disponibles el día anterior. </p> </td> 
  </tr> 
 </tbody> 
</table>
