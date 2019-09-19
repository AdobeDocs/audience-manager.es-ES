---
description: La optimización de audiencia para anunciantes puede ayudarle a identificar oportunidades de rendimiento potenciales para segmentos de Audience Manager en las campañas de medios de pago. Estos informes combinan datos de rendimiento de campañas de nivel de registro con métricas de segmentos de Audience Manager para informar optimizaciones centradas en segmentos y una combinación de canales eficaz.
seo-description: La optimización de audiencia para anunciantes puede ayudarle a identificar oportunidades de rendimiento potenciales para segmentos de Audience Manager en las campañas de medios de pago. Estos informes combinan datos de rendimiento de campañas de nivel de registro con métricas de segmentos de Audience Manager para informar optimizaciones centradas en segmentos y una combinación de canales eficaz.
seo-title: Optimización de audiencias para anunciantes
solution: Audience Manager
title: Optimización de audiencias para anunciantes
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Optimization for Advertisers{#audience-optimization-for-advertisers}

La optimización de audiencia para anunciantes puede ayudarle a identificar oportunidades de rendimiento potenciales para segmentos de Audience Manager en las campañas de medios de pago. Estos informes combinan datos de rendimiento de campañas de nivel de registro con métricas de segmentos de Audience Manager para informar optimizaciones centradas en segmentos y una combinación de canales eficaz.

## Métodos de inserción de datos {#data-ingestion-methods}

Puede enviar datos a para utilizarlos [!DNL Audience Manager] en estos informes mediante cualquiera de estos métodos. A veces, los clientes envían datos por ambos métodos. Esto ayuda a garantizar que los informes contengan la información más completa y precisa sobre un visitante. Para utilizar los [!UICONTROL Audience Optimization] informes, las llamadas de evento deben incluir *todos* los parámetros enumerados en la documentación de [Información general y Asignaciones para archivos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) de metadatos. Puede enviar datos a través de los siguientes métodos.

* Pixel llama: Para pasar los parámetros de metadatos necesarios para [!DNL Audience Manager] ver [Captura de datos de clics de campaña mediante llamadas](../../../integration/media-data-integration/click-data-pixels.md) de píxel y [Captura de datos de impresión de campaña mediante llamadas](../../../integration/media-data-integration/impression-data-pixels.md)de píxel.

* Archivos de datos: Si desea utilizar estos informes para analizar sus propios datos o datos desde un origen que no esté integrado con [!DNL Audience Manager], debe crear y cargar archivos de datos y metadatos para esos datos. Para obtener más información, consulte Archivos [de datos para informes](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) de optimización de audiencia y Archivos [de datos y metadatos para informes](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)de optimización de audiencia.

## Controles de acceso basados en roles (RBAC) {#rbac}

El tipo de informes que puede ver depende del [!UICONTROL RBAC] grupo al que esté asignado. Consulte [Administración](../../../features/administration/administration-overview.md) y [Creación de un grupo](../../../features/administration/administration-overview.md#create-group) para obtener más información.

[!UICONTROL RBAC] los grupos deben tener algunas fuentes de datos configuradas para poder ver los [!UICONTROL Audience Optimization] informes. Su [!DNL Audience Manager] consultor configurará estas fuentes de datos para usted. Cuantos más orígenes de datos haya en cada grupo [!UICONTROL RBAC] de usuarios, más datos tendrán acceso dichos miembros del grupo. Como mínimo, su consultor configurará al menos una de estas fuentes de datos:

* Fuente de datos del anunciante
* Fuente de datos de marca
* Origen de datos de plataforma

Los usuarios que pertenecen a más de un grupo [!UICONTROL RBAC] de usuarios pueden cambiar entre la vista de cada grupo. Los datos mostrados se actualizarán para respetar el grupo seleccionado. Si su empresa no utiliza [!UICONTROL RBAC], todos los usuarios tendrán privilegios de administrador y acceso a todas las fuentes de datos (grupos de conversión).

## Grupos de conversión {#conversion-groups}

En los [!UICONTROL Audience Optimization] informes, **[!UICONTROL Conversion Groups]** son sinónimos de las fuentes de datos que contienen al menos una característica de conversión. Las fuentes de datos que no contienen al menos una característica de conversión no aparecen en los [!UICONTROL Audience Optimization] informes. Puede ver las características de conversión de los grupos de conversión en el informe Características de conversión [informadas](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) .
