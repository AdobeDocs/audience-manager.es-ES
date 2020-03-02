---
description: Consulte este documento para obtener la lista completa de los ID de Adobe Audience Manager.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Consulte este documento para obtener la lista completa de los ID de Adobe Audience Manager.
seo-title: Índice de ID en Audience Manager
solution: Audience Manager
title: Índice de ID en Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: f8916812a31513d3d8401a0598f37dae02a3fd02

---


# Índice de ID en Audience Manager{#index-of-ids-in-audience-manager}

## Información general {#overview}

Audience Manager utiliza varios ID para identificar y administrar los datos que se le envían. Consulte este artículo para obtener la lista completa de los ID de Adobe Audience Manager, junto con ejemplos de los prefijos con los que debe utilizarlos.

## Prefijo de ID {#prefixing}

Aunque puede hacer referencia a la mayoría de estos ID por sus nombres independientes, la mayoría de ellos están pensados para utilizarse con varios prefijos al pasar datos a través de llamadas DCS. Algunos de estos ID son utilizados por Audience Manager sin estar expuestos a los usuarios, mientras que otros también son visibles en la interfaz de usuario.

Para comprender los prefijos utilizados en los ejemplos siguientes, consulte Atributos [admitidos para llamadas](../api/dcs-intro/dcs-api-reference/dcs-keys.md)de API de DCS.

## Lista de ID de Audience Manager {#id-list}

| ID | Nombre y descripción | Uso y ejemplos | Ubicación de la interfaz de usuario |
|---|---|---|---|
| [!DNL AAM UUID] | ID de usuario único de Audience Manager. ID de dispositivo numérico de 38 dígitos que Audience Manager asocia a cada dispositivo con el que interactúa. Considere este ID siempre que vea una mención de usuarios únicos en la interfaz de usuario de Audience Manager. Audience Manager guarda este ID como una cookie en el dominio de `demdex.net` terceros. | En [!DNL DCS] llamadas, `uuid` va precedido del `d_` prefijo. <br>Ejemplo: `d_uuid = 07955261652886032950143702505894272138` | No visible en la interfaz de usuario de Audience Manager. |
| [!DNL ImsOrgId] | Identificador de organización. ID con el que se proporciona a una empresa al registrarse para una cuenta de Experience Cloud. | `5DC5123F5245B1D20A490D46@AdobeOrg` | No visible en la interfaz de usuario de Audience Manager. Para saber cómo puede encontrar el identificador de organización de su empresa, consulte [Buscar el identificador](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)de organización. |
| PID | ID del socio. El PID es un ID de empresa en Audience Manager. Audience Manager asocia un [!DNL imsOrgId] a un [!DNL PID]. | `1352` | No visible en la interfaz de usuario de Audience Manager. |
| [!DNL ECID], [!DNL MID] | ID de Experience Cloud. El ID de Experience Cloud ([!DNL ECID], abreviaturas heredadas [!DNL MID] o [!DNL MCID]) se deriva matemáticamente de su ID de organización y del ID de usuario único de Audience Manager. As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same organization ID and Audience Manager [!DNL UUID] you get the same [!DNL ECID] value every time. Puede obtener más información sobre el ECID en la documentación de [Cookies e ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) de Experience Cloud. | `mid = 08382830887934830189014177072406221371` | No visible en la interfaz de usuario de Audience Manager. |
| [!DNL SID] | ID de característica. El ID de característica identifica de forma exclusiva las características del entorno de Audience Manager. | En [!DNL DCS] llamadas, `SID` va precedido del `d_` prefijo. <br>Ejemplo `d_sid=289983`. | Se asigna un ID de característica a cada característica, visible en la interfaz de usuario, en la página [Características](../features/traits/trait-details-page.md) . |
| [!DNL SID] | ID del segmento. El ID de segmento identifica de forma exclusiva los segmentos en el entorno de Audience Manager. | En [!DNL DCS] llamadas, `SID` va precedido del `d_` prefijo. <br>Ejemplo `d_sid=4798574`. | En la página [Segmentos](../features/segments/segment-summary-view.md) se asigna un ID de segmento a cada segmento, visible en la interfaz de usuario. |
| [!DNL csegID] | ID de segmento heredado. Este ID identifica de forma exclusiva los segmentos en el entorno de Audience Manager. | `741232` | Se asigna un ID de segmento heredado a cada segmento, y se muestra visible en la interfaz de usuario, en la página [Segmentos](../features/segments/segment-summary-view.md) . |
| [!DNL destID] | ID de destino. El ID de destino identifica de forma exclusiva los destinos en el entorno de Audience Manager. Se asigna un ID a cada destino en la interfaz de usuario. | `2523` | En la página [Destinos](../features/destinations/destinations-home.md) se asigna un ID de destino a cada destino, visible en la interfaz de usuario. |
| [!DNL DPID] | ID de fuente de datos (también denominada ID del proveedor de datos). El ID de fuente de datos es un espacio de nombres para ID o características. Se asigna un ID a cada origen de datos (proveedor de datos) en la interfaz de usuario. | En [!DNL DCS] llamadas, `dpid` va precedido del `d_` prefijo. <br>Ejemplo: `d_dpid=39217`. | Se asigna un ID de proveedor de datos a cada fuente de datos y se muestra visible en la interfaz de usuario en la página Fuentes [de](../features/datasources-list-and-settings.md) datos. |
| [!DNL DPUUID] | ID de usuario único del proveedor de datos (también denominado [!DNL CRM ID]). Un ID de terceros. Es el ID mediante el cual se identifican los usuarios finales en su propio [!DNL CRM] sistema. Puede sincronizar [!DNL DPUUIDs] con Audience Manager [!DNL UUIDs] y sincronizar [!DNL DPUUIDs] desde sus distintas fuentes de datos ([!DNL DPIDs]) en el proceso de sincronización de ID. | En las llamadas de DCS, `dpuuid` está precedido por el `d_` prefijo. <br> Ejemplo `d_dpuuid=2132-3423vn-343fds-3432r`. | No visible en la interfaz de usuario de Audience Manager. |
| [!DNL CRM ID] | Consulte `DPUUID`. | Consulte `DPUUID`. | Consulte `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | ID de cliente, código de integración de ID de cliente. Los pares [!DNL CID] y [!DNL CID_IC] clave-valor reemplazan [!DNL DPID] y [!DNL DPUUID]. Proporcionan las mismas funciones que [!DNL DPID] y [!DNL DPUUID], pero son más eficientes porque incluyen la ID del proveedor de datos y la ID del usuario (o el código de integración) en un único par clave-valor. | En las llamadas de DCS, estos ID van precedidos del `d_` prefijo. <br>Ejemplo: `d_cid_ic=39217_myIntegrationCode`. | Consulte `DPID` y `DPUUID`. |
| [!DNL DAID] | ID de publicidad del dispositivo. Un ID exclusivo de cada dispositivo hardware y que se utiliza con propósitos publicitarios. Normalmente lo proporciona el fabricante del dispositivo o del sistema operativo del dispositivo. | Consulte ID de dispositivos [globales](#global-device-ids). |  |

## ID de dispositivo globales {#global-device-ids}

Los ID de dispositivo globales son ID de publicidad de dispositivo, exclusivos de cada dispositivo, proporcionados por el fabricante del dispositivo o el sistema operativo. La tabla siguiente explica cuáles son estos ID y cuál es su formato. Para obtener más información sobre los ID de dispositivos globales y cómo utilizarlos en Audience Manager, consulte Fuentes [de datos](/help/using/features/global-data-sources.md)globales.

| ID | ID de fuente de datos global | Nombre y descripción | Ejemplo |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] Los ID son identificadores de dispositivos móviles, proporcionados por el fabricante del dispositivo. Estos ID representan dispositivos que ejecutan el sistema operativo iOS. | El formato consiste estrictamente en 32 dígitos hexadecimales en mayúsculas, mostrados en cinco grupos y separados por guiones, en el formato 8-4-4-4-12, con un total de 36 caracteres.<br> Ejemplo: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s son identificadores de dispositivos móviles proporcionados por los fabricantes de dispositivos Android. Estos ID representan dispositivos que ejecutan el [!DNL Android] sistema operativo. | El formato consiste estrictamente en 32 dígitos hexadecimales en minúsculas, mostrados en cinco grupos y separados por guiones, en el formato 8-4-4-4-12, para un total de 36 caracteres. <br>Ejemplo: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] representan dispositivos [!DNL Roku] de flujo continuo. | El formato consiste estrictamente en 32 dígitos hexadecimales en minúsculas, mostrados en cinco grupos y separados por guiones, en el formato 8-4-4-4-12, para un total de 36 caracteres. <br>Ejemplo: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s son identificadores de dispositivo generados por [!DNL Windows 10] cada dispositivo por usuario. | [!DNL MAID]s tienen el formato de cadenas alfanuméricas. |
| [!DNL DUID] | 404660 | [!DNL Samsung DUID]Los identificadores de dispositivo son proporcionados por Samsung Smart TV. | Los Samsung [!DNL DUID]tienen el formato de cadenas alfanuméricas. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Identificadores de dispositivo que representan dispositivos que ejecutan el [!DNL Fire OS] sistema operativo. | El formato consiste estrictamente en 32 dígitos hexadecimales en minúsculas, mostrados en cinco grupos y separados por guiones, en el formato 8-4-4-4-12, para un total de 36 caracteres. <br>Ejemplo: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |

