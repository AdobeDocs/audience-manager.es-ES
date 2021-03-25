---
description: Consulte este documento para obtener la lista completa de Adobe Audience Manager ID.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Consulte este documento para obtener la lista completa de Adobe Audience Manager ID.
seo-title: Índice de ID en Audience Manager
solution: Audience Manager
title: Índice de ID en Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: referencia
translation-type: tm+mt
source-git-commit: 30d18c32f519930703c46046b0c2a413b222c317
workflow-type: tm+mt
source-wordcount: '965'
ht-degree: 5%

---


# Índice de ID en [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## Información general {#overview}

[!DNL Audience Manager] utiliza varios ID para identificar y administrar los datos que se le envían. Consulte este artículo para obtener la lista completa de [!DNL Audience Manager] ID, junto con ejemplos de los prefijos con los que debe utilizarlos.

## Prefijo de ID {#prefixing}

Aunque puede hacer referencia a la mayoría de estos ID por sus nombres independientes, la mayoría de ellos están pensados para utilizarse con varios prefijos, al pasar datos a través de llamadas [!DNL DCS] . Algunos de estos ID los utiliza [!DNL Audience Manager] sin estar expuestos a los usuarios, mientras que otros también están visibles en la interfaz de usuario (IU).

Para comprender los prefijos utilizados en los ejemplos siguientes, consulte [Atributos admitidos para llamadas a la API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## [!DNL Audience Manager] Lista de ID {#id-list}

| ID | Nombre y descripción | Uso y ejemplos | Ubicación de la interfaz de usuario |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID], también conocido como  [!UICONTROL Device ID]. Un ID de dispositivo numérico de 38 dígitos que [!DNL Audience Manager] asocia a cada dispositivo con el que interactúa. Piense en este ID siempre que vea una mención de usuarios únicos en la interfaz de usuario [!DNL Audience Manager] . El Audience Manager guarda este ID como [!DNL cookie] en el dominio de terceros `demdex.net`. | En las llamadas [!DNL DCS], `uuid` va precedido del prefijo `d_`. <br>Ejemplo: `d_uuid = 07955261652886032950143702505894272138` | Puede filtrar [!DNL traits] por [!UICONTROL Device ID] al crear [Modelos de similitud](../features/algorithmic-models/create-model.md) y [segmentos de creación](../features/segments/segment-builder.md). También puede filtrar los resultados por [!UICONTROL Device ID] al ejecutar [Informes generales para características](../reporting/general-reports.md) y [Informes de tendencias para características](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | [!DNL Organization ID]. Este es el ID que se proporciona a una empresa al registrarse en una cuenta [!DNL Experience Cloud]. | `5DC5123F5245B1D20A490D46@AdobeOrg` | No visible en la interfaz de usuario [!DNL Audience Manager]. Para saber cómo puede encontrar el [!DNL Organization ID] de su empresa, lea [Búsqueda del identificador de su organización](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| [!DNL PID] | [!DNL Partner ID]. El [!DNL PID] es el ID de una empresa en [!DNL Audience Manager]. El Audience Manager asocia un [!DNL imsOrgId] a un [!DNL PID]. | `1352` | No visible en la interfaz de usuario [!DNL Audience Manager]. |
| [!DNL ECID],  [!DNL MID] | [!DNL Experience Cloud] ID. El [!DNL Experience Cloud] ID ([!DNL ECID], las abreviaciones heredadas [!DNL MID] o [!DNL MCID]) se deriva matemáticamente de su [!DNL Organization ID] y de la [!DNL Audience Manager] [!UICONTROL Unique User ID]. Mientras estos ID permanezcan constantes, generar el [!DNL ECID] correcto para un usuario específico es simplemente un problema matemático. Con los mismos [!DNL Organization ID] y [!DNL Audience Manager] [!DNL UUID] obtiene el mismo valor [!DNL ECID] cada vez. Puede obtener más información sobre [!DNL ECID] en la documentación de [Cookies e ID de Experience Cloud](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) . | `mid = 08382830887934830189014177072406221371` | No visible en la interfaz de usuario [!DNL Audience Manager]. |
| [!DNL SID] | [!UICONTROL Trait ID]. El [!UICONTROL Trait ID] identifica de forma exclusiva [!DNL traits] en el entorno [!DNL Audience Manager]. | En las llamadas [!DNL DCS], `SID` va precedido del prefijo `d_`. <br>Ejemplo `d_sid=289983`. | Se asigna un [!UICONTROL Trait ID] a cada [!DNL trait] y es visible en la interfaz de usuario, en la página [Características](../features/traits/trait-details-page.md). |
| [!DNL SID] | [!UICONTROL Segment ID]. El [!UICONTROL Segment ID] identifica de forma exclusiva [!DNL segments] en el entorno [!DNL Audience Manager]. | En las llamadas [!DNL DCS], `SID` va precedido del prefijo `d_`. <br>Ejemplo `d_sid=4798574`. | Se asigna un [!UICONTROL Segment ID] a cada [!DNL segment] y es visible en la interfaz de usuario, en la página [Segments](../features/segments/segment-summary-view.md). |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Este ID identifica de forma exclusiva los segmentos del entorno [!DNL Audience Manager] . | `741232` | Se asigna un [!UICONTROL Legacy Segment ID] a cada segmento y se muestra visible en la interfaz de usuario, en la página [Segments](../features/segments/segment-summary-view.md). |
| [!DNL destID] | [!UICONTROL Destination ID]. El [!UICONTROL Destination ID] identifica de forma exclusiva [!DNL destinations] en el entorno [!DNL Audience Manager]. Se asigna un ID a cada [!DNL destination] en la interfaz de usuario. | `2523` | Se asigna un [!UICONTROL Destination ID] a cada [!DNL destination] y es visible en la interfaz de usuario, en la página [Destinations](../features/destinations/destinations-home.md). |
| [!DNL DPID] | [!UICONTROL Data Source ID] (también denominado  [!UICONTROL Data Provider ID]). El [!UICONTROL Data Source ID] es un espacio de nombres para ID o [!DNL traits]. Se asigna un ID a cada [!DNL data source] (proveedor de datos) en la interfaz de usuario. | En las llamadas [!DNL DCS], `dpid` va precedido del prefijo `d_`. <br>Ejemplo: `d_dpid=39217`. | Se asigna un [!UICONTROL Data Provider ID] a cada [!DNL data source] y es visible en la interfaz de usuario, en la página [Fuentes de datos](../features/datasources-list-and-settings.md). |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], también denominado  [!DNL CRM ID] o  [!UICONTROL Cross-Device ID]. Un ID de terceros. Este es el ID mediante el cual se identifican los usuarios finales en su propio sistema [!DNL CRM]. Puede sincronizar [!DNL DPUUIDs] con [!DNL Audience Manager] [!DNL UUIDs] y puede sincronizar [!DNL DPUUIDs] desde los diferentes [!UICONTROL Data Sources] ([!DNL DPIDs]) en el proceso de sincronización de ID. | En las llamadas [!DNL DCS], `dpuuid` va precedido del prefijo `d_`. <br> Ejemplo `d_dpuuid=2132-3423vn-343fds-3432r`. | Puede filtrar [!DNL traits] por [!UICONTROL Cross-Device ID] al crear [Modelos de similitud](../features/algorithmic-models/create-model.md) y [segmentos de creación](../features/segments/segment-builder.md). También puede filtrar los resultados por [!UICONTROL Cross-Device ID] al ejecutar [Informes generales para características](../reporting/general-reports.md) y [Informes de tendencias para características](../reporting/trend-reports.md). |
| [!DNL CRM ID] | Consulte `DPUUID`. | Consulte `DPUUID`. | Consulte `DPUUID`. |
| [!DNL CID],  [!DNL CID_IC] | [!UICONTROL Customer ID],  [!UICONTROL Customer ID Integration Code]. Los pares de clave-valor [!DNL CID] y [!DNL CID_IC] reemplazan a [!DNL DPID] y [!DNL DPUUID]. Proporcionan las mismas funciones que los [!DNL DPID] y [!DNL DPUUID], pero son más eficientes porque incluyen el ID del proveedor de datos y el ID de usuario (o código de integración) en un único par clave-valor. | En las llamadas [!DNL DCS] , estos ID van precedidos del prefijo `d_` . <br>Ejemplo: `d_cid_ic=39217_myIntegrationCode`. | Consulte `DPID` y `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Un ID exclusivo de cada dispositivo hardware y que se utiliza con propósitos publicitarios. Normalmente lo proporciona el fabricante del dispositivo o del sistema operativo del dispositivo. | Consulte [ID de dispositivo globales](#global-device-ids). |  |

## [!DNL Global Device IDs] {#global-device-ids}

Los ID de dispositivo globales son ID publicitarios de dispositivo, exclusivos de cada dispositivo, proporcionados por el fabricante del dispositivo o el sistema operativo. La tabla siguiente explica cuáles son estos ID y cuál es su formato. Para obtener más información sobre los ID de dispositivos globales y cómo utilizarlos en [!DNL Audience Manager], lea [Fuentes de datos globales](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | Nombre y descripción | Ejemplo |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] Los ID son identificadores de dispositivo móvil, proporcionados por el fabricante del dispositivo. Estos ID representan dispositivos que ejecutan el sistema operativo [!DNL iOS]. | El formato consta estrictamente de 32 dígitos hexadecimales en mayúsculas, mostrados en cinco grupos y separados por guiones, en el formulario 8-4-4-4-12, para un total de 36 caracteres.<br> Ejemplo: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]son identificadores de dispositivos móviles proporcionados por fabricantes de dispositivos Android. Estos ID representan dispositivos que ejecutan el sistema operativo [!DNL Android]. | El formato consta estrictamente de 32 dígitos hexadecimales en minúsculas, mostrados en cinco grupos y separados por guiones, en el formulario 8-4-4-4-12, para un total de 36 caracteres. <br>Ejemplo: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] representan dispositivos de  [!DNL Roku] flujo continuo. | El formato consta estrictamente de 32 dígitos hexadecimales en minúsculas, mostrados en cinco grupos y separados por guiones, en el formulario 8-4-4-4-12, para un total de 36 caracteres. <br>Ejemplo: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s son identificadores de dispositivo generados por  [!DNL Windows 10] en cada dispositivo y por usuario. | [!DNL MAID]s tienen formato de cadenas alfanuméricas. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] son identificadores de dispositivo proporcionados por  [!DNL Samsung] Smart TV. | [!DNL Samsung] [!DNL TIFA] Los ID tienen el formato de cadenas alfanuméricas. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Identificadores de dispositivo que representan dispositivos que ejecutan el sistema operativo [!DNL Fire OS]. | El formato consta estrictamente de 32 dígitos hexadecimales en minúsculas, mostrados en cinco grupos y separados por guiones, en el formulario 8-4-4-4-12, para un total de 36 caracteres. <br>Ejemplo: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |