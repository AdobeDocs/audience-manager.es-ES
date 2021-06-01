---
description: Utilice las fuentes de datos globales para importar los ID publicitarios de dispositivo.
seo-description: Utilice las fuentes de datos globales para importar los ID publicitarios de dispositivo.
seo-title: Fuentes de datos globales
solution: Audience Manager
title: Fuentes de datos globales
feature: Fuentes de datos
exl-id: ef137f89-1e1a-4cc0-8864-8a84162581c1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 6%

---

# Fuentes de datos globales {#global-data-sources}

## Información general

Todos los clientes Audience Manager pueden acceder a las fuentes de datos globales y contienen identificadores publicitarios de dispositivo generados por fabricantes de dispositivos como [!DNL Apple], [!DNL Samsung], [!DNL Microsoft], [!DNL Roku] y [!DNL Android]. Los fabricantes generan estos ID con fines publicitarios. Los clientes Audience Manager pueden utilizar fuentes de datos globales para sincronizar los ID de dispositivo e importar o exportar datos desactivados de esas asignaciones.

En la tabla siguiente se describen las fuentes de datos globales admitidas por el Audience Manager.

| ID de fuente de datos | Descripción |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** : los  **[!DNL GAID]** ID representan dispositivos que ejecutan el sistema  [!DNL Android] operativo. |
| 20915 | **[!DNL Apple ID For Advertising]** : los  **[!DNL IDFA]** ID representan dispositivos que ejecutan el sistema  [!DNL iOS] operativo. |
| 121963 | **[!DNL Roku ID for Advertising]** : los  **[!DNL RIDA]** ID representan dispositivos de  [!DNL Roku] flujo continuo. |
| 389146 | **[!DNL Microsoft Advertising ID]** : los  **[!DNL MAID]** ID representan dispositivos que ejecutan el sistema  [!DNL Windows 10] operativo. |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** : los  **[!DNL TIFA]** ID representan televisores  [!DNL Samsung] inteligentes. |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** representan dispositivos en ejecución  [!DNL Amazon Fire OS] |

## Importación de datos desde fuentes de datos globales

Puede importar ID de dispositivo desde fuentes de datos globales a través de [transferencia de datos en tiempo real](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) y [transferencia de datos por lotes](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md).

>[!IMPORTANT]
>
>Al enviar datos al Audience Manager mediante un ID de dispositivo global, asegúrese de utilizar la fuente de datos correspondiente para el ID de dispositivo en cuestión. Ejemplo: para importar datos para [!DNL Apple IDFA], utilice el ID de fuente de datos 2015.

## Limitaciones

En dispositivos que ejecutan sistemas operativos [!DNL iOS] y [!DNL Android], solo las aplicaciones nativas pueden recuperar y utilizar ID publicitarios de dispositivo ([!UICONTROL DAID]s). Las aplicaciones web que se ejecutan en exploradores móviles no tienen acceso a los ID publicitarios de los dispositivos.

## Validación global de ID de dispositivo

El Audience Manager valida los ID publicitarios de dispositivo ([!UICONTROL DAID]) importados por los clientes según su formato para asegurarse de que coinciden con el formato estándar de los fabricantes de dispositivos. Consulte [Índice de ID en Audience Manager](../reference/ids-in-aam.md) para obtener una asignación detallada de los ID publicitarios de dispositivo a las fuentes de datos globales y el formato adecuado para cada ID. Asegúrese de que está importando ID de dispositivo en el formato correcto, según el tipo de dispositivo. El Audience Manager rechaza los ID de dispositivo que no cumplen el formato adecuado y devuelve un mensaje de error para indicar que el ID se ha rechazado.

* Los mensajes de error para transferencias de datos por lotes se describen aquí: [Términos y definiciones del informe de estado de carga](../reporting/onboarding-status-report.md#report-terms-conditions).
* La mensajería de error para transferencias de datos en tiempo real se describe aquí: [Códigos de error DCS, mensajes y ejemplos](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

## Directiva de caducidad del ID del dispositivo

El Audience Manager descarta automáticamente los ID publicitarios de dispositivo después de 120 días de inactividad, de forma similar a [AAM UUID](../faq/faq-privacy.md)s.

## Solicitud de nuevas fuentes de datos globales

Para solicitar que se añadan nuevas fuentes de datos globales al Audience Manager, póngase en contacto con el servicio de consultoría de Adobe o con el servicio de atención al cliente de Adobe y proporcione información detallada sobre las fuentes de datos requeridas:

* El nombre de la plataforma solicitada (por ejemplo, [!UICONTROL Apple IDFA]);
* El nombre de la empresa u organización que administra la plataforma (por ejemplo, [!UICONTROL Apple Inc.]);
* Vínculos a las especificaciones técnicas del espacio de nombres del ID de publicidad del dispositivo (por ejemplo, [Documentación de asistencia técnica](https://developer.apple.com/documentation/adsupport)).
