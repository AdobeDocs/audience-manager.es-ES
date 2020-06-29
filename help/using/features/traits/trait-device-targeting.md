---
description: Describe los pares de clave-valor comunes de nivel de plataforma que puede utilizar para destinatario de usuarios con variables relacionadas con el dispositivo en todas las propiedades de la cuenta de Audience Manager.
seo-description: Describe los pares de clave-valor comunes de nivel de plataforma que puede utilizar para destinatario de usuarios con variables relacionadas con el dispositivo en todas las propiedades de la cuenta de Audience Manager.
seo-title: Segmentación de dispositivos con claves de nivel Platform
solution: Audience Manager
title: Segmentación de dispositivos con claves de nivel Platform
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---


# Device Targeting With Platform-level Keys {#device-targeting-with-platform-level-keys}

Describe los pares de clave-valor comunes de nivel de plataforma que puede utilizar para destinatario de usuarios con variables relacionadas con el dispositivo en todas las propiedades de la cuenta de Audience Manager.

## Objetivo de las variables de nivel Platform {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Las variables de nivel de Platform permiten tomar datos pasados desde un sitio en particular y ponerlos a disposición para objetivos en todas las propiedades de la [!DNL Audience Manager] cuenta. Estas variables están formadas por pares [](../../reference/key-value-pairs-explained.md) clave-valor con la clave con el prefijo `d_` como se muestra a continuación.

## Claves de nivel Platform definidas por el agente de usuario {#keys-user-agent}

Extraer los [!UICONTROL Data Collection Servers] valores de estas claves del encabezado [del agente de](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) usuario en `HTTP` las solicitudes. Los valores representan información de nivel de dispositivo de la [!UICONTROL Device Atlas] base de datos. Las señales de la siguiente tabla están disponibles, según se extrae del ejemplo del agente de usuario. [Descargue una lista de las claves](assets/device_keys.csv)más comunes, según [!UICONTROL Device Atlas] las mediciones.

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
>Aunque no se puedan recuperar una o más señales del encabezado del agente de usuario, las demás señales se seguirán pasando al [!UICONTROL Data Collection Servers].

>[!MORELIKETHIS]
>
>* [Requisitos de prefijo para variables clave](../../features/traits/trait-variable-prefixes.md)

