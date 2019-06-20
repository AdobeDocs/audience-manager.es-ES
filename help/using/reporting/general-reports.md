---
description: Un informe General devuelve datos de rendimiento sobre características, segmentos y destinos.
seo-description: Un informe General de Audience Manager devuelve datos de rendimiento sobre características, segmentos y destinos.
seo-title: Informes generales en Audience Manager
solution: Audience Manager
title: Informes generales
uuid: 0 cea 75 a 0-969 e -4 ee 3-971 a -60 b 911711 e 52
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# General Reports{#general-reports}

[!UICONTROL General] Un informe devuelve datos de rendimiento en características, segmentos y destinos.

## Información general {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] utiliza [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para ampliar los permisos de grupos de usuarios a [!UICONTROL General] los informes. Los usuarios solo pueden ver las características y los segmentos en los informes que tienen permisos para ver. [!UICONTROL RBAC] permite controlar qué datos de informes pueden ver los equipos internos. Por ejemplo, una agencia que administra diferentes cuentas de anunciante puede configurar permisos de grupos de usuarios para que un equipo que administra la cuenta de Anunciante A pueda ver los datos de informes del Anunciante B.

Run a [!UICONTROL General] report when you need to:

* Revise el rendimiento por características, segmentos o destinos.
* Rastree impresiones (total y único) en 1, 7, 14, 30, 60, 90 días y intervalos de duración.
* Revise el total y los recuentos únicos de carga.
* Compare el rendimiento de características y segmentos.
* Identifique los segmentos y características de rendimiento fuerte o deficiente, analice la demanda o compare los datos de carga y activador con informes de terceros.
* Exporte datos (formato. csv) para realizar análisis y compartir más.

The following illustration provides a high-level overview of key elements in the [!UICONTROL General] report.

![](assets/general_reports.png)

1. Configure las siguientes opciones:

   * **Tipo de informe:** Seleccione el tipo de informe deseado (Características, Segmento o Destino).

   * **Para fechas mediante:** Especifique el intervalo de fechas del informe.

2. Busque un atributo, segmento o destino por nombre o ID.
3. From the folder list, drag and drop the traits, segments, or destinations you want to report to the [!UICONTROL Selections] panel on the right side.
4. Genere el informe para que se muestre en una tabla exportable.

## Run a General Report {#run-general-report}

This section describes how to run a [!UICONTROL General] report and set time and other performance options.

<!-- 

t_run_general_report.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL General Reports]**.
1. From the **[!UICONTROL Report Type]** drop-down list, select the desired type: Trait, Segment, or Destination.
1. *Condicional Haga clic en* el cuadro de fecha para mostrar un calendario y, a continuación, seleccione la fecha final del informe si desea especificar una fecha distinta a hoy.
1. Busque un atributo, segmento o destino por nombre o ID.
1. From the folder list, drag and drop the traits, segments, or destinations you want to report to the [!UICONTROL Selections] panel on the right side.
1. Haga clic en **[!UICONTROL Run Report]**.

   Los resultados se muestran en una tabla exportable. Haga clic en los encabezados de columna para ordenar los resultados en orden ascendente o descendente.
1. Select the desired option button at the top of the report to filter data by performance ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], or [!UICONTROL Total Trait Population]) or by time (1, 7, 14, 30, 60, 90-day range or lifetime).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] solo se [!UICONTROL Rule-based Traits] calculan para.

1. *Clic opcional***[!UICONTROL Export to CSV]**. This exports the [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], and [!UICONTROL Total Trait Population] for all day ranges.

## General Reports Results Explained {#general-reports-explained}

The numbers in the [!UICONTROL General Reports] are generated directly from our [!UICONTROL User Profile Store]. The results reflect the number of users that [!DNL Audience Manager] contained in the backend at the time these reporting numbers were generated.

* Estos números no incluyen ID de visitante con tráfico excesivo. El tráfico de bots se filtra antes de alcanzar nuestro sistema de backend. Además, el tráfico de bots se descarta durante un trabajo de limpieza semanal ejecutado en el back-end.
* If you onboard data via inbound processing keyed off the [!DNL Audience Manager] UUID, and these IDs include users that are no longer active in our system, these inactive [!DNL Audience Manager] UUIDs never reach the [!UICONTROL User Profile Store] and are not reported.
* [!UICONTROL Total Trait Realizations] solo se [!UICONTROL Rule-based Traits] calculan para.

## General Reports Results for Traits {#general-report-results-traits}

The metrics below are available when you run a General report and select **[!UICONTROL Trait]** as the report type:

**Realización de características únicas**

This metric represents the unique number of [Audience Manager Unique User IDs (UUID)](../reference/ids-in-aam.md) that qualified for the trait in your selected time range. Por ejemplo, si un usuario visitó la página principal tres veces el 1 de marzo, vería una realización única de características.

**Realización total de características**

Esta métrica representa la cantidad total de características que se activan para la característica en el intervalo de tiempo seleccionado. Por ejemplo, si un usuario visitó su página principal, navegó a sus noticias técnicas y a las secciones de noticias deportivas, aparecerían en el informe general como tres características de características totales y una realización única de características.

**Población total de características**

Esta métrica representa la cantidad total de UUID de Audience Manager que están actualmente cualificados para la característica. Utilice este número para comprender la cantidad total de usuarios que puede utilizar para segmentación y segmentación. Typically, users remain part of a trait for [120 days](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). Por ejemplo, un usuario que visite la página principal tres veces hoy y que nunca vuelva después, permanecerá como usuario de esta población todos los días hasta que transcurran 120 días desde ahora. En la marca de 120 días, se eliminarían de la población. Read our [Trait Qualification Reference](../features/traits/trait-qualification-reference.md) for more examples on the difference between Unique Trait Realizations and Total Trait Population.

La siguiente ilustración muestra los resultados de ejecutar un informe general para el tipo de informe Características.

![](assets/general_reports_metrics.png)

## General Reports Results for Segments {#general-report-results-segments}

The metrics below are available when you run a General report and select **[!UICONTROL Segment]** as the report type:

**Población de segmentos en tiempo real**

Esta métrica representa la cantidad real de visitantes únicos que se vieron en tiempo real durante el intervalo de tiempo especificado y que fueron calificados para el segmento en el momento en que fueron vistos por Audience Manager.

**Población total de segmentos**

Esta métrica representa el número total de UUID de Audience Manager que están cualificados para el segmento dentro del período de retroceso seleccionado. La población de segmentos totales de 1 día representa la base de usuarios más precisa para la segmentación.

>[!NOTE]
>
>Select **[!UICONTROL Include Destination Mappings]** to see a breakdown of segment population for activated destinations.

La siguiente ilustración muestra los resultados de ejecutar un informe general para el tipo de informe Segmento.

![](assets/general_reports_segment_metrics.png)

## General Reports Results for Destinations {#general-report-results-destinations}

The metrics below are available when you run a General report and select **[!UICONTROL Destination]** as the report type:

**Población de segmentos en tiempo real**

Esta métrica representa la cantidad real de visitantes únicos que se vieron en tiempo real durante el intervalo de tiempo especificado y que fueron calificados para el segmento en el momento en que fueron vistos por Audience Manager.

**Población total de segmentos**

Esta métrica representa el número total de UUID de Audience Manager que pertenecen a un segmento dentro del período de retroceso, que se enviaron a un destino.

La siguiente ilustración muestra los resultados de ejecutar un informe general para el tipo de informe Destinos.

![](assets/general_reports_destinations.png)
