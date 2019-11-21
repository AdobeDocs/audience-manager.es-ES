---
description: Este documento explica cómo se rigen los datos de cliente en Audience Manager.
seo-description: Este documento explica cómo se rigen los datos de cliente en Audience Manager.
seo-title: Administración de datos
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent, obfuscation, governance
title: Administración de datos
translation-type: tm+mt
source-git-commit: b47819d5e6394e78d744ada1bb7090d337938983

---


# Administración de datos

## Información general {#overview}

La administración de datos en Audience Manager hace referencia al ciclo vital de los datos de sus clientes en Audience Manager y abarca la [recopilación y la confusión de direcciones](data-governance.md#collecting-ip-addresses)IP, la retención [](data-governance.md#data-retention)de datos y las transferencias [de datos](data-governance.md#data-transfers)transfronterizas.

## Recopilación de direcciones IP y confusión de direcciones IP {#collecting-ip-addresses}

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**** Metodología de confusión de IP: Siguiendo los principios de "Privacidad por diseño", Adobe Audience Manager permite a los clientes activar la confusión [!DNL IP] desde la interfaz de usuario, ya sea globalmente en todas las regiones geográficas o para países específicos. Al habilitar esta configuración, el último octeto (la última parte) de la [!DNL IP] dirección se descarta inmediatamente cuando la [!DNL IP] dirección se ingesta en Audience Manager. Audience Manager descarta esta parte de la [!DNL IP] dirección antes del procesamiento (incluso antes de cualquier búsqueda geográfica opcional o registro de la [!DNL IP] dirección). Por ejemplo:

* Antes de registrar los valores de: `255.255.255.255`
* Después: `255.255.255.0`

>[!NOTE]
>
>Consulte Confusión [de direcciones](../../features/administration/ip-obfuscation.md) IP para obtener información sobre cómo habilitar la confusión de [!DNL IP] direcciones en la interfaz de usuario de Audience Manager.

Vea el siguiente vídeo para comprender cómo funciona la confusión de [!DNL IP] direcciones en Audience Manager.

>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=spa)

**** Segmentación geográfica: Si habilita la confusión de [!DNL IP] direcciones, los octetos restantes de la [!DNL IP] dirección aún se pueden usar para la segmentación geográfica y los informes en Audience Manager. Si no habilita [!DNL IP] la confusión de direcciones, Audience Manager utiliza la [!DNL IP] dirección completa. Puede utilizar la función Segmentación geográfica que le permite identificar una [!DNL IP] ubicación por área geográfica en cualquier caso, pero con una ligera pérdida de precisión cuando se utiliza [!DNL IP] la confusión. Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. La obtención de información a nivel regional y nacional sólo debería verse ligeramente afectada. Los datos de segmentación geográfica solo son granulares a nivel de ciudad o de código postal, y no a nivel individual. Obtenga más información sobre [targeting](../../features/traits/trait-geotarget-keys.md) geográfico y cómo configurar características con variables geográficas.

## Retención de datos en Audience Manager {#data-retention}

La aplicación de políticas de retención de datos apropiadas, seguras y oportunas a sus datos es una parte importante del cumplimiento de las normas de privacidad de datos. Los clientes de Audience Manager pueden establecer períodos de retención personalizados en características y segmentos mediante la definición del TTL requerido (tiempo de vida). Consulte Preguntas más frecuentes sobre la retención [de datos](../../faq/faq-privacy.md) para obtener más información sobre los períodos de retención.

## Transferencias de datos transfronterizas {#data-transfers}

El RGPD no prohíbe la transferencia de datos fuera de Europa. Exige que la protección de la privacidad de los datos europeos persista dondequiera que se transfieran. Visite el [Adobe Privacy Center](https://www.adobe.com/privacy/eudatatransfers.html) para obtener más información. La CCPA no tiene restricciones de transferencia de datos transfronteriza.
