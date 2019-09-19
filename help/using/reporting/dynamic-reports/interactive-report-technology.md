---
description: Describe el software subyacente que alimenta los informes interactivos y la programación de actualización de datos.
seo-description: Describe el software subyacente que alimenta los informes interactivos y la programación de actualización de datos.
seo-title: Tecnología de informes
solution: Audience Manager
title: Tecnología de informes
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
translation-type: tm+mt
source-git-commit: b5a962381780f1a1627e39b59e3ca86fd51763b5

---


# Tecnología de informes{#report-technology}

Describe el software subyacente que alimenta los informes interactivos y la programación de actualización de datos.

<!-- 

c_report_technology.xml

 -->

## Informes interactivos Uso de la tecnología Tableau

[!DNL Audience Manager] utiliza el software [Tableau](https://www.tableausoftware.com/) para mostrar datos en los informes interactivos. Con [!DNL Tableau], los [!UICONTROL Delivery and Overlap] informes utilizan señales visuales y símbolos que le ayudan a:

* Encuentre características de alto y bajo rendimiento.
* Las características y los segmentos de puntos con visitantes únicos bajos y altos se superponen.
* Utilice los datos de superposición para crear segmentos de destino.
* Expanda el alcance identificando características relacionadas con baja superposición.

## Programación de actualización de datos

Los datos del informe se actualizan cada domingo cada semana. La actualización procesa los datos del sábado (el día anterior) al domingo anterior.

## Formas, colores y tamaños utilizados en informes interactivos {#shapes-colors-sizes}

La mayoría de los informes interactivos muestran los resultados utilizando formas de diferentes tamaños y colores. Este formato de visualización está diseñado para ayudarle a comprender los datos visualmente, sin tener que desplazarse por filas y columnas de números.

<!-- 

r_legend.xml

 -->

### Leyenda del informe

La tabla siguiente define las formas, los tamaños y los colores utilizados en los informes dinámicos.

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
     <li id="li_371331AE984A4A999CE0596EA13987E0">Los cuadrados indican características de terceros. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Colores</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Los tonos rojos indican solapamiento <i>bajo</i> . </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Los tonos verdes indican solapamiento <i>alto</i> . </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tamaño</b> </td> 
   <td colname="col2"> El tamaño aumenta o disminuye en proporción directa al alcance (el número o el porcentaje de clics o usuarios únicos en una característica o segmento). </td> 
  </tr> 
 </tbody> 
</table>

## Iconos y herramientas del informe explicados {#icons-tools-explained}

Describe cómo buscar y utilizar las distintas herramientas de icono utilizadas en los informes dinámicos.

<!-- 

r_icons.xml

 -->

### Iconos y herramientas de datos

Las siguientes herramientas de iconos están disponibles en la parte inferior de cada ventana de informe dinámico. La siguiente ilustración proporciona más información sobre estas herramientas.

![](assets/tools_icons90.png)

### Exportar datos

Esta herramienta permite exportar datos del informe en 4 formatos diferentes.

| Opción de exportación | Exporta datos |
|---|---|
| **[!UICONTROL Image]** | Como archivo de imagen (.png). Resulta útil cuando desea descargar y compartir datos de informes en su formato gráfico original. |
| **[!UICONTROL PDF]** | Como archivo PDF. |
| **[!UICONTROL Data]** | En una nueva ventana del navegador como datos numéricos en columnas y filas. |
| **[!UICONTROL Crosstab]** | Como archivo .csv. |

### Revertir cambios

Seleccione esta herramienta para deshacer cualquier cambio de clic interactivo que haya realizado en el informe.

### Actualizaciones automáticas

Los informes [!UICONTROL Delivery-Performance] y [!UICONTROL Trait-to-Trait Overlap] son informes dinámicos que responden y cambian según las acciones de clic del usuario.

Por ejemplo: supongamos que desea seleccionar varios anunciantes en el [!UICONTROL Overlap] informe. Cuando se habilita, las actualizaciones automáticas empezarán a devolver datos en cuanto seleccione una casilla de verificación. Este comportamiento dinámico puede interrumpir el flujo de trabajo porque tiene que esperar hasta que el informe termine de procesarse antes de seleccionar otro anunciante. Utilice esta herramienta para desactivar esa función (y volver a activarla) según sea necesario.

### Actualización de datos

Haga clic en el icono de actualización para ejecutar un informe o volver a cargar el conjunto de datos. Cuando las actualizaciones automáticas estén desactivadas, haga clic en actualizar para ejecutar o actualizar el informe.

### Herramienta de búsqueda

La búsqueda está representada por un icono de lupa genérico (no se muestra). El campo de búsqueda se oculta hasta que haga clic en las etiquetas de selección en el lado izquierdo de la pantalla. La tabla siguiente describe la ubicación de la herramienta de búsqueda para cada informe.

| Informe | Para buscar la búsqueda, pase el ratón por encima |
|---|---|
| [!UICONTROL Delivery and Performance] informe | Etiqueta "Nombre del anunciante". |
| [!UICONTROL Overlap] informes | Etiqueta "Nombre SID". |
