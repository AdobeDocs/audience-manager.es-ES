---
description: Un informe general devuelve datos sobre el rendimiento de los rasgos, los segmentos y los destinos.
seo-description: A General report in Audience Manager returns performance data on traits, segments, and destinations.
seo-title: General Reports in Audience Manager
solution: Audience Manager
title: Informes generales
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
feature: General & Trend Reports
exl-id: dc16a821-b776-4a04-af60-4b8c914253dd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 1%

---

# Informes generales{#general-reports}

Un [!UICONTROL General] Informe devuelve datos sobre el rendimiento de los rasgos, los segmentos y los destinos.

## Información general {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] utiliza [!UICONTROL Role Based Access Control] ( [!UICONTROL RBAC] ) para ampliar los permisos de grupo usuario a los [!UICONTROL General] informes. Los usuarios solo pueden ver esos rasgos y segmentos en sistema de informes que tienen permisos para vista. [!UICONTROL RBAC] funcionalidad permite controlar qué equipos internos de datos sistema de informes pueden vista. Por ejemplo, una agencia que gestiona diferentes anunciante cuentas puede configurar los permisos usuario grupo de modo que un equipo que administra el cuenta del anunciante A no pueda ver los datos de sistema de informes del anunciante B.

Ejecute un [!UICONTROL General] Informe cuando necesite:

* Revise el rendimiento por rasgo, segmento o destino.
* Seguimiento de impresiones (totales y únicas) a intervalos de 1, 7, 14, 30, 60 y 90 días.
* Revise los recuentos de carga totales y únicos.
* Comparar el rendimiento de rasgos y segmentos.
* Identifique segmentos y rasgos de rendimiento sólidos o deficientes, analice la demanda o compare datos de carga o activación con informes de terceros.
* Exporte datos (formato .csv) para su análisis y uso compartido adicionales.

La siguiente ilustración proporciona información general de alto nivel sobre los elementos clave de la [!UICONTROL General] informe.

![](assets/general_reports.png)

1. Configure las siguientes opciones:

   * **Tipo de informe:** Seleccione el tipo de informe deseado (rasgo, segmento o destino).

   * **Para Fechas Hasta:** Especifique el intervalo de fechas para el informe.

2. Busque un rasgo, segmento o destino por nombre o ID.
3. En la lista de carpetas, arrastre y suelte los rasgos, segmentos o destinos que desee incluir en el informe [!UICONTROL Selections] panel en el lado derecho.
4. Genere el informe para mostrarlo en una tabla exportable.

## Ejecutar un informe general {#run-general-report}

En esta sección se describe cómo ejecutar un [!UICONTROL General] Informe y establecer el tiempo y otras opciones de rendimiento.

<!-- 

t_run_general_report.xml

 -->

1. En la **[!UICONTROL Analytics]** panel, haga clic en **[!UICONTROL General Reports]** .
1. Desde el **[!UICONTROL Report Type]** , seleccione el tipo que desee: Rasgo, Segmento o Destino.
1. *Condicional* Haga clic en el cuadro de fecha para mostrar un calendario y, a continuación, seleccione la fecha de finalización del informe si desea especificar una fecha distinta a la de hoy.
1. Search para una característica, segmento o destino por nombre o ID.
1. Desde la lista de la carpeta, arrastre y suelte las características, los segmentos o los destinos que desee incluir en el [!UICONTROL Selections] panel del lado derecho.
1. Haga clic **[!UICONTROL Run Report]**.

   Los resultados se muestran en una tabla exportable. Haga clic en los encabezados de columna para ordenar los resultados en orden ascendente o de bajada.
1. Seleccione la opción que desee botón en la parte superior del informe para filtrar los datos por rendimiento ( [!UICONTROL Unique Trait Realizations] , [!UICONTROL Total Trait Realizations] o [!UICONTROL Total Trait Population] ) o por tiempo (1, 7, 14, 30, 60 o 90 de día).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] se calculan para [!UICONTROL Rule-based Traits] solo.

1. *Opcional* Clic **[!UICONTROL Export to CSV]**. Esto exporta el [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], y [!UICONTROL Total Trait Population] para todos los intervalos de días.

## Resultados de informes generales explicados {#general-reports-explained}

Los números del [!UICONTROL General Reports] se generan directamente a partir de [!UICONTROL User Profile Store]. Los resultados reflejan la cantidad de usuarios que [!DNL Audience Manager] contenido en el servidor en el momento en que se generaron estos números de informes.

* Estos números no incluyen los ID de visitante con tráfico excesivo. El tráfico de los bots se filtra antes de llegar a nuestro sistema back-end. Además, parte del tráfico de bots se descarta durante una ejecución semanal de trabajo de limpieza en el backend.
* Si incorpora datos mediante procesamiento entrante con la clave desactivada en la [!DNL Audience Manager] UUID, y estos ID incluyen usuarios que ya no están activos en nuestro sistema, estos inactivos [!DNL Audience Manager] Los UUID nunca llegan a [!UICONTROL User Profile Store] y no se incluyen en los informes.
* [!UICONTROL Total Trait Realizations] se calculan para [!UICONTROL Rule-based Traits] solo.

## Resultados de informes generales para características {#general-report-results-traits}

Los filtros siguientes están disponibles cuando se ejecuta un informe General y se selecciona **[!UICONTROL Trait]** como el tipo de informe.

Al filtrar los resultados por [!UICONTROL Device ID] :

* [!UICONTROL Unique Trait Realizations] es el número de visitantes de su dispositivo anónimo que han añadido el rasgo a su perfil en el intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Realization] es el número total de realizaciones de rasgos anónimas dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Population] es el número de visitantes de su dispositivo anónimo que tienen este rasgo en su perfil.

![general-report-traits-device](assets/general-report-traits-deviceid.png)

Al filtrar los resultados por [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] es el número de visitantes autenticados que han agregado el rasgo a su perfil, dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Realization] es el número total de realizaciones de rasgos autenticadas dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Population] es el número de los visitantes autenticados que tienen este rasgo en su perfil.

![general-report-traits-cross-device](assets/general-report-traits-cross-device.png)

<!-- 
### Unique Trait Realizations

This metric represents the unique number of [Audience Manager Unique User IDs (UUID)](../reference/ids-in-aam.md) that qualified for the trait in your selected time range. For example, if a user visited your homepage three times on 10/1, you would see one Unique Trait Realization.

### Total Trait Realizations

This metric represents the total amount of trait fires for the trait in your selected time range. For example, if a user visited your homepage, then navigated to your tech news and your sports news sections, they would appear in the General Report as three total trait realizations, and one unique trait realization.

### Total Trait Population

This metric represents the total amount of Audience Manager UUIDs that are currently qualified for the trait. Use this number to understand the total amount of users you could use for segmentation and targeting. Typically, users remain part of a trait for [120 days](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). For example, a user visiting your homepage three times today and never returning afterwards, would remain as a user in this population every day until 120 days from now. At the 120 day mark, they would be removed from the population. Read our [Trait and Segment Qualification Reference](../features/traits/trait-and-segment-qualification-reference.md) for more examples on the difference between Unique Trait Realizations and Total Trait Population.

The illustration below shows the results of running a general report for the Trait report type. -->
<!-- 
![](assets/general_reports_metrics.png) -->


## Resultados de informes generales para segmentos {#general-report-results-segments}

Las métricas siguientes están disponibles cuando ejecuta un informe General y selecciona **[!UICONTROL Segment]** como tipo de informe:

### Propagación de segmentos en tiempo real

Esta métrica representa el número real de visitantes únicos vistos en tiempo real durante el intervalo de tiempo especificado y que estaban cualificados para el segmento en el momento en que fueron vistos por el Audience Manager.

### Propagación total de segmentos

Esta métrica representa el número total de UUID de Audience Manager cualificados para el segmento dentro del periodo retroactivo seleccionado. La población total de segmentos de 1 día representa la base de usuarios más precisa para la segmentación.

>[!NOTE]
>
>Seleccione **[!UICONTROL Include Destination Mappings]** para ver una desglose de segmento población para los destinos activados.

La ilustración siguiente muestra los resultados de la ejecución de un informe general de la Tipo de informe de segmentos.

![](assets/general_reports_segment_metrics.png)

## Resultados de informes generales para destinos {#general-report-results-destinations}

Las métricas que se muestran a continuación están disponibles cuando se ejecuta un informe general y se selecciona **[!UICONTROL Destination]** como tipo de informe:

**Propagación de segmentos en tiempo real**

Esta métrica representa el número real de visitantes únicos vistos en tiempo real durante el intervalo de tiempo especificado y que estaban cualificados para el segmento en el momento en que fueron vistos por el Audience Manager.

**Población total del segmento**

Este Métrica representa el número total de Audience Manager UUID que pertenecen a una segmento dentro del período de búsqueda, que se enviaron a un destino.

La ilustración siguiente muestra los resultados de ejecutar un informe general para los destinos Tipo de informe.

![](assets/general_reports_destinations.png)
