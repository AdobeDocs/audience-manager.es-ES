---
description: Este documento explica cómo se rigen los datos de los clientes en Audience Manager.
seo-description: Este documento explica cómo se rigen los datos de clientes en Audience Manager.
seo-title: Administración de datos
solution: Audience Manager
keywords: IU del RGPD, API del RGPD, CCPA, privacidad, consentimiento, ofuscación, control
title: Administración de datos
feature: Data Governance & Privacy
exl-id: 52aeca00-73f2-4525-9e11-34a472ec45c6
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 94%

---

# Administración de datos

## Información general {#overview}

La administración de datos en Audience Manager se refiere al ciclo vital de los datos de sus clientes en Audience Manager y abarca la [recopilación y la ofuscación de direcciones IP](data-governance.md#collecting-ip-addresses), la [retención de datos](data-governance.md#data-retention) y las [transferencias de datos internacionales](data-governance.md#data-transfers).

## Recopilación y ofuscación de direcciones IP {#collecting-ip-addresses}

La dirección [!DNL IP] de un visitante en el sitio web de un cliente se transmite a un [!DNL Data Processing Center] de Adobe ([!DNL DPC]) donde se puede almacenar la dirección [!DNL IP]. Dependiendo de la configuración de red del visitante, la dirección [!DNL IP] no representa necesariamente la dirección [!DNL IP] del equipo del visitante. Por ejemplo, la dirección [!DNL IP] puede ser una dirección [!DNL IP] externa de un firewall de traducción de direcciones de red (NAT), un proxy [!DNL HTTP] o una puerta de enlace de Internet.

**Metodología de ofuscación de IP:** Siguiendo los principios de “Privacidad por diseño”, Adobe Audience Manager permite a los clientes activar la ofuscación de [!DNL IP] desde la interfaz de usuario, ya sea globalmente en todas las regiones geográficas o para países específicos. Cuando se habilita esta configuración, el último octeto (la última parte) de la dirección [!DNL IP] se descarta inmediatamente cuando la [!DNL IP] se incorpora en Audience Manager. Audience Manager descarta esta parte de la dirección [!DNL IP] antes del procesamiento (incluso antes de cualquier búsqueda geográfica opcional o registro de la dirección [!DNL IP]). Por ejemplo:

* Antes de registrar los valores de: `255.255.255.255`
* Después: `255.255.255.0`

>[!NOTE]
>
>Consulte [Ofuscación de direcciones IP](../../features/administration/ip-obfuscation.md) para obtener información sobre cómo habilitar la ofuscación de direcciones [!DNL IP] en la interfaz de usuario del Audience Manager.

Consulte el siguiente vídeo para comprender cómo funciona la ofuscación de direcciones [!DNL IP] en Audience Manager.

>[!VIDEO](https://video.tv.adobe.com/v/27218/)

**Segmentación geográfica:** Si habilita la ofuscación de direcciones [!DNL IP], los octetos restantes de la [!DNL IP] aún se pueden usar para la segmentación geográfica y creación de informes en Audience Manager. Si no habilita la ofuscación de direcciones [!DNL IP], Audience Manager utilizará la [!DNL IP] completa. Puede utilizar la función Segmentación geográfica que le permite identificar una ubicación de [!DNL IP] por área geográfica en cualquier caso, pero con una ligera pérdida de precisión cuando se utiliza la ofuscación de [!DNL IP]. Es muy probable que la obtención de información por ciudad se vea significativamente afectada por la ofuscación de la dirección [!DNL IP]. La obtención de información por región y país solo debería verse ligeramente afectada. Los datos de segmentación geográfica se detallan solamente hasta el nivel de ciudad o de código postal y no a nivel individual. Obtenga más información sobre [Segmentación geográfica](../../features/traits/trait-geotarget-keys.md) y cómo establecer rasgos con variables geográficas.

## Retención de datos en Audience Manager {#data-retention}

La aplicación de políticas de retención de datos apropiadas, seguras y oportunas a sus datos es una parte importante del cumplimiento de las normas de privacidad de datos. Los clientes de Audience Manager pueden establecer períodos de retención personalizados en rasgos y segmentos mediante la definición del TTL requerido (tiempo de vida). Consulte [Preguntas frecuentes sobre la retención de datos](../../faq/faq-privacy.md) para obtener más información sobre los períodos de retención.

## Transferencias de datos internacionales {#data-transfers}

Cuando Audience Manager transfiere datos personales de los clientes a otros países, lo hace cumpliendo las leyes correspondientes. Visite el [Centro de privacidad de Adobe](https://www.adobe.com/es/privacy/eudatatransfers.html) para obtener más información.
