---
description: Este documento cubre los tipos de ID de Audience Manager que puede utilizar en las solicitudes sobre privacidad de datos.
seo-description: This document covers the types of Audience Manager IDs that you can use in data privacy requests.
seo-title: Audience Manager Identifiers (IDs)
solution: Audience Manager
keywords: AAM IU del RGPD, API del RGPD, CCPA, privacidad, ID de la
title: Identificadores (ID) de Audience Manager
feature: Data Governance & Privacy
exl-id: 5f18ed0a-c875-4596-a4d1-f9a7fe871d1b
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 96%

---

# Identificadores (ID) de Audience Manager {#aam-ids}

Al enviar [solicitudes sobre privacidad de datos](data-privacy-requests.md) a Adobe Audience Manager, debe incluir uno de los identificadores (ID) que se indican a continuación. Encontrará más información sobre los formatos de ID en nuestro [Índice de ID de Audience Manager](../../reference/ids-in-aam.md).

## ID de usuario único de Adobe Audience Manager

* **ID de usuario**: `aam_uuid`
* **Definición**: ID de usuario único de Adobe Audience Manager
* **ID de área de nombres**: 0

**Ejemplo de JSON**:

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

>[!NOTE]
>
>También puede utilizar el área de nombres [!DNL CORE].

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

## Adobe Experience Cloud ID

* **ID de usuario**: `mid`
* **Definición**: [!DNL Adobe Experience Cloud ID], anteriormente conocido como [!DNL Visitor ID] o [!DNL Marketing Cloud ID]
* **ID de área de nombres**: 4

>[!NOTE]
>
>También puede utilizar el área de nombres [!DNL ECID]. Consulte el segundo ejemplo [!DNL JSON].

**Ejemplo de JSON**:

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

## ID de cliente

**ID de usuario**: `cid`

**Definición**: ID del cliente, como una cookie que configuró para visitantes anónimos del sitio, el ID [!DNL CRM] de un sistema sin conexión o un nombre de usuario cifrado.

**ID de área de nombres**: específico del cliente. Lo encontrará en la instancia de Audience Manager.

**Ejemplo de JSON**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
```

## ID de publicidad móvil

**ID de usuario**: `d_cid`

**Definición**: ID de publicidad móvil.

**ID de área de nombres**:

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

Consulte [Fuentes de datos globales](../../features/global-data-sources.md) para obtener más información.

>[!IMPORTANT]
>
> Si utiliza el [!DNL SDK] móvil, también debe enviar el Experience Cloud ID (`MID`) junto con los ID de publicidad móvil para obtener respuestas de acceso y eliminación completas.

**Ejemplo de JSON**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

## Código de integración

**ID de usuario**: `d_cid_ic`

**Definición**: código de integración para la fuente de datos. Puede emplearse en lugar del ID de la fuente de datos/ID del área de nombres en la solicitud [!DNL API] a [!DNL Adobe Experience Cloud Privacy Core Service].

**ID** de área de nombres: no aplicable

**Ejemplo de JSON**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```
