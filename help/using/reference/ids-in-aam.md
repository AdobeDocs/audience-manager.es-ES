---
description: Consulte este documento para obtener la lista completa de Adobe Audience Manager ID.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuuid, uuuid, uuid
seo-description: Refer to this document for the complete list of Adobe Audience Manager IDs.
seo-title: Index of IDs in Audience Manager
solution: Audience Manager
title: Índice de ID en Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: Reference
exl-id: 1caf3c6a-ebfd-49f1-9ebd-d4604474c070
source-git-commit: e408c118870fb331c40758be8a7e6b38690aeb5f
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 5%

---

# Índice de ID en [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## Información general {#overview}

[!DNL Audience Manager] utiliza varios ID para identificar y administrar los datos que le envía. Consulte este artículo para obtener la lista completa de [!DNL Audience Manager] Los ID, junto con ejemplos de los prefijos con los que debe utilizarlos.

## Prefijo de ID {#prefixing}

Aunque puede hacer referencia a la mayoría de estos ID por sus nombres independientes, la mayoría de ellos están pensados para utilizarse con varios prefijos al pasar datos [!DNL DCS] llamadas. Algunos de estos ID los utiliza [!DNL Audience Manager] sin estar expuesto a los usuarios, mientras que otros también están visibles en la interfaz de usuario (IU).

Para conocer los prefijos utilizados en los ejemplos siguientes, consulte [Atributos admitidos para llamadas a la API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## [!DNL Audience Manager] Lista de ID {#id-list}

| ID | Nombre y descripción | Uso y ejemplos | Ubicación de interfaz de usuario |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID], también conocido como [!UICONTROL Device ID]. Un ID de dispositivo numérico de 38 dígitos que [!DNL Audience Manager] se asocia a cada dispositivo con el que interactúa. Piense en este ID siempre que vea una mención de usuarios únicos en la [!DNL Audience Manager] IU. El Audience Manager guarda este ID como [!DNL cookie] en el `demdex.net` Dominio de terceros. | Entrada [!DNL DCS] llamadas, `uuid` va precedido de `d_` prefijo. <br>Ejemplo: `d_uuid = 07955261652886032950143702505894272138` | Puede filtrar [!DNL traits] por [!UICONTROL Device ID] al crear [Modelos de similitud](../features/algorithmic-models/create-model.md), y [creación de segmentos](../features/segments/segment-builder.md). También puede filtrar los resultados por [!UICONTROL Device ID] al ejecutar [Informes generales de características](../reporting/general-reports.md) y [Informes de tendencias para características](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | [!DNL Organization ID]. Este es el ID que se proporciona a una compañía al registrarse en un [!DNL Experience Cloud] cuenta. | `5DC5123F5245B1D20A490D46@AdobeOrg` | No visible en el [!DNL Audience Manager] interfaz de usuario. Para saber cómo puede encontrar los [!DNL Organization ID], lea [Búsqueda del identificador de organización](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| [!DNL PID] | [!DNL Partner ID]. El [!DNL PID] es el ID de una empresa en [!DNL Audience Manager]. El Audience Manager asocia un [!DNL imsOrgId] a un [!DNL PID]. | `1352` | No visible en el [!DNL Audience Manager] interfaz de usuario. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. El [!DNL Experience Cloud] ID ([!DNL ECID], abreviaturas heredadas [!DNL MID] o [!DNL MCID]) se deriva matemáticamente de su [!DNL Organization ID] y el [!DNL Audience Manager] [!UICONTROL Unique User ID]. Siempre que estos ID permanezcan constantes, se generará el [!DNL ECID] para un usuario específico es simplemente un problema matemático. Con el mismo [!DNL Organization ID] y [!DNL Audience Manager] [!DNL UUID] tú obtienes lo mismo [!DNL ECID] valor cada vez. Puede leer más sobre la [!DNL ECID] en el [Cookies e ID de Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) documentación. | `mid = 08382830887934830189014177072406221371` | No visible en el [!DNL Audience Manager] interfaz de usuario. |
| [!DNL SID] | [!UICONTROL Trait ID]. El [!UICONTROL Trait ID] identifica de forma exclusiva [!DNL traits] en el [!DNL Audience Manager] entorno. | Entrada [!DNL DCS] llamadas, `SID` va precedido de `d_` prefijo. <br>Ejemplo `d_sid=289983`. | A [!UICONTROL Trait ID] se asigna a cada [!DNL trait], y visible en la interfaz de usuario, en la [Características](../features/traits/trait-details-page.md) página. |
| [!DNL SID] | [!UICONTROL Segment ID]. El [!UICONTROL Segment ID] identifica de forma exclusiva [!DNL segments] en el [!DNL Audience Manager] entorno. | Entrada [!DNL DCS] llamadas, `SID` va precedido de `d_` prefijo. <br>Ejemplo `d_sid=4798574`. | A [!UICONTROL Segment ID] se asigna a cada [!DNL segment], y visible en la interfaz de usuario, en la [Segmentos](../features/segments/segment-summary-view.md) página. |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Este ID identifica de forma exclusiva los segmentos en la [!DNL Audience Manager] entorno. | `741232` | A [!UICONTROL Legacy Segment ID] está asignado a cada segmento y es visible en la interfaz de usuario, en la variable [Segmentos](../features/segments/segment-summary-view.md) página. |
| [!DNL destID] | [!UICONTROL Destination ID]. El [!UICONTROL Destination ID] identifica de forma exclusiva [!DNL destinations] en el [!DNL Audience Manager] entorno. Se asigna un ID a cada [!DNL destination] en la interfaz de usuario de. | `2523` | A [!UICONTROL Destination ID] se asigna a cada [!DNL destination], y visible en la interfaz de usuario, en la [Destinos](../features/destinations/destinations-home.md) página. |
| [!DNL DPID] | [!UICONTROL Data Source ID] (también denominado [!UICONTROL Data Provider ID]). El [!UICONTROL Data Source ID] es un área de nombres para ID o [!DNL traits]. Se asigna un ID a cada [!DNL data source] (proveedor de datos) en la interfaz de usuario. | Entrada [!DNL DCS] llamadas, `dpid` va precedido de `d_` prefijo. <br>Ejemplo: `d_dpid=39217`. | A [!UICONTROL Data Provider ID] se asigna a cada [!DNL data source], y visible en la interfaz de usuario, en la [Fuentes de datos](../features/datasources-list-and-settings.md) página. |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], también denominado [!DNL CRM ID] o [!UICONTROL Cross-Device ID]. Un ID de terceros. Este es el ID con el que identifica a los usuarios finales por su cuenta [!DNL CRM] sistema. Puede sincronizar [!DNL DPUUIDs] con [!DNL Audience Manager] [!DNL UUIDs] y puede sincronizar [!DNL DPUUIDs] de sus diferentes [!UICONTROL Data Sources] ([!DNL DPIDs]) en el proceso de sincronización de ID. | Entrada [!DNL DCS] llamadas, `dpuuid` va precedido de `d_` prefijo. <br> Ejemplo `d_dpuuid=2132-3423vn-343fds-3432r`. | Puede filtrar [!DNL traits] por [!UICONTROL Cross-Device ID] al crear [Modelos de similitud](../features/algorithmic-models/create-model.md), y [creación de segmentos](../features/segments/segment-builder.md). También puede filtrar los resultados por [!UICONTROL Cross-Device ID] al ejecutar [Informes generales de características](../reporting/general-reports.md) y [Informes de tendencias para características](../reporting/trend-reports.md). |
| [!DNL CRM ID] | Consulte `DPUUID`. | Consulte `DPUUID`. | Consulte `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. El [!DNL CID] y [!DNL CID_IC] pares clave-valor reemplazar [!DNL DPID] y [!DNL DPUUID]. Proporcionan las mismas funciones que el [!DNL DPID] y [!DNL DPUUID], pero son más eficientes porque incluyen el ID del proveedor de datos y el ID de usuario (o código de integración) en un único par clave-valor. | Entrada [!DNL DCS] llamadas de, estos ID van precedidos de la variable `d_` prefijo. <br>Ejemplo: `d_cid_ic=39217_myIntegrationCode`. | Consulte `DPID` y `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Un ID único de cada dispositivo hardware y que se utiliza con propósitos publicitarios. Suele ser proporcionada por el fabricante del dispositivo o sistema operativo del dispositivo. | Consulte [ID de dispositivo globales](#global-device-ids). |  |

## [!DNL Global Device IDs] {#global-device-ids}

Los ID de dispositivo globales son ID publicitarios de dispositivo, únicos para cada dispositivo, proporcionados por el fabricante del dispositivo o el sistema operativo. La siguiente tabla explica cuáles son estos ID y cuál es su formato. Para obtener más información sobre los ID de dispositivo globales y cómo utilizarlos en [!DNL Audience Manager], lea [Fuentes de datos globales](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | Nombre y descripción | Ejemplo |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] Los ID son identificadores de dispositivos móviles proporcionados por el fabricante del dispositivo. Estos ID representan dispositivos que ejecutan el [!DNL iOS] sistema operativo. | El formato consiste estrictamente en 32 dígitos hexadecimales en mayúsculas, mostrados en cinco grupos y separados por guiones, en la forma 8-4-4-4-12, para un total de 36 caracteres.<br> Ejemplo: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]Los son identificadores de dispositivos móviles proporcionados por fabricantes de dispositivos Android. Estos ID representan dispositivos que ejecutan el [!DNL Android] sistema operativo. | El formato consiste estrictamente en 32 dígitos hexadecimales en minúsculas, mostrados en cinco grupos y separados por guiones, en la forma 8-4-4-4-12, para un total de 36 caracteres. <br>Ejemplo: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] representar [!DNL Roku] dispositivos de streaming. | El formato consiste estrictamente en 32 dígitos hexadecimales en minúsculas, mostrados en cinco grupos y separados por guiones, en la forma 8-4-4-4-12, para un total de 36 caracteres. <br>Ejemplo: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]Los son identificadores de dispositivo generados por [!DNL Windows 10] de forma individual para cada dispositivo y cada usuario. | [!DNL MAID]Las cadenas tienen el formato de cadenas alfanuméricas. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] son identificadores de dispositivo proporcionados por [!DNL Samsung] Televisores inteligentes. | [!DNL Samsung] [!DNL TIFA] Los ID tienen el formato de cadenas alfanuméricas. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Identificadores de dispositivo que representan dispositivos que ejecutan el [!DNL Fire OS] sistema operativo. | El formato consiste estrictamente en 32 dígitos hexadecimales en minúsculas, mostrados en cinco grupos y separados por guiones, en la forma 8-4-4-4-12, para un total de 36 caracteres. <br>Ejemplo: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
| [!DNL LGUDID] | 1171485 | Identificadores de dispositivo que representan dispositivos que ejecutan el [!DNL LG webOS] sistema operativo. | El formato consiste estrictamente en 32 dígitos hexadecimales en minúsculas, mostrados en cinco grupos y separados por guiones, en la forma 8-4-4-4-12, para un total de 36 caracteres. <br>Ejemplo: `095f142a-ace8-ac5d-b86a-92c8be18b197` |
| [!DNL Vizio IFA] | 1171489 | Identificadores de dispositivo que representan dispositivos que ejecutan el sistema operativo Vizio Smart TV. | [!DNL Vizio IFA] Los ID tienen el formato de cadenas alfanuméricas. <br>Ejemplo: `7XCBNROQJQPYW`. |
