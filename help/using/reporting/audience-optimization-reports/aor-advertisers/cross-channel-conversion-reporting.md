---
description: La opción Conversión en todos los canales en los informes de Audience Optimization permite atribuir conversiones sin conexión a impresiones o clics en línea.
seo-description: The Cross Channel Conversion option in the Audience Optimization reports allows you to attribute offline conversions to served online impressions or clicks.
seo-title: Cross Channel Conversion
solution: Audience Manager
title: Conversión en canales múltiples
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: Audience Optimization Reports
exl-id: 7412a43f-81b5-477e-8acf-89d6c8661f1e
TQID: https://experienceleague.adobe.com/oP3jo2IVz2w0ExYE00wHo19nelOfOf4iAN84pgF64fU
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 238
ht-degree: 0%

---

# Conversión en canales múltiples{#cross-channel-conversion}

La opción Conversión en todos los canales en los informes de Audience Optimization permite atribuir conversiones sin conexión a impresiones o clics en línea.

Los informes de [!UICONTROL Cross Channel Conversion] combinan los resultados de la plataforma [!DNL Google Campaign Manager] con [!DNL Audience Manager] rasgos de conversión. Esto permite vincular conversiones sin conexión con impresiones o clics en línea.

Puede usar [!UICONTROL Cross Channel Conversion] para los informes [Rendimiento del segmento](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) y [Frecuencia óptima](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md).

Para ver los informes de [!UICONTROL Cross Channel Conversion], seleccione el elemento **[!UICONTROL AAM + Ad Server Name]** en la lista desplegable **[!UICONTROL Platform]**.

En la tabla siguiente se enumeran consideraciones importantes al configurar [!UICONTROL Cross Channel Conversion]:

<table id="table_62590B4AB7624B619EC9AA8FF89722C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Consideración </th> 
   <th class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>Número mínimo de rasgos de conversión </p> </td> 
   <td colname="col1"> <p>Se debe asignar al menos un rasgo de conversión a un origen de datos para que se ejecuten los informes <span class="wintitle"> de conversión entre canales</span>. Consulte <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> información básica sobre características</a> para obtener más información sobre características. </p> </td> 
  </tr>
  <tr> 
   <td> <p>Ventana de atribución </p> </td> 
   <td> <p> <b><span class="uicontrol"> La ventana de atribución de AAM+Google Campaign Manager</span></b> tiene 14 días, lo que significa que solo se tienen en cuenta los rasgos de conversión mostrados en las últimas dos semanas. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Metodología de último contacto </p> </td> 
   <td> <p>El creativo que el usuario ha visto por última vez antes de la conversión es el que recibe la conversión. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Clics frente a impresiones </p> </td> 
   <td> <p>Un clic tiene prioridad sobre una impresión al decidir la atribución si se producen al mismo tiempo. Por ejemplo, en una página en la que se muestran varios creativos, al que se hace clic se le asigna la conversión. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Actualización de datos </p> </td> 
   <td> <p>Los informes siempre se calculan para los datos disponibles el día anterior. </p> </td> 
  </tr> 
 </tbody> 
</table>
