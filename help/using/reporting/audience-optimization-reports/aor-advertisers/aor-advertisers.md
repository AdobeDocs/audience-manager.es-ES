---
description: Audience Optimization para anunciantes puede ayudarle a identificar posibles oportunidades de rendimiento para Audience Manager segmentos en sus campañas de medios de pago. Estos informes combinan datos de rendimiento de la campaña a nivel de registro con métricas de segmento de Audience Manager para informar optimizaciones centradas en el segmento y una combinación de canal efectiva.
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

[!UICONTROL Audience Optimization] para anunciantes puede ayudarle a identificar posibles oportunidades de rendimiento para segmentos de Audience Manager en sus campañas de medios de pago. Estos informes combinan datos de rendimiento de la campaña a nivel de registro con métricas Audience Manager [!UICONTROL segment] para informar optimizaciones centradas en el segmento y una combinación de canal efectiva.

## Métodos de incorporación de datos {#data-ingestion-methods}

Puede enviar datos [!DNL Audience Manager] a para que se utilicen en estos informes mediante cualquiera de estos métodos. En ocasiones, los clientes envían datos por ambos métodos. Esto ayuda a garantizar que sus informes contengan la información más completa y precisa sobre un visitante. Para usar los informes, las [!UICONTROL Audience Optimization] llamadas de evento deben incluir *todos los* parámetros enumerados en la [documentación del Archivos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) Información general y asignaciones para metadatos. Puede enviar datos a través de los siguientes métodos enumerados a continuación.

* Llamadas de píxeles: para pasar los parámetros de metadatos necesarios para [!DNL Audience Manager] ver [Captura de datos de clics en Campaign a través de llamadas de píxeles](../../../integration/media-data-integration/click-data-pixels.md) y [Captura de datos de impresiones de Campaign a través de llamadas de píxeles](../../../integration/media-data-integration/impression-data-pixels.md).

* Archivos de datos: Si desea utilizar estos informes para analizar sus propios datos o datos de un origen que no está integrado con [!DNL Audience Manager], debe crear y cargar datos y metadatos archivos para esos datos. Para obtener más información, vea [Archivos de datos para informes](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) de Audience Optimization y [Archivos de datos y metadatos para informes](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) de Audience Optimization.

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

El tipo de informes que puede vista depende del [!UICONTROL RBAC] grupo esté asignado. Consulte [Administración](../../../features/administration/administration-overview.md) y [Crear un grupo](../../../features/administration/administration-overview.md#create-group) para obtener más información.

[!UICONTROL RBAC] Los grupos deben tener configuradas algunas fuentes de datos para vista los [!UICONTROL Audience Optimization] informes. El [!DNL Audience Manager] consultor las configurará [!UICONTROL data sources] por usted. Cuantos más [!UICONTROL data sources] grupo de usuarios cada [!UICONTROL RBAC] , más datos tendrán acceso esos miembros de la grupo. Como mínimo, el consultor configurará al menos una de estas operaciones [!UICONTROL data sources]:

* Anunciante [!UICONTROL data source]
* Marca [!UICONTROL data source]
* Plataforma [!UICONTROL data source]

Los usuarios que pertenezcan a más de un [!UICONTROL RBAC] grupo de usuarios pueden cambiar entre los vista de cada grupo. Los datos mostrados se actualizarán para respetar el grupo seleccionado. Si su compañía no utiliza [!UICONTROL RBAC], todos los usuarios tendrán privilegios de administrador y acceso a todos los [!UICONTROL data sources] grupos (Conversión).

## Grupos de conversión {#conversion-groups}

En los [!UICONTROL Audience Optimization] informes, **[!UICONTROL Conversion Groups]** son sinónimos de [!UICONTROL data sources] que contienen al menos un rasgo Conversión. [!UICONTROL Data sources] que no contengan al menos un rasgo Conversión no aparecen en los [!UICONTROL Audience Optimization] informes. Puede vista las características Conversión para grupos Conversión en el [informe Características](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) de conversión informadas.
