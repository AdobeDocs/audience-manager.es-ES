---
description: Audience Analytics permite enviar segmentos de Audience Manager a Analytics. Para usar esta función, hay que crear un destino de Analytics y segmentos de mapas para este en Audience Manager.
seo-description: Audience Analytics permite enviar segmentos de Audience Manager a Analytics. Para usar esta función, hay que crear un destino de Analytics y segmentos de mapas para este en Audience Manager.
seo-title: Configurar un destino de Analytics
solution: Audience Manager
title: Configurar un destino de Analytics
translation-type: tm+mt
source-git-commit: 3179b9007e102f7031cc4cc9e0da64f77cfa3eeb

---


# Configurar un destino de Analytics

## Requisitos {#requirements}

See [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

## Destinos de Analytics y nuevos destinos de Analytics predeterminados

| Tipo de destino de Analytics | Descripción |
|---|---|
| Valor predeterminado | El nombre de este destino predeterminado es "Adobe Analytics", que puede editar. Los ID de grupos de informes asignados aparecen en el almacenamiento de carpetas para sus características y segmentos de Audience Manager. <br>Audience Manager crea un destino automáticamente si su cuenta tiene: <br> <ul><li>Met the requirements described in the [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) documentation.</li><li>A [report suite](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) in Analytics.</li><li>[Se ha asignado un grupo de informes a una organización](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).</li></ul> |
| Nuevo | Para crear nuevos destinos de Analytics, vaya a Datos de audiencia &gt; Destinos &gt; Crear nuevo destino y siga los pasos para cada sección descrita a continuación. |

## Paso 1: Proporcionar información básica

Esta sección contiene campos y opciones que inician el proceso de creación de destinos de Analytics. Para completar esta sección:

1. Click **Basic Information** to expose the controls.
2. Asigne un nombre al destino. Evite abreviaciones y caracteres especiales.
3. *(Opcional)* Describa el destino. Una descripción concisa es una manera eficaz de definir o proporcionar más información sobre un destino.
4. *(Opcional)* En la lista **Plataforma** , deje el valor predeterminado definido en **Todos**. Actualmente, estas opciones no hacen nada. Están diseñadas para admitir funciones que pueden agregarse más adelante.
5. In the **Category** list, select **Adobe Experience Cloud**.
6. In the **Type** list, select **Adobe Analytics**.
7. Click **Save** to go to the Configuration settings or click **Data Export Labels** to apply export controls to the destination.

>[!NOTE]
>
>For an Analytics destination, the **Auto-fill Destination Mappping** check box and **Segment ID** option are selected by default. No puede cambiar esta configuración.

![basicinformación](assets/basicinformation.png)

## Paso 2: Configurar controles de exportación de datos

This section contains options that apply [Data Export Controls](/help/using/features/data-export-controls.md) to an Analytics destination. Omita este paso si no utiliza los controles de exportación de datos. Para completar esta sección:

1. Click **Data Export Controls** to expose the controls.
2. Select a label that corresponds to the data export control applied to the destination (see [Add Data Export Labels to a Destination](/help/using/features/destinations/manage-destinations.md#add-data-export-labels) ). En los destinos de Analytics, la casilla de verificación PII está seleccionada de forma predeterminada.
3. Haga clic en **Guardar**.

![exportcontrols](assets/exportControls.png)

## Paso 3: Asignar grupos de informes

La sección Configuración enumera los grupos de informes de Analytics que se han activado para el reenvío de servidor. Si tiene varios destinos de Analytics, los grupos de informes asignados a estos destinos serán mutuamente excluyentes y aplicables por Audience Manager. Para completar esta sección:

1. Click **Configuration** to expose the controls.
2. Seleccione uno (o más) grupos de informes a los que desee enviar segmentos.
3. Haga clic en **Guardar**.

![grupos de informes](assets/reportSuites.png)

## Paso 4: Asignaciones de segmentos

Esta sección proporciona opciones que permiten asignar segmentos de forma automática o manual.

| Opción de asignación | Descripción |
|---|---|
| Asignar automáticamente todos los segmentos actuales y futuros | Esta función, seleccionada de forma predeterminada, envía a Analytics todos los segmentos que un visitante califica para cada visita. <br>Si un visitante pertenece a más de 150 segmentos de Audience Manager en una sola visita, solo se envían a Analytics los 150 segmentos cualificados más recientes, mientras que la lista restante se trunca. Se envía un indicador adicional a Analytics que indica que la lista de segmentos se truncó. Esta acción se muestra como «Alcanzado límite de audiencias» en la dimensión Nombre de audiencias y «1» en la dimensión ID de audiencias. See the [FAQ](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) for details. <br>Además, esta opción afecta a la disponibilidad de destino en [el Generador de segmentos](/help/using/features/segments/segment-builder.md). For example, if a segment is mapped automatically to an Analytics destination, that destination is not available for selection in the [destination mappings](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) section of Segment Builder. El destino de Analytics aparece atenuado y muestra "Analytics" en la columna Tipo del navegador de destino. |
| Asignación manual de segmentos | Esta opción expone los controles de búsqueda y exploración que le permiten elegir los segmentos que desee enviar a Analytics. <br>Para buscar un segmento: <br> <ol><li>Escriba el nombre o ID del segmento en el campo de búsqueda.</li><li>Haga clic en <b>Agregar.</b></li><li>Continue to search and add segments or click <b>Done</b>.</li></ol><br>Para buscar un segmento: <ol><li>Click <b>Browse all segments</b>. Esto expone una lista de segmentos disponibles.</li><li>From the list, select the check box of the segment you want to use and click <b>Add selected segments</b>.</li><li>Click <b>Save</b> in the Add Mappings window. No puede cambiar las asignaciones, las fechas de inicio o las de finalización durante la versión beta.</li><li>Continue to browse and add segments or click <b>Done</b>.</li></ol> |

![mapsegments](assets/mapSegments.png)

## Pasos siguientes

Después de crear y guardar un destino, puede trabajar con esos datos en Analytics. Sin embargo, puede tardar unas horas antes de que los datos estén disponibles en los grupos de informes seleccionados. See [Use the Audience Data in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).



