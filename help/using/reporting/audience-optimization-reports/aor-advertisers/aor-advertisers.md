---
description: Audience Optimization para anunciantes puede ayudarle a identificar posibles oportunidades de rendimiento para segmentos de Audience Manager en sus campañas de medios de pago. Estos informes combinan datos de rendimiento de campañas a nivel de registro con métricas de segmentos de Audience Manager para informar optimizaciones centradas en segmentos y una combinación de canales eficaz.
seo-description: Audience Optimization para anunciantes puede ayudarle a identificar posibles oportunidades de rendimiento para segmentos de Audience Manager en sus campañas de medios de pago. Estos informes combinan datos de rendimiento de campañas a nivel de registro con métricas de segmentos de Audience Manager para informar optimizaciones centradas en segmentos y una combinación de canales eficaz.
seo-title: Optimización de Audiencias para anunciantes
solution: Audience Manager
title: Optimización de Audiencias para anunciantes
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization Reports
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 3%

---

# [!UICONTROL Audience Optimization] para anunciantes{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] para anunciantes puede ayudarle a identificar posibles oportunidades de rendimiento para segmentos de Audience Manager en sus campañas de medios de pago. Estos informes combinan datos de rendimiento de campañas a nivel de registro con métricas de Audience Manager [!UICONTROL segment] para informar optimizaciones centradas en segmentos y una combinación de canales eficaz.

## Métodos de ingesta de datos {#data-ingestion-methods}

Puede enviar datos a [!DNL Audience Manager] para usarlos en estos informes mediante cualquiera de estos métodos. A veces, los clientes envían datos mediante ambos métodos. Esto ayuda a garantizar que los informes contengan la información más completa y precisa sobre un visitante. Para utilizar los informes [!UICONTROL Audience Optimization] , las llamadas de evento deben incluir *all* de los parámetros enumerados en la documentación [Información general y asignaciones para archivos de metadatos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) . Puede enviar datos a través de los siguientes métodos enumerados a continuación.

* Pixel llama: Para pasar los parámetros de metadatos requeridos a [!DNL Audience Manager], consulte [Capturing Campaign Click Data via Pixel Calls](../../../integration/media-data-integration/click-data-pixels.md) y [Capturing Campaign Impression Data via Pixel Calls](../../../integration/media-data-integration/impression-data-pixels.md).

* Archivos de datos: Si desea utilizar estos informes para analizar sus propios datos o datos desde un origen que no esté integrado con [!DNL Audience Manager], debe crear y cargar archivos de datos y metadatos para esos datos. Para obtener más información, consulte [Archivos de datos para informes de Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) y [Archivos de datos y metadatos para informes de Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC)  {#rbac}

El tipo de informes que puede ver depende del grupo [!UICONTROL RBAC] al que esté asignado. Consulte [Administración](../../../features/administration/administration-overview.md) y [Crear un grupo](../../../features/administration/administration-overview.md#create-group) para obtener más información.

[!UICONTROL RBAC] Los grupos deben tener algunas fuentes de datos configuradas para poder ver los  [!UICONTROL Audience Optimization] informes. Su [!DNL Audience Manager] consultor configurará estos [!UICONTROL data sources] para usted. Cuantos más [!UICONTROL data sources] haya en cada grupo de usuarios [!UICONTROL RBAC], más datos tendrán acceso a esos miembros del grupo. Como mínimo, su consultor configurará al menos una de estas [!UICONTROL data sources]:

* Anunciante [!UICONTROL data source ]
* Marca [!UICONTROL data source]
* Plataforma [!UICONTROL data source]

Los usuarios que pertenecen a más de un grupo de usuarios [!UICONTROL RBAC] pueden cambiar entre la vista de cada grupo. Los datos mostrados se actualizarán para respetar el grupo seleccionado. Si su empresa no utiliza [!UICONTROL RBAC], todos los usuarios tendrán privilegios de administrador y acceso a todos los [!UICONTROL data sources] (grupos de conversión).

## Grupos de conversión {#conversion-groups}

En los informes [!UICONTROL Audience Optimization], **[!UICONTROL Conversion Groups]** son sinónimos de [!UICONTROL data sources] que contienen al menos un rasgo de conversión. [!UICONTROL Data sources] que no contienen al menos un rasgo de conversión no aparecen en los  [!UICONTROL Audience Optimization] informes. Puede ver los rasgos de conversión de los grupos de conversión en el informe [Rasgos de conversión registrados](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md).
