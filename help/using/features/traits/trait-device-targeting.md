---
description: Describe los pares clave-valor comunes de nivel de plataforma que puede utilizar para dirigirse a usuarios con variables relacionadas con el dispositivo en todas las propiedades de la cuenta de Audience Manager.
seo-description: Describe los pares clave-valor comunes de nivel de plataforma que puede utilizar para dirigirse a usuarios con variables relacionadas con el dispositivo en todas las propiedades de la cuenta de Audience Manager.
seo-title: Segmentación de dispositivos con claves a nivel de plataforma
solution: Audience Manager
title: Segmentación de dispositivos con claves a nivel de plataforma
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: 'Rasgos '
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 9%

---

# Segmentación de dispositivos con claves a nivel de plataforma {#device-targeting-with-platform-level-keys}

Describe los pares clave-valor comunes de nivel de plataforma que puede utilizar para dirigirse a usuarios con variables relacionadas con el dispositivo en todas las propiedades de la cuenta de Audience Manager.

## Objetivo de las variables a nivel de plataforma {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Las variables de nivel de plataforma permiten tomar los datos pasados desde un sitio en particular y ponerlos a disposición para su segmentación en todas las propiedades de su cuenta [!DNL Audience Manager]. Estas variables están formadas por [pares clave-valor](../../reference/key-value-pairs-explained.md) con la clave con el prefijo `d_` como se muestra a continuación.

## Claves a nivel de plataforma definidas por el agente de usuario {#keys-user-agent}

El [!UICONTROL Data Collection Servers] extrae los valores para estas claves del [encabezado del agente de usuario](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) en las solicitudes `HTTP`. Los valores representan información a nivel de dispositivo de la base de datos [!UICONTROL Device Atlas]. Las señales de la siguiente tabla están disponibles, tal como se extrae del ejemplo del agente de usuario. [Descargue una lista de las claves](assets/device_keys.csv) más comunes, según las  [!UICONTROL Device Atlas] mediciones.

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
>Incluso si una o más señales no se pueden recuperar del encabezado del agente de usuario, las demás señales se pasarán a [!UICONTROL Data Collection Servers].

>[!MORELIKETHIS]
>
>* [Requisitos de prefijo para variables clave](../../features/traits/trait-variable-prefixes.md)

