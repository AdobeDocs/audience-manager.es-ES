---
description: La opción Conversión en todos los canales en los informes de Audience Optimization permite atribuir conversiones sin conexión a impresiones o clics en línea.
seo-description: The Cross Channel Conversion option in the Audience Optimization reports allows you to attribute offline conversions to served online impressions or clicks.
seo-title: Cross Channel Conversion
solution: Audience Manager
title: Conversión en diferentes canales
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: Audience Optimization Reports
exl-id: 7412a43f-81b5-477e-8acf-89d6c8661f1e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 3%

---

# Conversión en diferentes canales{#cross-channel-conversion}

La opción Conversión en todos los canales en los informes de Audience Optimization permite atribuir conversiones sin conexión a impresiones o clics en línea.

El [!UICONTROL Cross Channel Conversion] Los informes de combinan los resultados de la [!DNL Google Campaign Manager] plataforma con [!DNL Audience Manager] rasgos de conversión. Esto permite vincular conversiones sin conexión con impresiones o clics en línea.

Puede usar el complemento [!UICONTROL Cross Channel Conversion] para el [Rendimiento del segmento](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) y [Frecuencia óptima](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) informes.

Para ver la [!UICONTROL Cross Channel Conversion] informes, seleccione la **[!UICONTROL AAM + Ad Server Name]** elemento en el **[!UICONTROL Platform]** lista desplegable.

En la tabla siguiente se enumeran las consideraciones importantes al configurar [!UICONTROL Cross Channel Conversion]:

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
   <td colname="col1"> <p>Se debe asignar al menos un rasgo de conversión a una fuente de datos para que la variable <span class="wintitle"> Conversión en canales múltiples</span> informes para ejecutar. Consulte <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Información básica sobre características</a> para obtener más información sobre las características. </p> </td> 
  </tr>
  <tr> 
   <td> <p>Ventana de atribución </p> </td> 
   <td> <p> <b><span class="uicontrol"> AAM Administrador de campañas de+Google</span></b> la ventana de atribución es de 14 días, lo que significa que solo se tienen en cuenta los rasgos de conversión mostrados en las últimas dos semanas. </p> </td> 
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
