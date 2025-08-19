---
description: Describe los pares clave-valor comunes a nivel de plataforma que puede usar para dirigirse a usuarios con variables relacionadas con dispositivos en todas las propiedades de su cuenta de Audience Manager.
seo-description: Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.
seo-title: Device Targeting With Platform-level Keys
solution: Audience Manager
title: Segmentación de dispositivos con claves a nivel de plataforma
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: b299783b993c5d4a1c7738eca82932c20f377ee7
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 1%

---

# Segmentación de dispositivos con claves a nivel de plataforma {#device-targeting-with-platform-level-keys}

>[!WARNING]
>
>Google ha actualizado la funcionalidad de [!DNL Google Chrome] y de todos los exploradores basados en [!DNL Chromium] para minimizar la información recopilada mediante el encabezado `User-Agent`.
>&#x200B;>A partir de marzo de 2023, Audience Manager admitirá estas actualizaciones aprovechando [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es). Para seguir usando la información de rasgos proporcionada a través del encabezado `User-Agent`, debe usar [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es) y habilitar [sugerencias de cliente de agente de usuario de alta entropía](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=es).
>&#x200B;>Estas actualizaciones no son compatibles con [DIL](../../../using/dil/dil-overview.md), por lo que los clientes de Audience Manager que usen [!DNL DIL] no podrán recopilar información de rasgos a través del encabezado `User-Agent`.

Describe los pares clave-valor comunes a nivel de plataforma que puede usar para dirigirse a usuarios con variables relacionadas con dispositivos en todas las propiedades de su cuenta de Audience Manager.

## Propósito de las variables de nivel de plataforma {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Las variables de nivel de plataforma le permiten tomar datos pasados desde un sitio en particular y hacer que estén disponibles para la segmentación en todas las propiedades de su cuenta de [!DNL Audience Manager]. Estas variables están formadas por [pares clave-valor](../../reference/key-value-pairs-explained.md) con la clave con el prefijo `d_`, como se muestra a continuación.

## Claves de nivel de plataforma definidas por el agente de usuario {#keys-user-agent}

[!UICONTROL Data Collection Servers] extrae los valores de estas claves del [encabezado del agente de usuario](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) en `HTTP` solicitudes. Los valores representan información de nivel de dispositivo de la base de datos [!UICONTROL Device Atlas]. Las señales de la tabla siguiente están disponibles, tal como se extraen del ejemplo del agente de usuario. [Descargue una lista de las claves más comunes](assets/device_keys.csv), según las mediciones de [!UICONTROL Device Atlas].

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
>Aunque no se puedan recuperar una o más señales del encabezado del agente de usuario, las demás señales se pasarán al [!UICONTROL Data Collection Servers].

>[!MORELIKETHIS]
>
>* [Requisitos de prefijo para variables clave](../../features/traits/trait-variable-prefixes.md)
