---
description: El informe Rendimiento del segmento compara segmentos asignados y no asignados por impresiones y únicos de segmentos en tiempo real. Un segmento asignado es un segmento que crea y envía a un destino para su segmentación. Un segmento sin asignar es un segmento que ha creado pero que no ha enviado a un destino para su segmentación. La comparación de estos distintos tipos de segmentos dentro de y entre informes le ayuda a optimizar las campañas existentes y a encontrar segmentos que no tiene en cuenta y que puede que desee enviar a un destino para este fin.
seo-description: El informe Rendimiento del segmento compara segmentos asignados y no asignados por impresiones y únicos de segmentos en tiempo real. Un segmento asignado es un segmento que crea y envía a un destino para su segmentación. Un segmento sin asignar es un segmento que ha creado pero que no ha enviado a un destino para su segmentación. La comparación de estos distintos tipos de segmentos dentro de y entre informes le ayuda a optimizar las campañas existentes y a encontrar segmentos que no tiene en cuenta y que puede que desee enviar a un destino para este fin.
seo-title: Informe de Rendimiento del segmento
solution: Audience Manager
title: Informe Rendimiento del segmento para editores
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
feature: Informes de optimización de Audiencia
exl-id: 0cc10399-5737-4d82-a1f6-9561e024054d
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 2%

---

# Informe de Rendimiento del segmento{#segment-performance-report}

El informe Rendimiento del segmento compara segmentos asignados y no asignados por impresiones y únicos de segmentos en tiempo real.

Un segmento asignado es un segmento que crea y envía a un destino para su segmentación. Un segmento sin asignar es un segmento que ha creado pero que no ha enviado a un destino para su segmentación.

La comparación de estos distintos tipos de segmentos dentro de y entre informes le ayuda a optimizar las campañas existentes y a encontrar segmentos que no tiene en cuenta y que puede que desee enviar a un destino para este fin.

## Casos de uso {#use-cases}

Con el informe [!UICONTROL Segment Performance], puede:

* Identifique los segmentos de audiencia asignados que impulsan el rendimiento o la escala.
* Identifique los segmentos sin asignar que se presentarán en futuras campañas, según la contribución de una audiencia al rendimiento anterior.

## Uso del informe Rendimiento del segmento {#using-segment-performance-report}

Alterne entre **[!UICONTROL Mapped]** y **[!UICONTROL Unmapped]** para seleccionar segmentos asignados a un destino o no. Seleccione **[!UICONTROL All]** para incluir todos los segmentos en el informe.

Utilice los controles **Day Range** y **Date Through** para ajustar el intervalo retrospectivo. Tenga en cuenta que los periodos retrospectivos de 7 días y 30 días solo están disponibles para las fechas de domingo.

Utilice el cuadro desplegable **[!UICONTROL Line Item]** para seleccionar las propiedades web para las que desea devolver información.

En el cuadro desplegable **[!UICONTROL Segment Data Source]**, seleccione las fuentes de datos que contengan los segmentos que desee ver en el informe.

Utilice el cuadro desplegable **[!UICONTROL Segment]** para seleccionar qué segmentos desea ver en el informe.

>[!IMPORTANT]
>
>Al habilitar [!UICONTROL Audience Optimization for Publishers], debe incluir metadatos descriptivos para [!UICONTROL Line Item IDs], tal como se describe en el paso 3 de [Importar archivos de datos de Google Ad Manager (anteriormente DFP) en el Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Al hacerlo, se asegura de que el informe detalle la propiedad web como [!UICONTROL Line Item] en lugar de [!UICONTROL Line Item ID].

## Interpretación de los resultados {#interpreting-results}

Su informe [!UICONTROL Segment Performance] puede tener un aspecto similar al que se muestra a continuación. En el informe, haga clic en una burbuja para ver los datos subyacentes. Consulte las descripciones para obtener información adicional en la tabla que se encuentra debajo del informe de ejemplo.

![](assets/publisher_segment_performance.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Segmento </p> </td> 
   <td colname="col2"> <p>El nombre alfanumérico que asignó a este segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de segmento </p> </td> 
   <td colname="col2"> <p>ID exclusivo de este segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Elemento de línea </p> </td> 
   <td colname="col2"> <p>La propiedad web de la que verá este informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Clics </p> </td> 
   <td colname="col2"> <p>Número de veces que los miembros de este rasgo han hecho clic en elementos de la propiedad web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Impresiones </p> </td> 
   <td colname="col2"> <p>Número de veces que los miembros de este rasgo han estado expuestos al inventario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>Tasa de pulsaciones. </p> <p>Esta métrica transmite el porcentaje de impresiones seguido de clics. Dividir clics por impresiones para obtener esta métrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Propagación de segmentos en tiempo real </p> </td> 
   <td colname="col2"> <p>La cantidad real de visitantes únicos vistos en tiempo real durante el intervalo de tiempo especificado y que fueron calificados para el segmento en el momento en que fueron vistos por el <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cómo leer los resultados del segmento asignado {#read-mapped-segment}

La posición de los segmentos asignados en un informe puede indicarle mucho sobre qué segmentos tienen un buen rendimiento y dónde podría necesitar realizar algunos ajustes.

Para leer el informe, ayuda a dividir los resultados en cuatro secciones con líneas imaginarias (en rojo) y las categorías que se muestran en el informe de muestra a continuación. Las etiquetas del ejemplo pueden ayudarle a comprender el rendimiento del segmento y cómo responder a estos resultados.

![](assets/publisher_segment_performance_mapped.png)

## Cómo leer los resultados del segmento sin asignar {#read-unmapped-segment}

Mirar los segmentos sin asignar en un informe [!UICONTROL Segment Performance] es una buena manera de encontrar nuevos segmentos que no ha considerado para la segmentación. De hecho, algunos de estos segmentos pueden superar el rendimiento de sus segmentos asignados.

Para leer este informe, ayuda a dividir los resultados en cuatro secciones con líneas imaginarias (en rojo) y categorías que se muestran en el informe de muestra a continuación.

![](assets/publisher_segment_performance_unmapped.png)
