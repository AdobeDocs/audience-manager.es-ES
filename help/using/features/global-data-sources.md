---
description: Utilice las fuentes de datos globales para importar los ID de publicidad de dispositivos.
seo-description: Utilice las fuentes de datos globales para importar los ID de publicidad de dispositivos.
seo-title: Fuentes de datos globales
solution: Audience Manager
title: Fuentes de datos globales
feature: Data Sources
translation-type: tm+mt
source-git-commit: cb84f95d52c2e851cb0c016cb25f408f2d79d01b
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 6%

---


# Fuentes de datos globales {#global-data-sources}

## Información general

Todos los clientes Audience Manager pueden acceder a las fuentes de datos globales y contienen ID de publicidad de dispositivos generados por fabricantes de dispositivos como [!DNL Apple], [!DNL Samsung], [!DNL Microsoft], [!DNL Roku] y [!DNL Android] fabricantes de dispositivos. Los fabricantes generan estos ID con fines publicitarios. Los clientes Audience Manager pueden utilizar fuentes de datos globales para sincronizar los ID de dispositivos e importar o exportar datos bloqueados de dichas asignaciones.

En la tabla siguiente se describen las fuentes de datos globales admitidas por Audience Manager.

| ID de fuente de datos | Descripción |
|---|---|
| 2014 | **[!DNL Google Advertising ID]** -  **[!DNL GAID]** Los ID representan dispositivos que ejecutan el sistema  [!DNL Android] operativo. |
| 2015 | **[!DNL Apple ID For Advertising]** -  **[!DNL IDFA]** Los ID representan dispositivos que ejecutan el sistema  [!DNL iOS] operativo. |
| 121963 | **[!DNL Roku ID for Advertising]** -  **[!DNL RIDA]** Los ID representan dispositivos  [!DNL Roku] de flujo continuo. |
| 389146 | **[!DNL Microsoft Advertising ID]** -  **[!DNL MAID]** Los ID representan dispositivos que ejecutan el sistema  [!DNL Windows 10] operativo. |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** -  **[!DNL TIFA]** Los ID representan televisores  [!DNL Samsung] inteligentes. |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** representan dispositivos que se ejecutan  [!DNL Amazon Fire OS] |

## Importación de datos desde fuentes de datos globales

Puede importar ID de dispositivos desde orígenes de datos globales a través de [transferencia de datos en tiempo real](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) y [transferencia de datos por lotes](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md).

>[!IMPORTANT]
>
>Al enviar datos al Audience Manager mediante un ID de dispositivo global, asegúrese de utilizar el origen de datos correspondiente para el ID de dispositivo en cuestión. Ejemplo: para importar datos para [!DNL Apple IDFA], utilice el ID de fuente de datos 2015.

## Limitaciones

En dispositivos que ejecutan sistemas operativos [!DNL iOS] y [!DNL Android], solo las aplicaciones nativas pueden recuperar y utilizar ID de publicidad de dispositivos ([!UICONTROL DAID]s). Las aplicaciones web que se ejecutan en exploradores móviles no tienen acceso a los ID de publicidad de dispositivos.

## Validación global de ID de dispositivo

El Audience Manager valida los ID de publicidad de dispositivo ([!UICONTROL DAID]) importados por los clientes, según su formato, para asegurarse de que coinciden con el formato estándar descrito por los fabricantes de dispositivos. Consulte [Índice de ID en Audience Manager](../reference/ids-in-aam.md) para obtener una asignación detallada de los ID de publicidad de dispositivo a las fuentes de datos globales y el formato adecuado para cada ID. Asegúrese de que está importando los ID de dispositivo en el formato correcto, según el tipo de dispositivo. El Audience Manager rechaza los ID de dispositivo que no cumplen el formato adecuado y devuelve un mensaje de error para indicar que el ID se ha rechazado.

* Los mensajes de error para las transferencias de datos por lotes se describen a continuación: [Términos y definiciones del informe de estado de integración](../reporting/onboarding-status-report.md#report-terms-conditions).
* Los mensajes de error para las transferencias de datos en tiempo real se describen a continuación: [Códigos de error, mensajes y ejemplos de DCS](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

## Directiva de caducidad de ID de dispositivo

El Audience Manager descarta automáticamente los ID de publicidad de dispositivos después de 120 días de inactividad, de forma similar a [AAM UUID](../faq/faq-privacy.md)s.

## Solicitud de nuevas fuentes de datos globales

Para solicitar que se agreguen nuevas fuentes de datos globales al Audience Manager, póngase en contacto con el servicio de consultoría de Adobe o con el servicio de atención al cliente de Adobe y proporcione información detallada sobre las fuentes de datos requeridas:

* El nombre de la plataforma solicitada (por ejemplo, [!UICONTROL Apple IDFA]);
* Nombre de la compañía/organización que administra la plataforma (por ejemplo: [!UICONTROL Apple Inc.]);
* Vínculos a las especificaciones técnicas para la Área de nombres de ID de publicidad de dispositivos (por ejemplo: [Documentación de AdSupport](https://developer.apple.com/documentation/adsupport)).