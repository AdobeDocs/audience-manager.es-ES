---
description: Audience Optimization para anunciantes puede ayudarle a identificar posibles oportunidades de rendimiento para segmentos de Audience Manager en sus campañas de medios de pago. Estos informes combinan datos de rendimiento de campañas en el nivel del registro con métricas de segmentos de Audience Manager para informar optimizaciones centradas en segmentos y una combinación de canales efectiva.
seo-description: Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.
seo-title: Audience Optimization for Advertisers
solution: Audience Manager
title: Audience Optimization para anunciantes
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization Reports
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 0%

---

# [!UICONTROL Audience Optimization] para anunciantes{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] para anunciantes puede ayudarle a identificar posibles oportunidades de rendimiento para segmentos de Audience Manager en sus campañas de medios de pago. Estos informes combinan datos de rendimiento de campañas en el nivel de registro con métricas de Audience Manager [!UICONTROL segment] para informar optimizaciones centradas en segmentos y una combinación de canales efectiva.

## Métodos de ingesta de datos {#data-ingestion-methods}

Puede enviar datos a [!DNL Audience Manager] para su uso en estos informes mediante cualquiera de estos métodos. A veces, los clientes envían datos por ambos métodos. Esto contribuye a garantizar que los informes contengan la información más completa y precisa sobre un visitante. Para usar los informes [!UICONTROL Audience Optimization], las llamadas de evento deben incluir *todos* los parámetros enumerados en la documentación de [Información general y asignaciones para archivos de metadatos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md). Puede enviar datos mediante los métodos siguientes que se enumeran a continuación.

* Llamadas en píxeles: para pasar los parámetros de metadatos requeridos a [!DNL Audience Manager], consulte [Captura de datos de clic de campaña a través de llamadas en píxeles](../../../integration/media-data-integration/click-data-pixels.md) y [Captura de datos de impresión de campaña a través de llamadas en píxeles](../../../integration/media-data-integration/impression-data-pixels.md).

* Archivos de datos: si desea utilizar estos informes para analizar sus propios datos o los datos de un origen que no está integrado con [!DNL Audience Manager], debe crear y cargar los datos y los archivos de metadatos para esos datos. Para obtener más información, vea [Archivos de datos para informes de Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) y [Archivos de datos y metadatos para informes de Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

El tipo de informes que puede ver depende del grupo [!UICONTROL RBAC] al que esté asignado. Consulte [Administración](../../../features/administration/administration-overview.md) y [Crear un grupo](../../../features/administration/administration-overview.md#create-group) para obtener más información.

[!UICONTROL RBAC] grupos deben tener algunas fuentes de datos configuradas para ver los informes de [!UICONTROL Audience Optimization]. Su asesor de [!DNL Audience Manager] configurará estos [!UICONTROL data sources] para usted. Cuantos más [!UICONTROL data sources] haya en cada grupo de usuarios [!UICONTROL RBAC], más datos tendrán acceso esos miembros del grupo. Como mínimo, el consultor configurará al menos uno de estos [!UICONTROL data sources]:

* Anunciante [!UICONTROL data source]
* Marca [!UICONTROL data source]
* Plataforma [!UICONTROL data source]

Los usuarios que pertenecen a más de un grupo de usuarios [!UICONTROL RBAC] pueden cambiar entre las vistas de cada grupo. Los datos mostrados se actualizarán para respetar el grupo seleccionado. Si su compañía no usa [!UICONTROL RBAC], todos los usuarios tendrán privilegios de administrador y acceso a todos los [!UICONTROL data sources] (grupos de conversión).

## Grupos de conversión {#conversion-groups}

En los informes [!UICONTROL Audience Optimization], **[!UICONTROL Conversion Groups]** son sinónimos de [!UICONTROL data sources] que contienen al menos un rasgo de conversión. [!UICONTROL Data sources] que no contienen al menos un rasgo de conversión no aparecen en los informes [!UICONTROL Audience Optimization]. Puede ver las características de conversión de los grupos de conversión en el informe [Características de conversión registradas](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md).
