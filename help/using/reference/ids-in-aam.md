---
description: Consulte este documento para obtener la lista completa de los ID de Adobe Audience Manager.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Consulte este documento para obtener la lista completa de los ID de Adobe Audience Manager.
seo-title: Índice de ID en el Audience Manager
solution: Audience Manager
title: Índice de ID en el Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 3%

---


# Índice de ID en el Audience Manager {#index-of-ids-in-audience-manager}

## Información general {#overview}

[!DNL Audience Manager] utiliza varios ID para identificar y administrar los datos que se le envían. Consulte este artículo para obtener la lista completa de [!DNL Audience Manager] los ID, junto con ejemplos de los prefijos con los que debe utilizarlos.

## Prefijo de ID {#prefixing}

Aunque puede hacer referencia a la mayoría de estos ID por sus nombres independientes, la mayoría de ellos están pensados para utilizarse con varios prefijos al pasar datos a través de [!DNL DCS] llamadas. Algunos de estos ID son utilizados por Audience Manager sin estar expuestos a los usuarios, mientras que otros también son visibles en la interfaz de usuario (IU).

Para comprender los prefijos utilizados en los ejemplos siguientes, consulte Atributos [admitidos para llamadas](../api/dcs-intro/dcs-api-reference/dcs-keys.md)de API de DCS.

## Lista Audience Manager de ID {#id-list}

| ID | Nombre y descripción | Uso y ejemplos | Ubicación de la interfaz de usuario |
|---|---|---|---|
| [!DNL AAM UUID] | ID de usuario único de Adobe Audience Manager, también conocida como [!UICONTROL Device ID]. Un ID de dispositivo numérico de 38 dígitos que [!DNL Audience Manager] se asocia a cada dispositivo con el que interactúa. Piense en este ID cada vez que vea una mención de usuarios únicos en la [!DNL Audience Manager] interfaz de usuario. Audience Manager guarda este ID como una cookie en el dominio de `demdex.net` terceros. | En [!DNL DCS] llamadas, `uuid` va precedido del `d_` prefijo. <br>Ejemplo: `d_uuid = 07955261652886032950143702505894272138` | Puede filtrar características [!UICONTROL Device ID] al crear modelos [](../features/algorithmic-models/create-model.md)parecidos y [generar segmentos](../features/segments/segment-builder.md). También puede filtrar los resultados por [!UICONTROL Device ID] cuando ejecute Informes [generales para características](../reporting/general-reports.md) e Informes de [tendencias para características](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | Identificador de organización. Es el ID con el que se proporciona una compañía al registrarse en una [!DNL Experience Cloud] cuenta. | `5DC5123F5245B1D20A490D46@AdobeOrg` | No visible en la interfaz de usuario del Audience Manager. Para saber cómo puede encontrar la compañía [!DNL Organization ID], lea [Buscar su identificador](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)de organización. |
| [!DNL PID] | ID del socio. El [!DNL PID] es un ID de compañía en [!DNL Audience Manager]. Audience Manager asocia un [!DNL imsOrgId] a un [!DNL PID]. | `1352` | No visible en la interfaz de usuario del Audience Manager. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. El [!DNL Experience Cloud] ID ([!DNL ECID], abreviaturas heredadas [!DNL MID] o [!DNL MCID]) se deriva matemáticamente del ID de organización y del [!DNL Audience Manager] [!UICONTROL Unique User ID]. As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same organization ID and [!DNL Audience Manager] [!DNL UUID] you get the same [!DNL ECID] value every time. Puede obtener más información sobre el [!DNL ECID] en la documentación de [Cookies e ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) de Experience Cloud. | `mid = 08382830887934830189014177072406221371` | No visible en el [!DNL Audience Manager][!DNL UI]. |
| [!DNL SID] | [!UICONTROL Trait ID]. El [!UICONTROL Trait ID] identifica de forma única las características del [!DNL Audience Manager] entorno. | En [!DNL DCS] llamadas, `SID` va precedido del `d_` prefijo. <br>Ejemplo `d_sid=289983`. | En la página [!UICONTROL Trait ID] Características [se asigna un](../features/traits/trait-details-page.md) atributo, visible en la interfaz de usuario. |
| [!DNL SID] | [!UICONTROL Segment ID]. El [!UICONTROL Segment ID] identifica de forma exclusiva los segmentos del [!DNL Audience Manager] entorno. | En [!DNL DCS] llamadas, `SID` va precedido del `d_` prefijo. <br>Ejemplo `d_sid=4798574`. | Se [!UICONTROL Segment ID] asigna un segmento a cada segmento, y se muestra visible en la interfaz de usuario, en la página [Segmentos](../features/segments/segment-summary-view.md) . |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Este ID identifica de forma exclusiva los segmentos del [!DNL Audience Manager] entorno. | `741232` | Se [!UICONTROL Legacy Segment ID] asigna un segmento a cada segmento, y se muestra visible en la interfaz de usuario, en la página [Segmentos](../features/segments/segment-summary-view.md) . |
| [!DNL destID] | [!UICONTROL Destination ID]. Identifica [!UICONTROL Destination ID] de forma exclusiva los destinos del [!DNL Audience Manager] entorno. Se asigna un ID a cada destino en la interfaz de usuario. | `2523` | En la página [!UICONTROL Destination ID] Destinos [se asigna un](../features/destinations/destinations-home.md) valor a cada destino, y se muestra visible en la interfaz de usuario. |
| [!DNL DPID] | [!UICONTROL Data Source ID] (también denominado [!UICONTROL Data Provider ID]). La [!UICONTROL Data Source ID] es una Área de nombres para ID o características. Se asigna un ID a cada origen de datos (proveedor de datos) en la interfaz de usuario. | En [!DNL DCS] llamadas, `dpid` va precedido del `d_` prefijo. <br>Ejemplo: `d_dpid=39217`. | En la página Fuentes [!UICONTROL Data Provider ID] de [datos se asigna un](../features/datasources-list-and-settings.md) objeto a cada fuente de datos y se muestra visible en la interfaz de usuario. |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], también denominado [!DNL CRM ID] o [!UICONTROL Cross-Device ID]. Un ID de terceros. Es el ID mediante el cual se identifican los usuarios finales en su propio [!DNL CRM] sistema. Puede sincronizar [!DNL DPUUIDs] con [!DNL Audience Manager] [!DNL UUIDs] y puede sincronizar [!DNL DPUUIDs] desde sus diferentes [!UICONTROL Data Sources] ([!DNL DPIDs]) usuarios en el proceso de sincronización de ID. | En [!DNL DCS] llamadas, `dpuuid` va precedido del `d_` prefijo. <br> Ejemplo `d_dpuuid=2132-3423vn-343fds-3432r`. | Puede filtrar características [!UICONTROL Cross-Device ID] al crear modelos [](../features/algorithmic-models/create-model.md)parecidos y [generar segmentos](../features/segments/segment-builder.md). También puede filtrar los resultados por [!UICONTROL Cross-Device ID] cuando ejecute Informes [generales para características](../reporting/general-reports.md) e Informes de [tendencias para características](../reporting/trend-reports.md). |
| [!DNL CRM ID] | Consulte `DPUUID`. | Consulte `DPUUID`. | Consulte `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. Los pares [!DNL CID] y [!DNL CID_IC] clave-valor reemplazan [!DNL DPID] y [!DNL DPUUID]. Proporcionan las mismas funciones que [!DNL DPID] y [!DNL DPUUID], pero son más eficientes porque incluyen la ID del proveedor de datos y la ID del usuario (o el código de integración) en un único par clave-valor. | En [!DNL DCS] las llamadas, estos ID van precedidos del `d_` prefijo. <br>Ejemplo: `d_cid_ic=39217_myIntegrationCode`. | Consulte `DPID` y `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Un ID exclusivo de cada dispositivo hardware y que se utiliza con propósitos publicitarios. Normalmente lo proporciona el fabricante del dispositivo o del sistema operativo del dispositivo. | Consulte ID de dispositivos [globales](#global-device-ids). |  |

## ID de dispositivo globales {#global-device-ids}

Los ID de dispositivo globales son ID de publicidad de dispositivo, exclusivos de cada dispositivo, proporcionados por el fabricante del dispositivo o el sistema operativo. La tabla siguiente explica cuáles son estos ID y cuál es su formato. Para obtener más información sobre los ID de dispositivos globales y cómo utilizarlos en [!DNL Audience Manager], consulte Fuentes [de datos](/help/using/features/global-data-sources.md)globales.

| ID | ID de fuente de datos global | Nombre y descripción | Ejemplo |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] Los ID son identificadores de dispositivos móviles, proporcionados por el fabricante del dispositivo. Estos ID representan dispositivos que ejecutan el sistema operativo iOS. | El formato consiste estrictamente en 32 dígitos hexadecimales en mayúsculas, mostrados en cinco grupos y separados por guiones, en el formato 8-4-4-4-12, con un total de 36 caracteres.<br> Ejemplo: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s son identificadores de dispositivos móviles proporcionados por los fabricantes de dispositivos Android. Estos ID representan dispositivos que ejecutan el [!DNL Android] sistema operativo. | El formato consiste estrictamente en 32 dígitos hexadecimales en minúsculas, mostrados en cinco grupos y separados por guiones, en el formato 8-4-4-4-12, para un total de 36 caracteres. <br>Ejemplo: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] representan dispositivos [!DNL Roku] de flujo continuo. | El formato consiste estrictamente en 32 dígitos hexadecimales en minúsculas, mostrados en cinco grupos y separados por guiones, en el formato 8-4-4-4-12, para un total de 36 caracteres. <br>Ejemplo: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s son identificadores de dispositivo generados por [!DNL Windows 10] cada dispositivo por usuario. | [!DNL MAID]s tienen el formato de cadenas alfanuméricas. |
| [!DNL DUID] | 404660 | [!DNL Samsung DUID]Los identificadores de dispositivo son proporcionados por [!DNL Samsung] Smart TV. | [!DNL Samsung] [!DNL DUID]s tienen el formato de cadenas alfanuméricas. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Identificadores de dispositivo que representan dispositivos que ejecutan el [!DNL Fire OS] sistema operativo. | El formato consiste estrictamente en 32 dígitos hexadecimales en minúsculas, mostrados en cinco grupos y separados por guiones, en el formato 8-4-4-4-12, para un total de 36 caracteres. <br>Ejemplo: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |

