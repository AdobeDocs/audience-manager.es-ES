---
description: Describe los pares comunes de clave-valor de nivel de plataforma que puede utilizar para dirigirse a usuarios con variables relacionadas con dispositivos en todas las propiedades de su cuenta de Audience Manager.
seo-description: Describe los pares comunes de clave-valor de nivel de plataforma que puede utilizar para dirigirse a usuarios con variables relacionadas con dispositivos en todas las propiedades de su cuenta de Audience Manager.
seo-title: Segmentación de dispositivos con claves a nivel de plataforma
solution: Audience Manager
title: Segmentación de dispositivos con claves a nivel de plataforma
uuid: bc 048 cc 5-3 df 1-49 bc-ac 78-0 ea 5 d 7 edd 9 cc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Device Targeting With Platform-level Keys {#device-targeting-with-platform-level-keys}

Describe los pares comunes de clave-valor de nivel de plataforma que puede utilizar para dirigirse a usuarios con variables relacionadas con dispositivos en todas las propiedades de su cuenta de Audience Manager.

## Purpose of Platform-level Variables {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Platform-level variables let you take data passed in from a particular site and make it available for targeting across all the properties in your [!DNL Audience Manager] account. These variables are formed by [key-value pairs](../../reference/key-value-pairs-explained.md) with the key prefixed by `d_` as shown below.

## Platform-level Keys Defined by User Agent {#keys-user-agent}

[!UICONTROL Data Collection Servers] La extracción de los valores de estas claves del encabezado del agente [de usuario](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) en `HTTP` solicitudes. The values represent device-level information from the [!UICONTROL Device Atlas] database. Las señales de la tabla siguiente están disponibles, como se extrae del ejemplo del agente de usuario. [Descargue una lista de las claves](assets/device_keys.csv)más comunes según [!UICONTROL Device Atlas] las medidas.

| [!DNL Signal] | [!DNL Type] | [!DNL Example] |
|---|---|---|
| `d_device_vendor` | [!DNL VENDOR] | [!DNL apple] |
| `d_device_hardware_type` | [!DNL HARDWARE] | [!DNL mobile phone] |
| `d_device_os_version` | [!DNL OS VERSION] | [!DNL 5_0] |
| `d_device_os_name` | [!DNL OS NAME] | [!DNL ios] |
| `d_device_model` | [!DNL MODEL] | [!DNL iphone] |
| `d_device_marketing_name` | [!DNL MARKETING NAME] | [!DNL iphone] |
| `d_device_manufacturer` | [!DNL MANUFACTURER] | [!DNL apple] |

```
 Mozilla/5.0 (iPhone; CPU iPhone OS 5_0 like Mac OS X) AppleWebKit/534.46 (KHTML, like Gecko) Version/5.1 Mobile/9A334 Safari/7534.48.3
```

>[!NOTE]
>
>Even if one or more signals cannot be retrieved from the user agent header, the other signals will still be passed to the [!UICONTROL Data Collection Servers].

>[!MORE_ LIKE_ THIS]
>
>* [Requisitos de prefijo para variables clave](../../features/traits/trait-variable-prefixes.md)

