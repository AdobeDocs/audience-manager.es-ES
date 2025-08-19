---
description: Utilice fuentes de datos globales para importar ID de publicidad dispositivos.
seo-description: Use Global Data Sources to import device advertising IDs.
seo-title: Global Data Sources
solution: Audience Manager
title: Fuentes de datos globales
feature: Data Sources
exl-id: ef137f89-1e1a-4cc0-8864-8a84162581c1
source-git-commit: 77daa5bd6545914f65e3e0f19b12c750535244e8
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# Fuentes de datos globales {#global-data-sources}

## Información general

Todos los clientes Audience Manager pueden acceder a las fuentes de datos globales y contienen dispositivos ID de publicidad generados por fabricantes dispositivos, , [!DNL Apple][!DNL Samsung][!DNL Microsoft][!DNL Roku], y [!DNL Android] dispositivos fabricantes. Los fabricantes generan estos ID con fines publicitarios. Audience Manager clientes pueden utilizar fuentes de datos globales para sincronizar ID de dispositivos e importar o exportar datos con claves fuera de esas asignaciones.

En la tabla siguiente se describen los orígenes de datos globales compatibles con Audience Manager.

| ID de Origen datos | Descripción |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** - **[!DNL GAID]** Los ID representan dispositivos que ejecutan el [!DNL Android] sistema operativo. |
| 20915 | **[!DNL Apple ID For Advertising]** - **[!DNL IDFA]** Los ID representan dispositivos que ejecutan el [!DNL iOS] sistema operativo. |
| 121963 | **[!DNL Roku ID for Advertising]** - **[!DNL RIDA]** Los ID representan [!DNL Roku] el flujo continuo dispositivos. |
| 389146 | **[!DNL Microsoft Advertising ID]** - **[!DNL MAID]** Los ID representan dispositivos que ejecutan el [!DNL Windows 10] sistema operativo. |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** - **[!DNL TIFA]** Las identificaciones representan [!DNL Samsung] televisores inteligentes. |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** representar dispositivos en ejecución [!DNL Amazon Fire OS] |
| 1171485 | **[!DNL LG webOS TV ID]** - **[!DNL LGUDID]** representan dispositivos que ejecutan el [!DNL LG webOS] sistema operativo. |
| 1171489 | **[!DNL Vizio ID for Advertising]** - **[!DNL IFA]** representan dispositivos que ejecutan los sistemas operativos de TV inteligente Vizio. |

## Importación de datos desde fuentes de datos globales

Puede importar ID de dispositivos desde orígenes de datos globales mediante [transferencia](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) de datos en tiempo real y [transferencia](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) de datos por lotes.

>[!IMPORTANT]
>
>Cuando envíe datos a Audience Manager utilizando un ID de dispositivos global, asegúrese de utilizar el fuente de datos correspondiente para el ID de dispositivos en cuestión. Ejemplo: para importar datos para [!DNL Apple IDFA], utilice el ID de fuente de datos 20915.

## Limitaciones

En dispositivos sistemas operativos y [!DNL iOS] en ejecución[!DNL Android], solo las aplicaciones nativa pueden recuperar y utilizar dispositivos ID de[!UICONTROL DAID] publicidad. Las aplicaciones web que se ejecutan en navegadores móviles no tienen acceso a dispositivos ID de publicidad.

## Validación de ID de dispositivo global

Audience Manager valida los ID de publicidad dispositivos[!UICONTROL DAID] () importados por los clientes, en función de sus formato, para garantizar que coincidan con los formato estándar descritos por dispositivos fabricantes. Consulte [Index de ID en Audience Manager](../reference/ids-in-aam.md) para obtener una asignación detallada de dispositivos ID de publicidad a las fuentes de datos globales y la formato adecuada para cada ID. Asegúrese de que está importando dispositivos ID en la formato correcta, según el tipo de dispositivo. Audience Manager rechaza dispositivos ID que no cumplen la formato adecuada y devuelve un mensaje de error para indicar que el ID se rechazó.

* Error mensajería para transferencias de datos por lotes se describe aquí: [Términos y definiciones](../reporting/onboarding-status-report.md#report-terms-conditions) de los informes de integración Estado.
* Error mensajería para transferencias de datos en tiempo real se describe aquí: [Códigos Error DCS, mensajes y ejemplos](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

## Política de caducidad del ID de dispositivo

Audience Manager descarta automáticamente los ID de publicidad dispositivos después de 120 días de inactividad, del mismo modo que los [UUID](../faq/faq-privacy.md)de AAM.

## Solicitud Nuevo fuentes de datos globales

Para solicitud nuevas fuentes de datos globales que añadir a Audience Manager, póngase en contacto con Adobe Systems Consulting o Adobe Systems Customer Care y proporcione información detallada sobre las fuentes de datos necesarias:

* El nombre de la plataforma solicitada (por ejemplo, [!UICONTROL Apple IDFA]);
* El nombre de la compañía/organización que administra la plataforma (por ejemplo, [!UICONTROL Apple Inc.]);
* Enlaces a las especificaciones técnicas del espacio de nombres de ID de publicidad dispositivos (por ejemplo, [AdSupport Documentación](https://developer.apple.com/documentation/adsupport)).
