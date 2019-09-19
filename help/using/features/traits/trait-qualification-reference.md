---
description: La cualificación de características, o realización de características, se trata de forma diferente en Audience Manager, según el tipo de característica. Consulte la tabla siguiente para obtener información detallada sobre la calificación de rasgos.
keywords: cualificación de características;realización de características;Realizaciones de características únicas;UTR;Población total de características;TTP
seo-description: La cualificación de características, o realización de características, se trata de forma diferente en Audience Manager, según el tipo de característica. Consulte la tabla siguiente para obtener información detallada sobre la calificación de rasgos.
seo-title: Referencia de calificación de características
solution: Audience Manager
title: Referencia de calificación de características
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# Referencia de calificación de características {#trait-qualification-reference}

La cualificación de características, o realización de características, se trata de forma diferente en Audience Manager, según el tipo de característica. Consulte la tabla siguiente para obtener información detallada sobre la calificación de rasgos.

## Cualificación de características por tipo de característica {#trait-type}

<table id="table_14CD705F376B44EEA9A6C011984356F0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de característica </th> 
   <th colname="col2" class="entry"> Criterios de cualificación </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Características basadas en reglas </p> </td> 
   <td colname="col2"> <p>La calificación de características se realiza en tiempo real, ya que los usuarios cumplen los requisitos para una característica en su explorador. Los usuarios empezarán a cumplir los requisitos para una característica basada en reglas aproximadamente 4 horas después de <a href="../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits"> crear la característica</a> en la interfaz de usuario. </p> <p>Las características basadas en reglas le permiten utilizar controles de frecuencia <a href="../../features/segments/recency-and-frequency.md"></a> y actualización para los límites de frecuencia de publicidad y otros casos de uso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Características integradas </p> </td> 
   <td colname="col2"> <p>La calificación de características se produce después de procesar un archivo entrante, es decir, el archivo entrante se importa a Audience Manager <a href="../../faq/faq-inbound-data-ingestion.md"></a> y es cuando se produce la calificación de características. </p> <p> Para las características integradas, el número máximo de cualificaciones para un perfil de usuario es 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Características algorítmicas </p> </td> 
   <td colname="col2"> <p>Para las características algorítmicas, el número máximo de cualificaciones para un perfil de usuario es 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Características de la carpeta </p> </td> 
   <td colname="col2"> <p>Una característica de carpeta resume las calificaciones de características de las características que contiene. </p> <p>Leer características <a href="../../features/traits/about-folder-traits.md"> de la carpeta: Acerca</a> de para obtener más información. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>Características de audiencias activas y características sincronizadas de fuentes de datos </p> </td> 
   <td colname="col2"> <p>Una característica de Audiencia <span class="wintitle"> activa contiene todos los dispositivos que se administran en la cuenta de</span> Audience Manager <span class="wintitle"></span> . </p> <p><span class="wintitle"> Las características</span> sincronizadas de la fuente de datos rastrean a todos los usuarios asociados a una fuente de datos. </p> <p>Obtenga más información sobre <a href="../../features/traits/client-activity-synced-audience-traits.md"> las características de audiencia activa y las características</a>de la fuente de datos. </p> </td>
  </tr>
 </tbody>
</table>

## Realizaciones únicas de características y población total de características {#unique-trait-realizations}

![](assets/utr-ttp1.png)

El **[!UICONTROL Unique Trait Realizations]** recuento del número de visitantes que agregaron la característica a su perfil, dentro de diferentes intervalos de tiempo.

Representa el **[!UICONTROL Total Trait Population]** número de visitantes que tienen esta característica en su perfil.

Piensen en los números de esta manera. En la imagen anterior, desde la vista Detalles [de](../../features/traits/trait-details-page.md) características, 181 representa el número de dispositivos activos que visitaron sus propiedades ayer. El [!UICONTROL Total Trait Population] de 1.595 representa la cantidad de usuarios cualificados actualmente para esta característica. La [!UICONTROL Total Trait Population] figura muestra la cantidad total de usuarios que podrían utilizarse para segmentación/segmentación. Normalmente, los usuarios permanecerán como parte de una característica durante 120 días.

Porque ejecutamos dos trabajos computacionales diferentes para calcular las dos poblaciones, las [!UICONTROL Total Trait Population] mismas siempre están rezagadas en 24 horas [!UICONTROL Unique Trait Realizations] . En el gráfico de arriba, pueden ver 175 [!UICONTROL Unique Trait Realizations] y un [!UICONTROL Total Trait Population] 6 para el 11 de febrero. Los 175 perfiles se agregan al [!UICONTROL Total Trait Population] día siguiente.

Para llevar el punto a casa, si experimentaste un pico de 10.000 visitantes en este momento, aparecerían en la página de mañana [!UICONTROL Unique Trait Realizations], pero solo aparecerían 24 horas después en la [!UICONTROL Total Trait Population].

## Límite de cualificación de características {#trait-qualification-limit}

Aplicamos un límite de 150.000 cualificaciones de características para cada perfil de usuario, ya sea un perfil autenticado ( [DPUUID](../../reference/ids-in-aam.md)) o un ID de dispositivo ( [UUID](../../reference/ids-in-aam.md)). Tenga en cuenta que aunque los DPUUID son exclusivos de una instancia específica de [!DNL Audience Manager], los UUID se comparten en la [!DNL Audience Manager] plataforma. Para [!UICONTROL UUID]los adultos, imponemos una política de equidad al almacenar las calificaciones de rasgos. Un algoritmo garantiza que una parte igual del [!UICONTROL UUID] perfil esté disponible para cada instancia de [!DNL Audience Manager].
