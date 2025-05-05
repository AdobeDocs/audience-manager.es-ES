---
description: Audience Analytics permite enviar segmentos de Audience Manager a Analytics. Para usar esta función, hay que crear un destino de Analytics y segmentos de mapas para este en Audience Manager.
seo-description: Audience Analytics lets you send Audience Manager segments to Analytics. To use this feature, you create an Analytics destination and map segments to it in Audience Manager.
seo-title: Configure an Analytics Destination
solution: Audience Manager
title: Configuración de un destino de Analytics
feature: Adobe Analytics Integration
exl-id: f3ead057-04d1-40cd-8e3d-d0934d85cdb4
source-git-commit: ef8cca16c8c9478f8558c26bf6f3ae95cd72e7ac
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 4%

---

# Configuración de un destino de Analytics

## Requisitos {#requirements}

Para configurar un destino de Analytics, el usuario Audience Manager debe tener permisos de administración. Consulte [Crear usuarios](/help/using/features/administration/administration-overview.md#create-users) en la Guía de administración. Tenga en cuenta que tener el `CREATE_DESTINATIONS` [permiso comodín](/help/using/features/administration/administration-overview.md#wild-card-permissions) no es suficiente para crear destinos de Analytics.
Para obtener más información, consulte Requisitos previos en [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html?lang=es).

## Su destino predeterminado de Analytics y los nuevos destinos de Analytics

| Tipo de destino de Analytics | Descripción |
|---|---|
| Valor predeterminado | El nombre de este destino predeterminado es &quot;Adobe Analytics&quot;, que puede editar. Los ID de grupo de informes asignados aparecen en el almacenamiento de carpetas para sus rasgos de Audience Manager y segmentos. <br>  El Audience Manager crea un destino automáticamente si su cuenta tiene: <br>  <ul><li>Se cumplieron los requisitos descritos en la documentación de [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html?lang=es).</li><li>Un [grupo de informes](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html?lang=es) en Analytics.</li></ul> |
| Nuevo | Para crear nuevos destinos de Analytics, vaya a Datos de audiencia > Destinos > Crear nuevo destino y siga los pasos de cada sección que se describen a continuación. |

## cualificaciones de segmentos de Audience Manager en Adobe Analytics {#segment-qualifications}

Al enviar información de segmentos a un destino de Analytics, Audience Manager solo envía los segmentos para los que el visitante cumple los requisitos. Si un visitante deja de cumplir los requisitos para un segmento, esta información se _no_ reenvía a Adobe Analytics.

Por ejemplo, considere las siguientes reglas de segmentos:

* Segmento A: Rasgo 1 Y Rasgo 2
* Segmento B: Rasgo 1 Y NO Rasgo 2

En los informes de Analytics, puede que se muestre un perfil cualificado para ambos segmentos, aunque haya dejado de cumplir los requisitos para el segmento B.

## Paso 1: Proporcionar información básica

Esta sección contiene campos y opciones que inician el proceso de creación de destinos de Analytics. Para completar esta sección:

1. Haga clic en **Información básica** para mostrar los controles.
2. Nombre el destino. Evite las abreviaciones y los caracteres especiales.
3. *(Opcional)* Describa el destino. Una descripción concisa es una forma eficaz de definir o proporcionar más información sobre un destino.
4. *(Opcional)* En la lista **Plataforma**, deje el valor predeterminado establecido en **Todos**. Actualmente, estas opciones no hacen nada. Están diseñadas para admitir funciones que se puedan agregar más adelante.
5. En la lista **Categoría**, seleccione **Adobe Experience Cloud**.
6. En la lista **Type**, seleccione **Adobe Analytics**.
7. Haga clic en **Guardar** para ir a los ajustes de configuración o haga clic en **Etiquetas de exportación de datos** para aplicar los controles de exportación al destino.

>[!NOTE]
>
>Para un destino de Analytics, la casilla de verificación **Asignación de destino de relleno automático** y la opción **ID de segmento** están seleccionadas de forma predeterminada. No puede cambiar esta configuración.

![información básica](assets/basicinformation.png)

## Paso 2: Configuración de los controles de exportación de datos

Esta sección contiene opciones que aplican [controles de exportación de datos](/help/using/features/data-export-controls.md) a un destino de Analytics. Omita este paso si no utiliza controles de exportación de datos. Para completar esta sección:

1. Haga clic en **Controles de exportación de datos** para mostrar los controles.
1. Seleccione una etiqueta que corresponda al control de exportación de datos aplicado al destino (consulte [Agregar etiquetas de exportación de datos a un destino](/help/using/features/destinations/add-data-export-labels.md) ). Para destinos de Analytics, la casilla de verificación PII está seleccionada de forma predeterminada.
1. Haga clic en **Guardar**.

![controles de exportación](assets/exportControls.png)

## Paso 3: Asignación de grupos de informes

La sección Configuración enumera los grupos de informes de Analytics que se han habilitado para el reenvío del lado del servidor. Si tiene varios destinos de Analytics, los grupos de informes asignados a estos destinos se excluirán mutuamente y el Audience Manager los aplicará. Para completar esta sección:

1. Haga clic en **Configuración** para mostrar los controles.
1. Seleccione uno o varios grupos de informes a los que desee enviar segmentos.
1. Haga clic en **Guardar**.

![grupos de informes](assets/reportSuites.png)

## Paso 4: Asignaciones de segmentos

Esta sección proporciona opciones que le permiten asignar segmentos automática o manualmente.

| Opción de asignación | Descripción |
|---|---|
| Asignar automáticamente todos los segmentos actuales y futuros | Seleccionada de forma predeterminada, esta función envía a Analytics, para cada visita, todos los segmentos a los que el visitante pertenece. <br>  Si un visitante pertenece a más de 150 segmentos del Audience Manager en una sola visita, solo se envían a Analytics los 150 segmentos para los que se ha obtenido cualificación más recientemente y el resto se trunca. Se envía a Analytics un indicador adicional que indica que la lista de segmentos se ha truncado. Esta acción se muestra como &quot;Alcanzado límite de audiencias&quot; en la dimensión Nombre de audiencias y &quot;1&quot; en la dimensión ID de audiencias. Consulte las [preguntas frecuentes](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html?lang=es) para obtener más información. <br>  Además, esta opción afecta a la disponibilidad de destino en [Generador de segmentos](/help/using/features/segments/segment-builder.md). Por ejemplo, si un segmento se asigna automáticamente a un destino de Analytics, ese destino no está disponible para su selección en la sección [asignaciones de destino](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) del Generador de segmentos. El destino de Analytics aparece atenuado y muestra &quot;Analytics&quot; en la columna Tipo del explorador de destino. |
| Asignar segmentos manualmente | Esta opción expone los controles de búsqueda y exploración que le permiten elegir qué segmentos desea enviar a Analytics. <br>  Para buscar un segmento: <br>  <ol><li>Escriba el nombre o ID del segmento en el campo de búsqueda.</li><li>Haga clic en <b>Agregar.</b></li><li>Continúe buscando y agregando segmentos o haga clic en <b>Listo</b>.</li></ol><br>  Para buscar un segmento: <ol><li>Haga clic en <b>Examinar todos los segmentos</b>. Esto expone una lista de segmentos disponibles.</li><li>En la lista, seleccione la casilla del segmento que desee usar y haga clic en <b>Agregar segmentos seleccionados</b>.</li><li>Haga clic en <b>Guardar</b> en la ventana Agregar asignaciones. No puede cambiar las asignaciones, las fechas de inicio o las de finalización durante la versión beta.</li><li>Continúe explorando y agregando segmentos o haga clic en <b>Listo</b>.</li></ol> ![mapsegments](assets/mapSegments.png) |

## Pasos siguientes

Después de crear y guardar un destino, puede trabajar con esos datos en Analytics. Sin embargo, los datos pueden tardar unas horas en estar disponibles en los grupos de informes seleccionados. Ver [Usar los datos de audiencia en Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html?lang=es).
