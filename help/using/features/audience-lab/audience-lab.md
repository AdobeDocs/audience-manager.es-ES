---
description: Cree segmentos de prueba mutuamente excluyentes en Grupos de prueba de segmentos para comparar y medir la eficacia de los diferentes destinos. Puede apartar un grupo de control y dividir el segmento en porcentajes del mismo para probar la eficacia.
seo-description: Cree segmentos de prueba mutuamente excluyentes en Grupos de prueba de segmentos para comparar y medir la eficacia de los diferentes destinos. Puede apartar un grupo de control y dividir el segmento en porcentajes del mismo para probar la eficacia.
seo-title: Audiencia Lab
solution: Audience Manager
title: Audiencia Lab
topic: API DIL
uuid: aaee 820 c -1 e 78-4 fd 4-bd 8 f -2629085 d 78 e 9
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab {#audience-lab}

Create mutually exclusive test segments in [!UICONTROL Segment Test Groups] to compare and measure effectiveness of different destinations. Puede apartar un grupo de control y dividir el segmento en porcentajes del mismo para probar la eficacia.

## Información general {#audience-lab-overview}

[!UICONTROL Audience Lab] utiliza [el vínculo de perfil](../../features/profile-merge-rules/merge-rules-overview.md) para realizar pruebas entre dispositivos. Esto ayuda a garantizar que un usuario cumpla los mismos segmentos de prueba y recibe el mismo tratamiento en todos los dispositivos. The test segments in test groups will inherit the [Profile Merge Rule](../../features/profile-merge-rules/merge-rules-dashboard.md) the base segment has assigned to it.

The [!UICONTROL Audience Lab] default view displays a card for each of the test groups. Click a card to access the **[!UICONTROL Test Group]** view. Esta vista incluye la siguiente información:

* **[Información de grupo de prueba](../../features/audience-lab/audience-lab-information-view.md)**
* **[Informes de grupos de prueba](../../features/audience-lab/audience-lab-reporting-view.md)**

You are able to create **up to 10 test groups**, each one with **up to 15 test segments**.

![](assets/test-groups-view.PNG)

## Search and Filter Test Groups {#search-and-filter}

Una vez que comience a crear varios grupos de prueba con varios segmentos de prueba, puede ser más fácil utilizar el cuadro de búsqueda para encontrar un grupo de prueba específico. Puede buscar un grupo de prueba por:

* El nombre del grupo de prueba;
* Nombre de cualquiera de los segmentos de prueba del grupo de prueba;
* Descripción del grupo de prueba.

![](assets/search_and_filter_audience_lab.png)

También puede filtrar los grupos de prueba por estado. All available statuses are described in the [Status](../../features/audience-lab/audience-lab.md#status) section below.

## Estado {#status}

El estado de un grupo de prueba puede estar activo, programado, pausado, borrador o completado. Más información sobre cada una de ellas en la siguiente tabla:

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
   <td colname="col2"> <p>An <i>active</i> test group means that data is currently being sent to destinations. Press <b><span class="uicontrol"> Pause Test </span></b> in the <b><span class="uicontrol"> Test Group </span></b> card to suspend sending data to destinations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Programado </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>scheduled</i> test group is not yet active but cannot be edited anymore. It will become active at the start date you selected in the <b>Create Test Groups</b> wizard. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> En pausa </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>paused</i> test group does not currently send data to destinations. Press <b><span class="uicontrol"> Make Active </span></b> in the <b><span class="uicontrol"> Test Group </span></b> card to resume sending traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Borrador </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>draft</i> test group is not yet active and can still be edited. Todavía no envía datos a los destinos asignados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Completado </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>completed</i> test group has reached the end date you selected in the <b><span class="uicontrol"> Create Test Groups </span></b> wizard and has stopped sending reporting data. </p> </td>
  </tr>
 </tbody>
</table>

## Acciones {#actions}

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
   <td colname="col2"> <p>Available <b>only</b> for draft test groups. Allows you to resume the <b><span class="uicontrol"> Create New Test Group </span></b> wizard. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pausa </span></b> </p> </td>
   <td colname="col2"> <p>Disponible para grupos de prueba activos. Permite pausar el envío de segmentos de prueba a destinos. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Active </span></b> </p> </td>
   <td colname="col2"> <p>Disponible para grupos de prueba en pausa. Permite reanudar el envío de segmentos de prueba a destinos. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ver </span></b> </p> </td>
   <td colname="col2"> <p>Disponible para grupos de prueba completados. Permite ver la información de informes que ha generado la prueba. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Duplicar </span></b> </p> </td>
   <td colname="col2"> <p>Permite crear un nuevo grupo de prueba con la misma configuración que la que está duplicando. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Eliminar </span></b> </p> </td>
   <td colname="col2"> <p>Permite eliminar un grupo de prueba. Los segmentos de prueba no se asignarán a los destinos, el segmento de línea base y las características de conversión asociadas al grupo de prueba son totalmente editables. Una alerta le solicitará que descargue el archivo CSV cuando elimine un grupo de prueba para guardar los informes si lo desea. </p> </td>
  </tr>
 </tbody>
</table>