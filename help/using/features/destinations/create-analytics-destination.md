---
description: Audience Analytics permite enviar segmentos de Audience Manager a Analytics. Para usar esta función, hay que crear un destino de Analytics y segmentos de mapas para este en Audience Manager.
seo-description: Audience Analytics permite enviar segmentos de Audience Manager a Analytics. Para usar esta función, hay que crear un destino de Analytics y segmentos de mapas para este en Audience Manager.
seo-title: Configuración de un destino de Analytics
solution: Audience Manager
title: Configuración de un destino de Analytics
feature: Integration with Analytics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '864'
ht-degree: 9%

---


# Configuración de un destino de Analytics

## Requisitos {#requirements}

Para configurar un destino de Analytics, el usuario Audience Manager debe tener permisos de administrador. Consulte [Crear usuarios](/help/using/features/administration/administration-overview.md#create-users) en la Guía de administración. Tenga en cuenta que el `CREATE_DESTINATIONS` [permiso comodín](/help/using/features/administration/administration-overview.md#wild-card-permissions) no es suficiente para crear destinos de Analytics.
Para obtener más información, consulte Requisitos previos en [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html).

## Su destino de Analytics predeterminado y sus nuevos destinos de Analytics

| Tipo de destino de Analytics | Descripción |
|---|---|
| Valor predeterminado | El nombre de este destino predeterminado es &quot;Adobe Analytics&quot;, que puede editar. Las ID de los grupos de informes asignados aparecen en el almacenamiento de carpetas para sus características y segmentos de Audience Manager. <br>  Audience Manager crea un destino automáticamente si su cuenta tiene:  <br>  <ul><li>Cumplir los requisitos descritos en la documentación de [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html).</li><li>Un [grupo de informes](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html) en Analytics.</li><li>[Se asignó un grupo de informes a una organización](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html).</li></ul> |
| Nuevo | Para crear nuevos destinos de Analytics, vaya a Datos de Audiencia > Destinos > Crear nuevo destino y siga los pasos para cada sección que se describe a continuación. |

## Paso 1: Proporcionar información básica

Esta sección contiene campos y opciones que inicio el proceso de creación de destinos de Analytics. Para completar esta sección:

1. Haga clic en **Información básica** para exponer los controles.
2. Asigne un nombre al destino. Evite abreviaciones y caracteres especiales.
3. *(Opcional)* Describa el destino. Una descripción concisa es una forma eficaz de definir o proporcionar más información sobre un destino.
4. *(Opcional)* En la lista  **** Plataformas, deje el valor predeterminado establecido en  **Todos**. Actualmente, estas opciones no hacen nada. Están diseñadas para admitir funciones que se pueden agregar más adelante.
5. En la lista **Categoría**, seleccione **Adobe Experience Cloud**.
6. En la lista **Tipo**, seleccione **Adobe Analytics**.
7. Haga clic en **Guardar** para ir a la configuración o haga clic en **Etiquetas de exportación de datos** para aplicar controles de exportación al destino.

>[!NOTE]
>
>Para un destino de Analytics, la casilla de verificación **Asignación de destino de relleno automático** y la opción **ID de segmento** están seleccionadas de forma predeterminada. No puede cambiar esta configuración.

![basicinformation](assets/basicinformation.png)

## Paso 2: Configurar controles de exportación de datos

Esta sección contiene opciones que aplican [Controles de exportación de datos](/help/using/features/data-export-controls.md) a un destino de Analytics. Omita este paso si no utiliza controles de exportación de datos. Para completar esta sección:

1. Haga clic en **Controles de exportación de datos** para exponer los controles.
1. Seleccione una etiqueta que corresponda al control de exportación de datos aplicado al destino (consulte [Añadir etiquetas de exportación de datos a un destino](/help/using/features/destinations/add-data-export-labels.md) ). Para los destinos de Analytics, la casilla de verificación PII está activada de forma predeterminada.
1. Haga clic en **Guardar**.

![controles de exportación](assets/exportControls.png)

## Paso 3: Asignar grupos de informes

La sección Configuración lista los grupos de informes de Analytics que se han habilitado para el reenvío del lado del servidor. Si tiene varios destinos de Analytics, los grupos de informes asignados a estos destinos serán mutuamente excluyentes y el Audience Manager los aplicará. Para completar esta sección:

1. Haga clic en **Configuración** para exponer los controles.
1. Seleccione uno o varios grupos de informes a los que desee enviar segmentos.
1. Haga clic en **Guardar**.

![grupos de informes](assets/reportSuites.png)

## Paso 4: Asignaciones de segmentos

Esta sección proporciona opciones que le permiten asignar segmentos de forma automática o manual.

| Opción de asignación | Descripción |
|---|---|
| Asignación automática de todos los segmentos actuales y futuros | Seleccionado de forma predeterminada, esta función envía todos los segmentos para los que un visitante cumple los requisitos, por visita, a Analytics. <br>  Si un visitante pertenece a más de 150 segmentos de Audience Manager en una sola visita, solo se envían a Analytics los segmentos cualificados más recientes, mientras que la lista restante se trunca. Se envía a Analytics un indicador adicional que indica que la lista del segmento se ha truncado. Esta acción se muestra como &quot;límite de Audiencia alcanzado&quot; en la dimensión Nombre de Audiencias y &quot;1&quot; en la dimensión ID de Audiencias. Consulte las [preguntas más frecuentes](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html) para obtener más información. <br>  Además, esta opción afecta a la disponibilidad del destino en el Generador  [de segmentos](/help/using/features/segments/segment-builder.md). Por ejemplo, si un segmento se asigna automáticamente a un destino de Analytics, dicho destino no estará disponible para su selección en la sección [asignaciones de destino](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) del Generador de segmentos. El destino de Analytics aparece atenuado y muestra &quot;Analytics&quot; en la columna Tipo del navegador de destino. |
| Asignación manual de segmentos | Esta opción expone los controles de búsqueda y exploración que le permiten elegir los segmentos que desea enviar a Analytics. <br>  Para buscar un segmento:  <br>  <ol><li>Escriba el nombre o ID del segmento en el campo de búsqueda.</li><li>Haga clic en <b>Agregar.</b></li><li>Continúe buscando y agregando segmentos o haga clic en <b>Finalizado</b>.</li></ol><br>  Para buscar un segmento: <ol><li>Haga clic en <b>Examinar todos los segmentos</b>. Esto expone una lista de segmentos disponibles.</li><li>En la lista, seleccione la casilla de verificación del segmento que desee utilizar y haga clic en <b>Añadir segmentos seleccionados</b>.</li><li>Haga clic en <b>Guardar</b> en la ventana Añadir asignaciones. No se pueden cambiar las asignaciones, los inicios ni las fechas de finalización durante la versión beta.</li><li>Continúe explorando y agregando segmentos o haga clic en <b>Finalizado</b>.</li></ol> ![mapsegments](assets/mapSegments.png) |

## Pasos siguientes

Después de crear y guardar un destino, puede trabajar con esos datos en Analytics. Sin embargo, pueden pasar unas horas antes de que los datos estén disponibles en los grupos de informes seleccionados. Consulte [Uso de los datos de Audiencia en Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html).
