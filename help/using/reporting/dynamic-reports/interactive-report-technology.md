---
description: Describe el software subyacente que alimenta los informes interactivos y la programación de actualizaciones de datos.
seo-description: Describe el software subyacente que alimenta los informes interactivos y la programación de actualizaciones de datos.
seo-title: Tecnología de informes
solution: Audience Manager
title: Tecnología de informes
uuid: 5 f 3 d 815 b-e 1 e 6-42 f 2-b 848-ac 035 a 5 aa 77 d
translation-type: tm+mt
source-git-commit: b5a962381780f1a1627e39b59e3ca86fd51763b5

---


# Report Technology{#report-technology}

Describe el software subyacente que alimenta los informes interactivos y la programación de actualizaciones de datos.

<!-- 

c_report_technology.xml

 -->

## Informes interactivos Utilizar tecnología Tableau

[!DNL Audience Manager] utiliza [software Tableau](https://www.tableausoftware.com/) para mostrar datos en los informes interactivos. With [!DNL Tableau], the [!UICONTROL Delivery and Overlap] reports use visual cues and symbols that help you:

* Busque características de alto y bajo rendimiento.
* Los rasgos de spot y los segmentos con una superposición de visitante único y bajo.
* Utilice los datos superpuestos para generar segmentos de objetivo.
* Amplíe el alcance identificando características relacionadas con superposición baja.

## Programación de actualizaciones de datos

Los datos del informe se actualizan semanalmente cada domingo. La actualización procesa los datos del sábado (el día anterior) al domingo anterior.

## Shapes, Colors, and Sizes Used in Interactive Reports {#shapes-colors-sizes}

La mayoría de los informes interactivos muestran resultados utilizando formas de diferentes tamaños y colores. Este formato de visualización está diseñado para ayudarle a comprender los datos visualmente, sin tener que esperar a través de filas y columnas de números.

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
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Red shades indicate <i>low</i> overlap. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Green shades indicate <i>high</i> overlap. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tamaño</b> </td> 
   <td colname="col2"> El tamaño aumenta o disminuye la proporción directa al alcance (el número o el porcentaje de clics o usuarios únicos en un rasgo o segmento). </td> 
  </tr> 
 </tbody> 
</table>

## Report Icons and Tools Explained {#icons-tools-explained}

Describe cómo buscar y utilizar las distintas herramientas de iconos utilizadas en los informes dinámicos.

<!-- 

r_icons.xml

 -->

### Herramientas y iconos de datos

Los siguientes iconos están disponibles en la parte inferior de cada ventana de informe dinámico. La siguiente ilustración proporciona más información sobre estas herramientas.

![](assets/tools_icons90.png)

### Exportar datos

Esta herramienta permite exportar datos del informe en 4 formatos diferentes.

| Opción de exportación | Exporta datos |
|---|---|
| **[!UICONTROL Image]** | Como archivo de imagen (. png). Útil cuando desee descargar y compartir datos de informes en su formato gráfico original. |
| **[!UICONTROL PDF]** | Como archivo PDF. |
| **[!UICONTROL Data]** | En una nueva ventana del explorador como datos numéricos en columnas y filas. |
| **[!UICONTROL Crosstab]** | Como archivo. csv. |

### Revertir cambios

Seleccione esta herramienta para deshacer los cambios interactivos que haya realizado en el informe.

### Actualizaciones automáticas

[!UICONTROL Delivery-Performance] Los [!UICONTROL Trait-to-Trait Overlap] informes e informes son informes dinámicos que responden y cambian según las acciones de clics del usuario.

For example, say you want to select several advertisers in the [!UICONTROL Overlap] report. Cuando esté activada, las actualizaciones automáticas empezarán a devolver datos en cuanto seleccione una casilla de verificación. Este comportamiento dinámico puede interrumpir el flujo de trabajo porque tiene que esperar hasta que el informe termine de procesarse antes de seleccionar otro anunciante. Utilice esta herramienta para desactivar la función (y volver a activarla) según sea necesario.

### Actualización de datos

Haga clic en el icono Actualizar para ejecutar un informe o volver a cargar el conjunto de datos. Cuando las actualizaciones automáticas están desactivadas, haga clic en actualizar para ejecutar o actualizar el informe.

### Herramienta de búsqueda

La búsqueda se representa mediante un icono de lupa genérico (no se muestra). El campo de búsqueda se oculta hasta que se hace clic en las etiquetas de selección en el lado izquierdo de la pantalla. La tabla siguiente describe la ubicación de la herramienta de búsqueda para cada informe.

| Informe | Para buscar búsqueda, coloque el puntero sobre |
|---|---|
| [!UICONTROL Delivery and Performance] informe | La etiqueta "Nombre del anunciante". |
| [!UICONTROL Overlap] informes | La etiqueta "Nombre del SID". |
