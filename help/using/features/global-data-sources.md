---
description: Utilice las fuentes de datos globales para importar los ID publicitarios de dispositivo.
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

Todos los clientes de Audience Manager pueden acceder a las fuentes de datos globales y contienen identificadores publicitarios de dispositivo generados por fabricantes de dispositivos como [!DNL Apple], [!DNL Samsung], [!DNL Microsoft], [!DNL Roku] y [!DNL Android]. Los fabricantes generan estos ID con fines publicitarios. Los clientes de Audience Manager pueden utilizar fuentes de datos globales para sincronizar los ID de dispositivo e importar o exportar datos desactivados de esas asignaciones.

En la tabla siguiente se describen las fuentes de datos globales que admite Audience Manager.

| ID de Data Source | Descripción |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** - **[!DNL GAID]** ID representan dispositivos que ejecutan el sistema operativo [!DNL Android]. |
| 20915 | **[!DNL Apple ID For Advertising]** - **[!DNL IDFA]** ID representan dispositivos que ejecutan el sistema operativo [!DNL iOS]. |
| 121963 | **[!DNL Roku ID for Advertising]** - **[!DNL RIDA]** ID representan [!DNL Roku] dispositivos de transmisión. |
| 389146 | **[!DNL Microsoft Advertising ID]** - **[!DNL MAID]** ID representan dispositivos que ejecutan el sistema operativo [!DNL Windows 10]. |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** - **[!DNL TIFA]** ID representan [!DNL Samsung] televisores inteligentes. |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** representan dispositivos que ejecutan [!DNL Amazon Fire OS] |
| 1171485 | **[!DNL LG webOS TV ID]** - **[!DNL LGUDID]** representan dispositivos que ejecutan el sistema operativo [!DNL LG webOS]. |
| 1171489 | **[!DNL Vizio ID for Advertising]** - **[!DNL IFA]** representan dispositivos que ejecutan sistemas operativos Vizio Smart TV. |

## Importación de datos desde orígenes de datos globales

Puede importar ID de dispositivo desde fuentes de datos globales mediante [transferencia de datos en tiempo real](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) y [transferencia de datos por lotes](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md).

>[!IMPORTANT]
>
>Al enviar datos al Audience Manager mediante un ID de dispositivo global, asegúrese de utilizar la fuente de datos correspondiente para el ID de dispositivo en cuestión. Ejemplo: para importar datos de [!DNL Apple IDFA], use el 20915 de ID de origen de datos.

## Limitaciones

En dispositivos que ejecutan los sistemas operativos [!DNL iOS] y [!DNL Android], solo las aplicaciones nativas pueden recuperar y utilizar los identificadores publicitarios de dispositivo ([!UICONTROL DAID]s). Las aplicaciones web que se ejecutan en exploradores móviles no tienen acceso a los ID publicitarios de dispositivo.

## Validación de ID de dispositivo global

Audience Manager valida los identificadores publicitarios de dispositivo ([!UICONTROL DAID]) importados por los clientes según su formato para asegurarse de que coinciden con el formato estándar de los fabricantes de dispositivos. Consulte [Índice de ID en Audience Manager](../reference/ids-in-aam.md) para obtener una asignación detallada de los ID publicitarios de dispositivo a las fuentes de datos globales y el formato adecuado para cada ID. Asegúrese de importar los ID de dispositivo en el formato correcto, según el tipo de dispositivo. El Audience Manager rechaza los ID de dispositivo que no tienen el formato adecuado y devuelve un mensaje de error para indicar que el ID se ha rechazado.

* Los mensajes de error para las transferencias de datos por lotes se describen aquí: [Términos y definiciones del informe de estado de carga](../reporting/onboarding-status-report.md#report-terms-conditions).
* Los mensajes de error para transferencias de datos en tiempo real se describen aquí: [Códigos de error DCS, mensajes y ejemplos](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

## Política de caducidad del ID del dispositivo

El Audience Manager AAM descarta automáticamente los ID de publicidad de dispositivos tras 120 días de inactividad, de forma similar a [UUID](../faq/faq-privacy.md)s de la.

## Solicitud de nuevas fuentes de datos globales

Para solicitar que se añadan nuevas fuentes de datos globales al Audience Manager, póngase en contacto con Adobe Consulting o con el Servicio de atención al cliente de Adobe y proporcione información detallada sobre las fuentes de datos necesarias:

* El nombre de la plataforma solicitada (por ejemplo, [!UICONTROL Apple IDFA]);
* El nombre de la empresa u organización que administra la plataforma (por ejemplo, [!UICONTROL Apple Inc.]);
* Vínculos a las especificaciones técnicas del área de nombres del ID de publicidad del dispositivo (por ejemplo, [Documentación de AdSupport](https://developer.apple.com/documentation/adsupport)).
