---
description: El informe Rendimiento del segmento compara segmentos asignados y sin asignar por impresiones y tasas de conversión. Un segmento asignado es un segmento que crea y envía a un destino para la segmentación. Un segmento sin asignar es un segmento que ha creado pero que no se ha enviado a un destino para la segmentación. La comparación de estos diferentes tipos de segmentos dentro y entre informes ayuda a optimizar las campañas existentes y encuentra los segmentos ignorados que quizá desee enviar a un destino para la segmentación.
seo-description: El informe Rendimiento del segmento compara segmentos asignados y sin asignar por impresiones y tasas de conversión. Un segmento asignado es un segmento que crea y envía a un destino para la segmentación. Un segmento sin asignar es un segmento que ha creado pero que no se ha enviado a un destino para la segmentación. La comparación de estos diferentes tipos de segmentos dentro y entre informes ayuda a optimizar las campañas existentes y encuentra los segmentos ignorados que quizá desee enviar a un destino para la segmentación.
seo-title: Informe Rendimiento del segmento
solution: Audience Manager
title: Informe Rendimiento del segmento
uuid: 5156 a 4 c 7-831 d -4 a 95-a 1 be-eb 516 f 0 d 91 b 7
translation-type: tm+mt
source-git-commit: ad4721cd2ff1f4b2b7cb814cbafdef1f59138a26

---


# Segment Performance Report{#segment-performance-report}

The [!UICONTROL Segment Performance] report compares mapped and unmapped segments by impressions and conversion rates. Un segmento asignado es un segmento que crea y envía a un destino para la segmentación. Un segmento sin asignar es un segmento que ha creado pero que no se ha enviado a un destino para la segmentación. La comparación de estos diferentes tipos de segmentos dentro y entre informes ayuda a optimizar las campañas existentes y encuentra los segmentos ignorados que quizá desee enviar a un destino para la segmentación.

## How to Read Your Mapped Segment Results {#read-mapped-segment-results}

The mapped [!UICONTROL Segment Performance] report displays all the segments you created and sent to a destination for targeting.The position of your mapped segments in a report can tell you a lot about which segments are performing well and where you might need to make some adjustments.

Para leer el informe, ayuda a dividir los resultados en 4 secciones con líneas imaginarias (en rojo) y las categorías que se muestran en el informe de muestra siguiente.

![](assets/mapped-segment-performance.png)

Las etiquetas del ejemplo y de la tabla siguiente pueden ayudarle a comprender el rendimiento de los segmentos y cómo responder a estos resultados.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Posición </th> 
   <th colname="col2" class="entry"> Ubicación indica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Superior izquierda</b> </p> </td> 
   <td colname="col2"> <p>Buenas tasas de conversión. </p> <p>Es posible que pueda obtener más conversiones al aumentar las impresiones. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior izquierda</b> </p> </td> 
   <td colname="col2"> <p>Tasas de conversión bajas. </p> <p>Es posible que desee evitar la segmentación de estos segmentos. Los segmentos de esta sección hacen grandes candidatos para compararlos con los de los resultados del segmento sin asignar. Algunos de los segmentos sin asignar pueden funcionar mejor que los segmentos que ya está segmentando. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Superior derecha</b> </p> </td> 
   <td colname="col2"> <p>Sólido rendimiento. Deje estos segmentos por separado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Inferior derecha</b> </p> </td> 
   <td colname="col2"> <p>Tasas de conversión bajas y altas impresiones. </p> <p>Los segmentos de esta sección no funcionan bien. Es posible que desee desplazar el presupuesto de estos segmentos y en segmentos en el cuadrante superior izquierdo del informe. Esto ayudará a reducir las impresiones y puede ayudar a mejorar las tasas de conversión de los segmentos en esta sección inferior derecha. Compare también estos segmentos asignados con los segmentos sin asignar. Algunos de los segmentos sin asignar pueden funcionar mejor que los segmentos que ya está segmentando. </p> </td> 
  </tr> 
 </tbody> 
</table>

## How to Read Your Unmapped Segment Results {#read-unmapped-segment-results}

Looking at unmapped segments in a [!UICONTROL Segment Performance] report is a great way to find new segments you haven't considered for targeting. De hecho, algunos de estos segmentos pueden superar los segmentos asignados. Esto se debe a que un segmento sin asignar tiene que cumplir un conjunto de criterios de cualificación que se incluirán en este informe. Para incluir en este informe, un segmento sin asignar debe:

* Tener conversiones mayores que la media de todos los segmentos asignados.
* Esté en los 100 segmentos sin asignar por tasa de conversión.

Para leer este informe, ayuda a dividir los resultados en 4 secciones con líneas imaginarias (en rojo) y categorías que se muestran en el informe de muestra siguiente.

![](assets/unmapped-segment-performance.png)

En este informe, solo desea centrarse en aquellos segmentos sin asignar en la sección superior izquierda. Estos segmentos sin asignar muestran tasas de conversión altas para un bajo nivel de impresiones cuando se comparan con los segmentos en las otras tres secciones.

>[!NOTE]
>
>7-day and 30-day look-back periods are only available for Sunday **[!UICONTROL Date Through]** dates.
