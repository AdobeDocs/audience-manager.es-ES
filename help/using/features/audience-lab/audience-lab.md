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
source-wordcount: '547'
ht-degree: 4%

---

# [!UICONTROL Audience Lab] {#audience-lab}

Creación de segmentos de prueba mutuamente excluyentes en [!UICONTROL Segment Test Groups] para comparar y medir la efectividad de diferentes destinos. Puede apartar un grupo de control y dividir el segmento en porcentajes de un todo para probar la eficacia.

## Información general {#audience-lab-overview}

[!UICONTROL Audience Lab] utiliza [Vínculo de perfil](../../features/profile-merge-rules/merge-rules-overview.md) para activar las pruebas entre dispositivos. Esto ayuda a garantizar que un usuario cumpla los requisitos del mismo segmento de prueba y reciba el mismo tratamiento en todos los dispositivos. Los segmentos de prueba de los grupos de prueba heredarán el [Regla de combinación de perfiles](../../features/profile-merge-rules/merge-rules-dashboard.md) el segmento base se le ha asignado.

El [!UICONTROL Audience Lab] la vista predeterminada muestra una tarjeta para cada uno de los grupos de prueba. Haga clic en una tarjeta para acceder a **[!UICONTROL Test Group]** vista. Esta vista incluye la siguiente información:

* **[Información del grupo de prueba](../../features/audience-lab/audience-lab-information-view.md)**
* **[Sistema de informes de grupo de prueba](../../features/audience-lab/audience-lab-reporting-view.md)**

Usted es capaz de crear **hasta 10 grupos de prueba**, cada uno con **hasta 15 segmentos de prueba**.

![](assets/test-groups-view.PNG)

## Buscar y filtrar grupos de prueba {#search-and-filter}

Una vez que comience a crear varios grupos de pruebas con varios segmentos de prueba, puede resultar más fácil utilizar el cuadro de búsqueda para encontrar un grupo de pruebas específico. Para buscar un grupo de prueba, haga lo siguiente:

* el nombre del grupo de prueba;
* El nombre de cualquiera de los segmentos de prueba del grupo de prueba;
* Descripción del grupo de prueba.

![](assets/search_and_filter_audience_lab.png)

También puede filtrar los grupos de prueba por estado. Todos los estados disponibles se describen en la [Estado](../../features/audience-lab/audience-lab.md#status) más abajo.

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
   <td colname="col1"> <p> <b><span class="uicontrol"> Activo </span></b> </p> </td> 
   <td colname="col2"> <p>Un <i>activo</i> grupo de prueba significa que los datos se están enviando a destinos. Prensa <b><span class="uicontrol"> Pausar prueba </span></b> en el <b><span class="uicontrol"> Grupo de prueba </span></b> para suspender el envío de datos a los destinos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Programado </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>programado</i> el grupo de prueba aún no está activo, pero ya no se puede editar. Se activará en la fecha de inicio seleccionada en la <b>Crear grupos de prueba</b> asistente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> En pausa </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>pausado</i> el grupo de prueba no envía datos actualmente a los destinos. Prensa <b><span class="uicontrol"> Convertir en activo </span></b> en el <b><span class="uicontrol"> Grupo de prueba </span></b> para reanudar el envío de características. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Borrador </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>borrador</i> el grupo de prueba aún no está activo y puede editarse. Todavía no envía datos a los destinos asignados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Completado </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>completado</i> el grupo de prueba ha alcanzado la fecha de finalización seleccionada en la <b><span class="uicontrol"> Crear grupos de prueba </span></b> asistente y ha dejado de enviar datos de informes. </p> </td>
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
   <td colname="col2"> <p>Disponible <b>solamente</b> para grupos de prueba de borrador. Permite reanudar el <b><span class="uicontrol"> Crear nuevo grupo de prueba </span></b> asistente. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pausa </span></b> </p> </td>
   <td colname="col2"> <p>Disponible para grupos de prueba activos. Permite pausar el envío de segmentos de prueba a destinos. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Convertir en activo </span></b> </p> </td>
   <td colname="col2"> <p>Disponible para grupos de prueba en pausa. Permite reanudar el envío de segmentos de prueba a destinos. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ver </span></b> </p> </td>
   <td colname="col2"> <p>Disponible para grupos de prueba completados. Permite ver la información de informes que ha generado la prueba. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Duplicar </span></b> </p> </td>
   <td colname="col2"> <p>Permite crear un nuevo grupo de prueba con la misma configuración que el que está duplicando. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Eliminar </span></b> </p> </td>
   <td colname="col2"> <p>Permite eliminar un grupo de prueba. Los segmentos de prueba se desasignarán de los destinos, el segmento de línea de base y los rasgos de conversión asociados al grupo de prueba se pueden editar por completo. Una alerta le pedirá que descargue el archivo CSV cuando elimine un grupo de prueba para guardar los informes si lo desea. </p> </td>
  </tr>
 </tbody>
</table>
