---
description: La opción Conversión en todos los canales de los informes de Audience Optimization permite atribuir conversiones sin conexión a impresiones o clics en línea.
seo-description: La opción Conversión en todos los canales de los informes de Audience Optimization permite atribuir conversiones sin conexión a impresiones o clics en línea.
seo-title: Conversión en diferentes canales
solution: Audience Manager
title: Conversión en diferentes canales
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: Audience Optimization Reports
exl-id: 7412a43f-81b5-477e-8acf-89d6c8661f1e
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 5%

---

# Conversión en diferentes canales{#cross-channel-conversion}

La opción Conversión en todos los canales de los informes de Audience Optimization permite atribuir conversiones sin conexión a impresiones o clics en línea.

Los informes [!UICONTROL Cross Channel Conversion] combinan los resultados de la plataforma [!DNL Google Campaign Manager] con características de conversión [!DNL Audience Manager]. Esto le permite vincular conversiones sin conexión a impresiones o clics en línea.

Puede utilizar [!UICONTROL Cross Channel Conversion] para los informes [Rendimiento del segmento](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) y [Frecuencia óptima](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md).

Para ver los informes [!UICONTROL Cross Channel Conversion] , seleccione el elemento **[!UICONTROL AAM + Ad Server Name]** en la lista desplegable **[!UICONTROL Platform]**.

La tabla siguiente enumera consideraciones importantes al configurar [!UICONTROL Cross Channel Conversion]:

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
   <td colname="col1"> <p>Se debe asignar al menos un rasgo de conversión a un origen de datos para que se ejecuten los informes <span class="wintitle"> Conversión en todos los canales</span>. Consulte <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Información básica para características</a> para obtener más información sobre características. </p> </td> 
  </tr>
  <tr> 
   <td> <p>Ventana Atribución </p> </td> 
   <td> <p> <b><span class="uicontrol"> La ventana de atribución AAM+Google Campaign </span></b> Manager es de 14 días, lo que significa que solo se tienen en cuenta los rasgos de conversión exhibidos en las últimas dos semanas. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Metodología de último contacto </p> </td> 
   <td> <p>El creativo que el usuario ha visto por última vez antes de la conversión es el que recibe la conversión. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Clics frente a impresiones </p> </td> 
   <td> <p>Un clic tiene prioridad sobre una impresión al decidir la atribución si se produce exactamente al mismo tiempo. Por ejemplo, en una página en la que se muestran varios elementos creativos, se asigna la conversión a la página en la que se hace clic. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Actualización de datos </p> </td> 
   <td> <p>Los informes siempre se calculan para los datos disponibles el día anterior. </p> </td> 
  </tr> 
 </tbody> 
</table>
