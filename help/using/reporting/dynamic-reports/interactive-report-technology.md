---
description: Describe el software subyacente que alimenta los informes interactivos y la programación de actualización de datos.
seo-description: Describe el software subyacente que alimenta los informes interactivos y la programación de actualización de datos.
seo-title: Tecnología de informes
solution: Audience Manager
title: Tecnología de informes
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
feature: Overlap Reports
exl-id: 59d875d6-a630-4795-93a7-1d432860f0a1
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 3%

---

# Tecnología de informes{#report-technology}

Describe el software subyacente que alimenta los informes interactivos y la programación de actualización de datos.

<!-- 

c_report_technology.xml

 -->

## Los informes interactivos utilizan la tecnología Tableau

[!DNL Audience Manager] utiliza  [](https://www.tableausoftware.com/) Tableaussoftware para mostrar los datos en los informes interactivos. Con [!DNL Tableau], los informes [!UICONTROL Delivery and Overlap] utilizan señales visuales y símbolos que le ayudan a:

* Encuentre características de alto y bajo rendimiento.
* Observe los rasgos y segmentos con superposición de visitante único alto y bajo.
* Utilice datos de superposición para crear segmentos de destino.
* Expanda el alcance identificando características relacionadas con baja superposición.

## Programación de la actualización de datos

Los datos del informe se actualizan semanalmente cada domingo. La actualización procesa los datos de sábado (el día anterior) hasta el domingo anterior.

## Formas, colores y tamaños utilizados en informes interactivos {#shapes-colors-sizes}

La mayoría de los informes interactivos muestran resultados utilizando formas de diferentes tamaños y colores. Este formato de visualización está diseñado para ayudarle a comprender los datos visualmente, sin tener que desplazarse por las filas y columnas de números.

<!-- 

r_legend.xml

 -->

### Leyenda del informe

En la tabla siguiente se definen las formas, los tamaños y los colores utilizados en los informes dinámicos.

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
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">Los círculos indican sus propios rasgos de origen. </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">Los cuadrados indican características de terceros. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Colores</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Los tonos rojos indican <i>baja</i> superposición. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Las sombras verdes indican <i>alta</i> superposición. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tamaño</b> </td> 
   <td colname="col2"> El tamaño aumenta o disminuye en proporción directa al alcance (el número o % de clics o usuarios únicos en un rasgo o segmento). </td> 
  </tr> 
 </tbody> 
</table>

## Documentación de Tableau {#tableau-documentation}

Para obtener más información sobre los controles Tableau que puede ver en nuestros informes interactivos, consulte la documentación oficial de [Tableau Server en Linux 2018.2](https://help.tableau.com/v2018.2/server-linux/en-us/get_started_server.htm)
