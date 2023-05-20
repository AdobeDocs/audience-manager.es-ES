---
description: El informe Rendimiento del segmento compara los segmentos asignados y no asignados según las impresiones y las tasas de conversión. Un segmento asignado es un segmento que crea y envía a un destino para su segmentación. Un segmento sin asignar es un segmento que ha creado, pero que no ha enviado a un destino para la segmentación. La comparación de estos diferentes tipos de segmentos dentro de los informes y entre ellos le ayuda a optimizar las campañas existentes y a encontrar segmentos que se han pasado por alto y que es posible que desee enviar a un destino para su segmentación.
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and conversion rates. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: Informe de Rendimiento del segmento
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: Audience Optimization Reports
exl-id: 2cd54b18-6916-4d69-bd65-7b8c8846c446
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 1%

---

# Informe de Rendimiento del segmento{#segment-performance-report}

El [!UICONTROL Segment Performance] El informe compara segmentos asignados y no asignados según las impresiones y las tasas de conversión. Un segmento asignado es un segmento que crea y envía a un destino para su segmentación. Un segmento sin asignar es un segmento que ha creado, pero que no ha enviado a un destino para la segmentación. La comparación de estos diferentes tipos de segmentos dentro de los informes y entre ellos le ayuda a optimizar las campañas existentes y a encontrar segmentos que se han pasado por alto y que es posible que desee enviar a un destino para su segmentación.

## Cómo leer los resultados del segmento asignado {#read-mapped-segment-results}

El asignado [!UICONTROL Segment Performance] Este informe muestra todos los segmentos que ha creado y enviado a un destino para la segmentación. La posición de los segmentos asignados en un informe puede indicarle mucho sobre qué segmentos tienen un buen rendimiento y dónde puede necesitar realizar algunos ajustes.

Para leer el informe, ayuda a dividir los resultados en 4 secciones con líneas imaginarias (en rojo) y las categorías que se muestran en el informe de muestra a continuación.

![](assets/mapped-segment-performance.png)

Las etiquetas del ejemplo y la siguiente tabla pueden ayudarle a comprender el rendimiento del segmento y cómo responder a estos resultados.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Posición </th> 
   <th colname="col2" class="entry"> La ubicación indica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Superior izquierda</b> </p> </td> 
   <td colname="col2"> <p>Buenas tasas de conversión. </p> <p>Es posible que pueda obtener más conversiones aumentando las impresiones. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior izquierda</b> </p> </td> 
   <td colname="col2"> <p>Tasas de conversión bajas. </p> <p>Es posible que desee evitar segmentar estos segmentos. Los segmentos de esta sección son buenos candidatos para compararlos con los de los resultados de segmentos no asignados. Algunos de los segmentos sin asignar pueden tener un mejor rendimiento que los segmentos a los que ya está dirigiendo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Superior derecha</b> </p> </td> 
   <td colname="col2"> <p>Fuerte rendimiento. Deje estos segmentos en paz. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior derecha</b> </p> </td> 
   <td colname="col2"> <p>Tasas de conversión bajas e impresiones altas. </p> <p>Los segmentos de esta sección no tienen un buen rendimiento. Es posible que desee desplazar el presupuesto fuera de estos segmentos a segmentos en el cuadrante superior izquierdo del informe. Esto ayudará a reducir las impresiones y puede ayudar a mejorar las tasas de conversión de los segmentos en esta sección inferior derecha. Además, compare estos segmentos asignados con los segmentos no asignados. Algunos de los segmentos sin asignar pueden tener un mejor rendimiento que los segmentos a los que ya está dirigiendo. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cómo leer los resultados de segmentos no asignados {#read-unmapped-segment-results}

Consulta de segmentos no asignados en una [!UICONTROL Segment Performance] El informe de es una buena forma de encontrar nuevos segmentos que no ha tenido en cuenta para la segmentación. De hecho, algunos de estos segmentos pueden superar el rendimiento de los segmentos asignados. Esto se debe a que un segmento no asignado debe cumplir un conjunto de criterios de cualificación para ser incluido en este informe. Para que se incluya en este informe, un segmento no asignado debe:

* Tener conversiones buenas a la media de todos los segmentos asignados.
* Estar entre los 100 segmentos sin asignar principales por tasa de conversión.

Para leer este informe, ayuda a dividir los resultados en 4 secciones con líneas imaginarias (en rojo) y categorías que se muestran en el informe de muestra a continuación.

![](assets/unmapped-segment-performance.png)

En este informe, solo desea centrarse en los segmentos no asignados de la sección superior izquierda. Estos segmentos sin asignar muestran altas tasas de conversión para un bajo nivel de impresiones en comparación con los segmentos de las otras tres secciones.

>[!NOTE]
>
>Los períodos retrospectivos de 7 días y 30 días solo están disponibles para el domingo **[!UICONTROL Date Through]** fechas.
