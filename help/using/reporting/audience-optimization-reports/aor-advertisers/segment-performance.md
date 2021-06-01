---
description: El informe Rendimiento del segmento compara segmentos asignados y no asignados por impresiones y tasas de conversión. Un segmento asignado es un segmento que crea y envía a un destino para su segmentación. Un segmento sin asignar es un segmento que ha creado pero que no ha enviado a un destino para su segmentación. La comparación de estos distintos tipos de segmentos dentro de y entre informes le ayuda a optimizar las campañas existentes y a encontrar segmentos que no tiene en cuenta y que puede que desee enviar a un destino para este fin.
seo-description: El informe Rendimiento del segmento compara segmentos asignados y no asignados por impresiones y tasas de conversión. Un segmento asignado es un segmento que crea y envía a un destino para su segmentación. Un segmento sin asignar es un segmento que ha creado pero que no ha enviado a un destino para su segmentación. La comparación de estos distintos tipos de segmentos dentro de y entre informes le ayuda a optimizar las campañas existentes y a encontrar segmentos que no tiene en cuenta y que puede que desee enviar a un destino para este fin.
seo-title: Informe de Rendimiento del segmento
solution: Audience Manager
title: Informe de Rendimiento del segmento
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: Informes de optimización de Audiencia
exl-id: 2cd54b18-6916-4d69-bd65-7b8c8846c446
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 1%

---

# Informe de Rendimiento del segmento{#segment-performance-report}

El informe [!UICONTROL Segment Performance] compara segmentos asignados y no asignados por impresiones y tasas de conversión. Un segmento asignado es un segmento que crea y envía a un destino para su segmentación. Un segmento sin asignar es un segmento que ha creado pero que no ha enviado a un destino para su segmentación. La comparación de estos distintos tipos de segmentos dentro de y entre informes le ayuda a optimizar las campañas existentes y a encontrar segmentos que no tiene en cuenta y que puede que desee enviar a un destino para este fin.

## Cómo leer los resultados del segmento asignado {#read-mapped-segment-results}

El informe [!UICONTROL Segment Performance] asignado muestra todos los segmentos que ha creado y enviado a un destino para su segmentación. La posición de los segmentos asignados en un informe puede indicarle mucho sobre qué segmentos tienen un buen rendimiento y dónde podría necesitar realizar algunos ajustes.

Para leer el informe, ayuda a dividir los resultados en 4 secciones con líneas imaginarias (en rojo) y las categorías que se muestran en el informe de muestra a continuación.

![](assets/mapped-segment-performance.png)

Las etiquetas del ejemplo y de la tabla siguiente pueden ayudarle a comprender el rendimiento del segmento y cómo responder a estos resultados.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Posición </th> 
   <th colname="col2" class="entry"> La colocación indica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Superior izquierda</b> </p> </td> 
   <td colname="col2"> <p>Buenas tasas de conversión. </p> <p>Es posible que obtenga más conversiones al aumentar las impresiones. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior izquierda</b> </p> </td> 
   <td colname="col2"> <p>Tasas de conversión bajas. </p> <p>Puede que desee evitar la segmentación de estos segmentos. Los segmentos de esta sección presentan buenos candidatos para compararlos con los que aparecen en los resultados de segmentos sin asignar. Algunos de los segmentos sin asignar pueden funcionar mejor que los segmentos a los que ya está dirigiendo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Superior derecha</b> </p> </td> 
   <td colname="col2"> <p>Fuerte rendimiento. Deje estos segmentos en paz. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior derecha</b> </p> </td> 
   <td colname="col2"> <p>Tasas de conversión bajas e impresiones altas. </p> <p>Los segmentos de esta sección no tienen un buen rendimiento. Es posible que desee desplazar el presupuesto de estos segmentos a segmentos en el cuadrante superior izquierdo del informe. Esto ayudará a reducir las impresiones y puede ayudar a mejorar las tasas de conversión de los segmentos en esta sección inferior derecha. Además, compare estos segmentos asignados con sus segmentos sin asignar. Algunos de los segmentos sin asignar pueden funcionar mejor que los segmentos a los que ya está dirigiendo. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cómo leer los resultados del segmento sin asignar {#read-unmapped-segment-results}

Mirar los segmentos sin asignar en un informe [!UICONTROL Segment Performance] es una buena manera de encontrar nuevos segmentos que no ha considerado para la segmentación. De hecho, algunos de estos segmentos pueden superar el rendimiento de sus segmentos asignados. Esto se debe a que un segmento sin asignar debe cumplir un conjunto de criterios de calificación que se incluirán en este informe. Para que se incluya en este informe, un segmento sin asignar debe:

* Tener conversiones buenas que el promedio de todos los segmentos asignados.
* Esté entre los 100 segmentos sin asignar principales por tasa de conversión.

Para leer este informe, ayuda a dividir los resultados en 4 secciones con líneas imaginarias (en rojo) y categorías que se muestran en el informe de muestra a continuación.

![](assets/unmapped-segment-performance.png)

En este informe, solo desea centrarse en esos segmentos sin asignar en la sección superior izquierda. Estos segmentos sin asignar muestran tasas de conversión elevadas para un bajo nivel de impresiones en comparación con los segmentos de las otras tres secciones.

>[!NOTE]
>
>Los periodos retrospectivos de 7 días y 30 días solo están disponibles para las fechas de domingo **[!UICONTROL Date Through]**.
