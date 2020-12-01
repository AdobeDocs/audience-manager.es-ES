---
description: Cree segmentos de prueba mutuamente excluyentes en los grupos de prueba de segmentos para comparar y medir la eficacia de diferentes destinos. Puede dejar de lado un grupo de control y dividir el segmento en porcentajes de un todo, para probar la eficacia.
seo-description: Cree segmentos de prueba mutuamente excluyentes en los grupos de prueba de segmentos para comparar y medir la eficacia de diferentes destinos. Puede dejar de lado un grupo de control y dividir el segmento en porcentajes de un todo, para probar la eficacia.
seo-title: 'Audience Lab '
solution: Audience Manager
title: 'Audience Lab '
topic: DIL API
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 4%

---


# [!UICONTROL Audience Lab] {#audience-lab}

Cree segmentos de prueba mutuamente excluyentes en [!UICONTROL Segment Test Groups] para comparar y medir la eficacia de diferentes destinos. Puede dejar de lado un grupo de control y dividir el segmento en porcentajes de un todo, para probar la eficacia.

## Información general {#audience-lab-overview}

[!UICONTROL Audience Lab] utiliza  [Perfil ](../../features/profile-merge-rules/merge-rules-overview.md) Linkto para realizar pruebas entre dispositivos. Esto ayuda a garantizar que un usuario cumple los requisitos para el mismo segmento de prueba y recibe el mismo tratamiento en todos los dispositivos. Los segmentos de prueba de los grupos de prueba heredarán la [regla de combinación de Perfiles](../../features/profile-merge-rules/merge-rules-dashboard.md) que el segmento base le ha asignado.

La vista predeterminada [!UICONTROL Audience Lab] muestra una tarjeta para cada uno de los grupos de prueba. Haga clic en una tarjeta para acceder a la vista **[!UICONTROL Test Group]**. Esta vista incluye la siguiente información:

* **[Información del grupo de prueba](../../features/audience-lab/audience-lab-information-view.md)**
* **[Sistema de informes de grupo de prueba](../../features/audience-lab/audience-lab-reporting-view.md)**

Puede crear **hasta 10 grupos de prueba**, cada uno con **hasta 15 segmentos de prueba**.

![](assets/test-groups-view.PNG)

## Buscar y filtrar grupos de pruebas {#search-and-filter}

Una vez que inicio la creación de varios grupos de prueba con varios segmentos de prueba, puede ser más fácil utilizar el cuadro de búsqueda para encontrar un grupo de prueba específico. Puede buscar un grupo de prueba mediante:

* Nombre del grupo de ensayo;
* Nombre de cualquiera de los segmentos de prueba del grupo de prueba;
* Descripción del grupo de prueba.

![](assets/search_and_filter_audience_lab.png)

También puede filtrar los grupos de prueba por estado. Todos los estados disponibles se describen en la sección [Estado](../../features/audience-lab/audience-lab.md#status) a continuación.

## [!UICONTROL Status] {#status}

El estado de un grupo de prueba puede ser activo, programado, en pausa, borrador o completado. Más información sobre cada una de ellas en la tabla siguiente:

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
   <td colname="col2"> <p>Un grupo de prueba <i>activo</i> significa que los datos se están enviando a los destinos. Pulse <b><span class="uicontrol"> Pausar prueba </span></b> en la tarjeta <b><span class="uicontrol"> Grupo de prueba </span></b> para suspender el envío de datos a los destinos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Programado </span></b> </p> </td> 
   <td colname="col2"> <p>Un grupo de prueba <i>programado</i> aún no está activo pero no se puede editar. Se activará en la fecha de inicio seleccionada en el asistente para <b>Crear grupos de prueba</b>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> En pausa </span></b> </p> </td> 
   <td colname="col2"> <p>Un grupo de prueba <i>pausado</i> no envía datos a los destinos. Pulse <b><span class="uicontrol"> Hacer activo </span></b> en la tarjeta <b><span class="uicontrol"> Grupo de prueba </span></b> para reanudar el envío de características. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Borrador </span></b> </p> </td> 
   <td colname="col2"> <p>Un grupo de prueba <i>borrador</i> aún no está activo y puede editarse. Todavía no envía datos a los destinos asignados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Completado </span></b> </p> </td> 
   <td colname="col2"> <p>Un grupo de prueba <i>completado</i> ha alcanzado la fecha de finalización seleccionada en el asistente para <b><span class="uicontrol"> Crear grupos de prueba </span></b> y ha dejado de enviar datos de sistema de informes. </p> </td>
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
   <td colname="col2"> <p>Disponible <b>sólo</b> para grupos de prueba de borrador. Le permite reanudar el asistente <b><span class="uicontrol"> Crear nuevo grupo de pruebas </span></b>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pausa </span></b> </p> </td>
   <td colname="col2"> <p>Disponible para grupos de prueba activos. Permite pausar el envío de segmentos de prueba a destinos. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Activar  </span></b> </p> </td>
   <td colname="col2"> <p>Disponible para grupos de prueba en pausa. Le permite reanudar el envío de los segmentos de prueba a destinos. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ver </span></b> </p> </td>
   <td colname="col2"> <p>Disponible para grupos de prueba completados. Permite la vista de la información de sistema de informes que ha generado la prueba. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Duplicar </span></b> </p> </td>
   <td colname="col2"> <p>Le permite crear un nuevo grupo de prueba con la misma configuración que el grupo que está duplicando. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Eliminar </span></b> </p> </td>
   <td colname="col2"> <p>Permite eliminar un grupo de prueba. Los segmentos de prueba no se asignarán a los destinos, el segmento de línea de base y las características de conversión asociadas al grupo de prueba se podrán editar por completo. Una alerta le pedirá que descargue el archivo CSV cuando elimine un grupo de prueba para guardar el sistema de informes si lo desea. </p> </td>
  </tr>
 </tbody>
</table>