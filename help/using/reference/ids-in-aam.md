---
description: Consulte este documento para obtener la lista completa de Adobe Audience Manager ID.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuuid, uuuid, uuid
seo-description: Refer to this document for the complete list of Adobe Audience Manager IDs.
seo-title: Index of IDs in Audience Manager
solution: Audience Manager
title: Índice de ID en el Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: Reference
exl-id: 1caf3c6a-ebfd-49f1-9ebd-d4604474c070
source-git-commit: e408c118870fb331c40758be8a7e6b38690aeb5f
workflow-type: tm+mt
source-wordcount: '1001'
ht-degree: 2%

---

# Índice de ID en [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## Información general {#overview}

[!DNL Audience Manager] utiliza varios ID para identificar y administrar los datos que le envía. Consulte este artículo para obtener la lista completa de [!DNL Audience Manager] ID, junto con ejemplos de los prefijos con los que debe utilizarlos.

## Prefijo de ID {#prefixing}

Aunque puede hacer referencia a la mayoría de estos ID por sus nombres independientes, la mayoría de ellos están pensados para utilizarse con varios prefijos al pasar datos a través de [!DNL DCS] llamadas. Algunos de estos identificadores los usa [!DNL Audience Manager] sin que se expongan a los usuarios, mientras que otros también están visibles en la interfaz de usuario (IU).

Para comprender los prefijos utilizados en los ejemplos siguientes, consulte [Atributos admitidos para las llamadas a la API de DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## [!DNL Audience Manager] lista de ID {#id-list}

| ID | Nombre y descripción | Uso y ejemplos | Ubicación de interfaz de usuario |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID], también conocido como [!UICONTROL Device ID]. Identificador de dispositivo numérico de 38 dígitos que [!DNL Audience Manager] asocia a cada dispositivo con el que interactúa. Piense en este ID siempre que vea una mención de usuarios únicos en la interfaz de usuario de [!DNL Audience Manager]. El Audience Manager guarda este identificador como [!DNL cookie] en el dominio de terceros `demdex.net`. | En las llamadas [!DNL DCS], `uuid` va precedido del prefijo `d_`. <br>Ejemplo: `d_uuid = 07955261652886032950143702505894272138` | Puede filtrar [!DNL traits] por [!UICONTROL Device ID] al crear [modelos de similitud](../features/algorithmic-models/create-model.md) y [generar segmentos](../features/segments/segment-builder.md). También puede filtrar los resultados por [!UICONTROL Device ID] al ejecutar [Informes generales para características](../reporting/general-reports.md) e [Informes de tendencias para características](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | [!DNL Organization ID]. Este es el identificador que se proporciona a una compañía al registrarse en una cuenta de [!DNL Experience Cloud]. | `5DC5123F5245B1D20A490D46@AdobeOrg` | No visible en la interfaz de usuario [!DNL Audience Manager]. Para saber cómo puede encontrar el [!DNL Organization ID] de su compañía, lea [Buscar el identificador de su organización](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| [!DNL PID] | [!DNL Partner ID]. [!DNL PID] es el identificador de una compañía en [!DNL Audience Manager]. El Audience Manager asocia un(a) [!DNL imsOrgId] a un(a) [!DNL PID]. | `1352` | No visible en la interfaz de usuario [!DNL Audience Manager]. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. El id. [!DNL Experience Cloud] ([!DNL ECID], abreviaturas heredadas [!DNL MID] o [!DNL MCID]) se deriva matemáticamente de su [!DNL Organization ID] y de [!DNL Audience Manager] [!UICONTROL Unique User ID]. Mientras estos identificadores permanezcan constantes, generar el [!DNL ECID] correcto para un usuario específico es simplemente un problema matemático. Con el mismo [!DNL Organization ID] y [!DNL Audience Manager] [!DNL UUID], obtiene el mismo valor de [!DNL ECID] cada vez. Puede obtener más información sobre [!DNL ECID] en la documentación de [Cookies e ID de Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17). | `mid = 08382830887934830189014177072406221371` | No visible en la interfaz de usuario [!DNL Audience Manager]. |
| [!DNL SID] | [!UICONTROL Trait ID]. [!UICONTROL Trait ID] identifica de forma exclusiva a [!DNL traits] en el entorno [!DNL Audience Manager]. | En las llamadas [!DNL DCS], `SID` va precedido del prefijo `d_`. <br>Ejemplo `d_sid=289983`. | Se ha asignado un [!UICONTROL Trait ID] a cada [!DNL trait], y es visible en la interfaz de usuario, en la página [Características](../features/traits/trait-details-page.md). |
| [!DNL SID] | [!UICONTROL Segment ID]. [!UICONTROL Segment ID] identifica de forma exclusiva a [!DNL segments] en el entorno [!DNL Audience Manager]. | En las llamadas [!DNL DCS], `SID` va precedido del prefijo `d_`. <br>Ejemplo `d_sid=4798574`. | Se ha asignado un [!UICONTROL Segment ID] a cada [!DNL segment], y es visible en la interfaz de usuario, en la página [Segmentos](../features/segments/segment-summary-view.md). |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Este identificador identifica de forma exclusiva los segmentos en el entorno [!DNL Audience Manager]. | `741232` | Se ha asignado un(a) [!UICONTROL Legacy Segment ID] a cada segmento, visible en la interfaz de usuario, en la página [Segmentos](../features/segments/segment-summary-view.md). |
| [!DNL destID] | [!UICONTROL Destination ID]. [!UICONTROL Destination ID] identifica de forma exclusiva a [!DNL destinations] en el entorno [!DNL Audience Manager]. Se asigna un ID a cada [!DNL destination] en la interfaz de usuario. | `2523` | Se ha asignado un [!UICONTROL Destination ID] a cada [!DNL destination], y es visible en la interfaz de usuario, en la página [Destinos](../features/destinations/destinations-home.md). |
| [!DNL DPID] | [!UICONTROL Data Source ID] (también denominado [!UICONTROL Data Provider ID]). [!UICONTROL Data Source ID] es un área de nombres para identificadores o [!DNL traits]. Se asigna un ID a cada [!DNL data source] (proveedor de datos) en la interfaz de usuario. | En las llamadas [!DNL DCS], `dpid` va precedido del prefijo `d_`. <br>Ejemplo: `d_dpid=39217`. | Se ha asignado un(a) [!UICONTROL Data Provider ID] a cada [!DNL data source], visible en la interfaz de usuario, en la página [Fuentes de datos](../features/datasources-list-and-settings.md). |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], también conocido como [!DNL CRM ID] o [!UICONTROL Cross-Device ID]. Un ID de terceros. Este es el ID con el cual identifica a los usuarios finales en su propio sistema [!DNL CRM]. Puede sincronizar [!DNL DPUUIDs] con [!DNL Audience Manager] [!DNL UUIDs] y sincronizar [!DNL DPUUIDs] desde los diferentes [!UICONTROL Data Sources] ([!DNL DPIDs]) en el proceso de sincronización de ID. | En [!DNL DCS] llamadas, `dpuuid` está precedido por el prefijo `d_`. <br> Ejemplo `d_dpuuid=2132-3423vn-343fds-3432r`. | Puede filtrar [!DNL traits] por [!UICONTROL Cross-Device ID] al crear [modelos de similitud](../features/algorithmic-models/create-model.md) y [generar segmentos](../features/segments/segment-builder.md). También puede filtrar los resultados por [!UICONTROL Cross-Device ID] al ejecutar [Informes generales para características](../reporting/general-reports.md) e [Informes de tendencias para características](../reporting/trend-reports.md). |
| [!DNL CRM ID] | Ver `DPUUID`. | Ver `DPUUID`. | Ver `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. Los pares clave-valor [!DNL CID] y [!DNL CID_IC] reemplazan a [!DNL DPID] y [!DNL DPUUID]. Proporcionan las mismas funciones que [!DNL DPID] y [!DNL DPUUID], pero son más eficaces porque incluyen el identificador de proveedor de datos y el identificador de usuario (o código de integración) en un único par clave-valor. | En las llamadas de [!DNL DCS], estos identificadores van precedidos del prefijo `d_`. <br>Ejemplo: `d_cid_ic=39217_myIntegrationCode`. | Ver `DPID` y `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Un ID único de cada dispositivo hardware y que se utiliza con propósitos publicitarios. Suele ser proporcionada por el fabricante del dispositivo o sistema operativo del dispositivo. | Ver [ID de dispositivo globales](#global-device-ids). |  |

## [!DNL Global Device IDs] {#global-device-ids}

Los ID de dispositivo globales son ID publicitarios de dispositivo, únicos para cada dispositivo, proporcionados por el fabricante del dispositivo o el sistema operativo. La siguiente tabla explica cuáles son estos ID y cuál es su formato. Para obtener más información acerca de los identificadores de dispositivos globales y cómo usarlos en [!DNL Audience Manager], lea [Fuentes de datos globales](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | Nombre y descripción | Ejemplo |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | Los identificadores de [!DNL Identifier for Advertisers] son identificadores de dispositivos móviles proporcionados por el fabricante del dispositivo. Estos identificadores representan dispositivos que ejecutan el sistema operativo [!DNL iOS]. | El formato consiste estrictamente en 32 dígitos hexadecimales en mayúsculas, mostrados en cinco grupos y separados por guiones, en la forma 8-4-4-4-12, para un total de 36 caracteres.<br> Ejemplo: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | Los [!DNL Google Advertising ID] son identificadores de dispositivo móvil proporcionados por fabricantes de dispositivos Android. Estos identificadores representan dispositivos que ejecutan el sistema operativo [!DNL Android]. | El formato consiste estrictamente en 32 dígitos hexadecimales en minúsculas, mostrados en cinco grupos y separados por guiones, en la forma 8-4-4-4-12, para un total de 36 caracteres. <br>Ejemplo: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] representan [!DNL Roku] dispositivos de transmisión. | El formato consiste estrictamente en 32 dígitos hexadecimales en minúsculas, mostrados en cinco grupos y separados por guiones, en la forma 8-4-4-4-12, para un total de 36 caracteres. <br>Ejemplo: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID] son identificadores de dispositivo generados por [!DNL Windows 10] por dispositivo y por usuario. | [!DNL MAID]s tienen el formato de cadenas alfanuméricas. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] son identificadores de dispositivo proporcionados por [!DNL Samsung] televisores inteligentes. | [!DNL Samsung] [!DNL TIFA] identificadores tienen el formato de cadenas alfanuméricas. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Identificadores de dispositivo que representan dispositivos que ejecutan el sistema operativo [!DNL Fire OS]. | El formato consiste estrictamente en 32 dígitos hexadecimales en minúsculas, mostrados en cinco grupos y separados por guiones, en la forma 8-4-4-4-12, para un total de 36 caracteres. <br>Ejemplo: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
| [!DNL LGUDID] | 1171485 | Identificadores de dispositivo que representan dispositivos que ejecutan el sistema operativo [!DNL LG webOS]. | El formato consiste estrictamente en 32 dígitos hexadecimales en minúsculas, mostrados en cinco grupos y separados por guiones, en la forma 8-4-4-4-12, para un total de 36 caracteres. <br>Ejemplo: `095f142a-ace8-ac5d-b86a-92c8be18b197` |
| [!DNL Vizio IFA] | 1171489 | Identificadores de dispositivo que representan dispositivos que ejecutan el sistema operativo Vizio Smart TV. | A los identificadores de [!DNL Vizio IFA] se les ha dado formato de cadenas alfanuméricas. <br>Ejemplo: `7XCBNROQJQPYW`. |
