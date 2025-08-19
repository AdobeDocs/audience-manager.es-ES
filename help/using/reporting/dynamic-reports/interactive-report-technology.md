---
description: Describe el software subyacente que impulsa los informes interactivos y la programación de actualización de datos.
seo-description: Describes the underlying software that powers the interactive reports and the data update schedule.
seo-title: Report Technology
solution: Audience Manager
title: Tecnología de informes
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
feature: Overlap Reports
exl-id: 59d875d6-a630-4795-93a7-1d432860f0a1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 0%

---

# Tecnología de informes{#report-technology}

Describe el software subyacente que impulsa los informes interactivos y la programación de actualización de datos.

<!-- 

c_report_technology.xml

 -->

## interactivo informes usan tecnología Tableau

[!DNL Audience Manager] usa [el software Tableau](https://www.tableausoftware.com/) para mostrar los datos en los informes interactivos. Con [!DNL Tableau], los [!UICONTROL Delivery and Overlap] informes utilizan indicaciones visuales y símbolos que le ayudan a:

* Encuentre características de alto y bajo rendimiento.
* Observe rasgos y segmentos con superposición de visitante único baja y alta.
* Utilice datos de superposición para versión segmentos de destino.
* Amplíe el alcance identificando rasgos relacionados con poca superposición.

## Programación de actualización de datos

Los datos del informe se actualizan semanalmente cada domingo. La actualización procesa los datos del sábado (el día anterior) al domingo anterior.

## Formas, colores y tamaños utilizados en interactivo informes {#shapes-colors-sizes}

La mayoría de los informes interactivos muestran los resultados utilizando formas de diferentes tamaños y colores. Este formato de visualización está diseñado para ayudarle a dar sentido a los datos visualmente, sin tener que recorrer filas y columnas de números.

<!-- 

r_legend.xml

 -->

### Leyenda del informe

La tabla siguiente define las formas, los tamaños y los colores que se utilizan en los informes dinámicos.

<table id="table_EC180A96E3784FC6B81FCFB546C4A3FA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento de datos </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Formas</b> </td> 
   <td colname="col2"> 
    <ul id="ul_076773ABD0BB4CE6834ACFA8B3D6AC2E"> 
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">Los círculos indican sus propias características de origen. </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">Los cuadrados indican terceros rasgos. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Colores</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Los tonos rojos indican <i>poca</i> superposición. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Los tonos verdes indican <i>una gran</i> superposición. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tamaño</b> </td> 
   <td colname="col2"> El tamaño aumenta o disminuye en proporción directa al alcance (el número o % de clics o usuarios únicos en un rasgo o segmento). </td> 
  </tr> 
 </tbody> 
</table>

## Tableau Documentación {#tableau-documentation}

Para obtener más información sobre los controles de Tableau que puede ver en nuestros informes interactivos, consulte la documentación [oficial de Tableau Server en Linux 2018.2](https://help.tableau.com/v2018.2/server-linux/en-us/get_started_server.htm)
