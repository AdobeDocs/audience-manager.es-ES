---
description: Optimización de audiencias para anunciantes puede ayudarle a identificar oportunidades de rendimiento potenciales para segmentos de Audience Manager en sus campañas de medios de pago. Estos informes combinan datos de rendimiento de campaña de nivel de registro con métricas de segmentos de Audience Manager para informar optimizaciones centradas en segmentos y una mezcla de canal eficaz.
seo-description: Optimización de audiencias para anunciantes puede ayudarle a identificar oportunidades de rendimiento potenciales para segmentos de Audience Manager en sus campañas de medios de pago. Estos informes combinan datos de rendimiento de campaña de nivel de registro con métricas de segmentos de Audience Manager para informar optimizaciones centradas en segmentos y una mezcla de canal eficaz.
seo-title: Optimización de audiencias para anunciantes
solution: Audience Manager
title: Optimización de audiencias para anunciantes
uuid: 852 d 550 e -3 c 7 f -4750-9 abc -365 c 3 a 6 f 7883
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Optimization for Advertisers{#audience-optimization-for-advertisers}

Optimización de audiencias para anunciantes puede ayudarle a identificar oportunidades de rendimiento potenciales para segmentos de Audience Manager en sus campañas de medios de pago. Estos informes combinan datos de rendimiento de campaña de nivel de registro con métricas de segmentos de Audience Manager para informar optimizaciones centradas en segmentos y una mezcla de canal eficaz.

## Data Ingestion Methods {#data-ingestion-methods}

You can send data to [!DNL Audience Manager] for use in these reports by either of these methods. A veces, los clientes envían datos según ambos métodos. Esto ayuda a garantizar que los informes contengan la información más completa y completa acerca de un visitante. To use the [!UICONTROL Audience Optimization] reports, your event calls must include *all* of the parameters listed in the [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) documentation. Puede enviar datos a través de los siguientes métodos enumerados a continuación.

* Pixel calls: To pass the required metadata parameters to [!DNL Audience Manager] see [Capturing Campaign Click Data via Pixel Calls](../../../integration/media-data-integration/click-data-pixels.md) and [Capturing Campaign Impression Data via Pixel Calls](../../../integration/media-data-integration/impression-data-pixels.md).

* Data files: If you want to use these reports to analyze your own data or data from a source that is not integrated with [!DNL Audience Manager], you need to create and upload data and metadata files for that data. For more information, see [Data Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) and [Data and Metadata Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## Role-Based Access Controls (RBAC) {#rbac}

The type of reports you can view depend on the [!UICONTROL RBAC] group you're assigned to. See [Administration](../../../features/administration/administration-overview.md) and [Create a Group](../../../features/administration/administration-overview.md#create-group) for more information.

[!UICONTROL RBAC] los grupos deben tener algunas fuentes de datos configuradas para ver [!UICONTROL Audience Optimization] los informes. Your [!DNL Audience Manager] consultant will set up these data sources for you. The more data sources in each [!UICONTROL RBAC] user group, the more data those group members will have access to. Como mínimo, su asesor configurará al menos una de estas fuentes de datos:

* Fuente de datos del anunciante
* Fuente de datos de marca
* Fuente de datos de plataforma

Users that belong to more than one [!UICONTROL RBAC] user group can switch between each group's view. Los datos mostrados se actualizarán para respetar el grupo seleccionado. If your company does not use [!UICONTROL RBAC], all users will have admin privileges and access to all the data sources (conversion groups).

## Conversion Groups {#conversion-groups}

In the [!UICONTROL Audience Optimization] reports, **[!UICONTROL Conversion Groups]** are synonymous with data sources that contain at least one conversion trait. Data sources which do not contain at least one conversion trait do not appear in the [!UICONTROL Audience Optimization] reports. You can view the conversion traits for conversion groups in the [Reported Conversion Traits](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) report.
