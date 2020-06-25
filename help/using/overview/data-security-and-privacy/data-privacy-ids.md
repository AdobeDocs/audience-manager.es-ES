---
description: Este documento cubre los tipos de ID de Audience Manager que puede utilizar en las solicitudes de privacidad de datos.
seo-description: Este documento cubre los tipos de ID de Audience Manager que puede utilizar en las solicitudes de privacidad de datos.
seo-title: Identificadores de Audience Manager (ID)
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, AAM ID
title: Identificadores de Audience Manager (ID)
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 10%

---


# Identificadores de Audience Manager (ID) {#aam-ids}

Al enviar solicitudes [de privacidad de](data-privacy-requests.md) datos a Adobe Audience Manager, debe incluir uno de los identificadores (ID) enumerados a continuación. Puede encontrar más información sobre los formatos de ID en nuestro [Índice de ID de Audience Manager](../../reference/ids-in-aam.md).

## ID de usuario único de Adobe Audience Manager

* **ID de usuario**: `aam_uuid`
* **Definición**: ID de usuario único de Adobe Audience Manager
* **ID** de Área de nombres: 0

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
>También puede utilizar la [!DNL CORE] Área de nombres.

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
* **ID** de Área de nombres: 4

>[!NOTE]
>
>También puede utilizar la [!DNL ECID] Área de nombres. Consulte el segundo [!DNL JSON] ejemplo.

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

## Customer ID

**ID de usuario**: `cid`

**Definición**: ID del cliente, como una cookie que configuró para visitantes anónimos del sitio o un [!DNL CRM] ID de un sistema sin conexión o un nombre de usuario con hash.

**ID** de Área de nombres: Específico del cliente. Por favor, búsquela en su instancia de Audience Manager.

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

**ID de espacio de nombres**:

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

Consulte Fuentes [de datos](../../features/global-data-sources.md) globales para obtener más información.

>[!IMPORTANT]
>
> Si utiliza Mobile [!DNL SDK], también debe enviar el ID de Experience Cloud (`MID`) junto con los ID de publicidad móvil para obtener respuestas de acceso y eliminación completas.

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

**Definición**: Código de integración para el origen de datos. Se puede usar en lugar de ID de fuente de datos / ID de Área de nombres en la [!DNL API] solicitud de [!DNL Adobe Experience Cloud Privacy Core Service].

**ID** de Área de nombres: No aplicable

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
