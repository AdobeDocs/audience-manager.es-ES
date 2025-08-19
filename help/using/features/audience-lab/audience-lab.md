---
description: Cree segmentos de prueba mutuamente excluyentes en Grupos de prueba de segmentos para comparar y medir la eficacia de diferentes destinos. Puede apartar un grupo de control y dividir el segmento en porcentajes de un todo para probar la eficacia.
seo-description: Create mutually exclusive test segments in Segment Test Groups to compare and measure effectiveness of different destinations. You can set aside a control group and divide your segment into percentages of a whole, in order to test efficacy.
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: Audience Lab
exl-id: b7fbeb03-52aa-4489-8fcb-45bc2d26621d
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 2%

---

# [!UICONTROL Audience Lab] {#audience-lab}

Cree segmentos de prueba mutuamente excluyentes en [!UICONTROL Segment Test Groups] para comparar y medir la efectividad de diferentes destinos. Puede apartar un grupo de control y dividir el segmento en porcentajes de un todo para probar la eficacia.

## Información general {#audience-lab-overview}

[!UICONTROL Audience Lab] usa [vínculo de perfil](../../features/profile-merge-rules/merge-rules-overview.md) para las pruebas entre dispositivos. Esto ayuda a garantizar que un usuario cumpla los requisitos del mismo segmento de prueba y reciba el mismo tratamiento en todos los dispositivos. Los segmentos de prueba de los grupos de prueba heredarán la [regla de combinación de perfiles](../../features/profile-merge-rules/merge-rules-dashboard.md) que el segmento base le haya asignado.

La vista predeterminada [!UICONTROL Audience Lab] muestra una tarjeta para cada uno de los grupos de prueba. Haga clic en una tarjeta para acceder a la vista **[!UICONTROL Test Group]**. Esta vista incluye la siguiente información:

* **[Información del grupo de prueba](../../features/audience-lab/audience-lab-information-view.md)**
* **[Sistema de informes de grupo de prueba](../../features/audience-lab/audience-lab-reporting-view.md)**

Puede crear **hasta 10 grupos de prueba**, cada uno con **hasta 15 segmentos de prueba**.

![](assets/test-groups-view.PNG)

## Buscar y filtrar grupos de prueba {#search-and-filter}

Una vez que comience a crear varios grupos de pruebas con varios segmentos de prueba, puede resultar más fácil utilizar el cuadro de búsqueda para encontrar un grupo de pruebas específico. Para buscar un grupo de prueba, haga lo siguiente:

* el nombre del grupo de prueba;
* El nombre de cualquiera de los segmentos de prueba del grupo de prueba;
* Descripción del grupo de prueba.

![](assets/search_and_filter_audience_lab.png)

También puede filtrar los grupos de prueba por estado. Todos los estados disponibles se describen en la sección [Estado](../../features/audience-lab/audience-lab.md#status) a continuación.

## [!UICONTROL Status] {#status}

El estado de un grupo de prueba puede ser activo, programado, pausado, en borrador o completado. En la tabla siguiente se proporciona más información sobre cada uno de ellos:

<table id="table_7A0388BA02E045AC971C06A22DAC2C63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Estado </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> activo </span></b> </p> </td> 
   <td colname="col2"> <p>Un grupo de prueba <i>active</i> significa que los datos se están enviando a los destinos. Pulse <b><span class="uicontrol"> Pausar prueba </span></b> en la tarjeta del grupo de prueba <b><span class="uicontrol"> de </span></b> para suspender el envío de datos a los destinos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> programado </span></b> </p> </td> 
   <td colname="col2"> <p>Un grupo de prueba <i>programado</i> aún no está activo, pero ya no se puede editar. Se activará en la fecha de inicio seleccionada en el asistente <b>Crear grupos de prueba</b>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> pausó </span></b> </p> </td> 
   <td colname="col2"> <p>Un grupo de prueba <i>pausado</i> no envía datos actualmente a los destinos. Pulse <b><span class="uicontrol"> Hacer activo </span></b> en la tarjeta del grupo de prueba <b><span class="uicontrol"> de </span></b> para reanudar el envío de características. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> borrador </span></b> </p> </td> 
   <td colname="col2"> <p>Un grupo de prueba <i>borrador</i> aún no está activo y se puede editar. Todavía no envía datos a los destinos asignados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> completó </span></b> </p> </td> 
   <td colname="col2"> <p>Un grupo de prueba <i>completado</i> ha alcanzado la fecha de finalización seleccionada en el asistente <b><span class="uicontrol"> Crear grupos de prueba </span></b> y ha dejado de enviar datos de informes. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Actions] {#actions}

<table id="table_481A411E2D2F4FE891595D00E775CF60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Acciones </th> 
   <th colname="col2" class="entry"> Descripción </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Editar </span></b> </p> </td>
   <td colname="col2"> <p>Disponible <b>solamente</b> para los grupos de prueba de borrador. Permite reanudar el asistente <b><span class="uicontrol"> Crear nuevo grupo de prueba </span></b>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pausar </span></b> </p> </td>
   <td colname="col2"> <p>Disponible para grupos de prueba activos. Permite pausar el envío de segmentos de prueba a destinos. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Hacer Activo </span></b> </p> </td>
   <td colname="col2"> <p>Disponible para grupos de prueba en pausa. Permite reanudar el envío de segmentos de prueba a destinos. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> vista </span></b> </p> </td>
   <td colname="col2"> <p>Disponible para grupos de prueba completados. Permite ver la información de informes que ha generado la prueba. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> duplicado </span></b> </p> </td>
   <td colname="col2"> <p>Permite crear un nuevo grupo de prueba con la misma configuración que el que está duplicando. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Eliminar </span></b> </p> </td>
   <td colname="col2"> <p>Permite eliminar un grupo de prueba. Los segmentos de prueba se desasignarán de los destinos, el segmento de línea de base y los rasgos de conversión asociados al grupo de prueba se pueden editar por completo. Una alerta le pedirá que descargue el archivo CSV cuando elimine un grupo de prueba para guardar los informes si lo desea. </p> </td>
  </tr>
 </tbody>
</table>
