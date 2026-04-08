---
description: Este documento explica cómo se rigen los datos de los clientes en Audience Manager.
seo-description: TThis document explains how customer data is governed in Audience Manager.
seo-title: Data Governance
solution: Audience Manager
keywords: IU del RGPD, API del RGPD, CCPA, privacidad, consentimiento, ofuscación, gobernanza
title: Administración de datos
feature: Data Governance & Privacy
exl-id: 52aeca00-73f2-4525-9e11-34a472ec45c6
TQID: https://experienceleague.adobe.com/HVF-SxKO4mcE7YkiiwXLBPn2K3N5NIjpZHFWgZb0CoI
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a99472c1-6aae-4c7a-8aa0-f60636369620id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: a49258d4-867f-4130-b875-d72c001bdf6cid: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: cc72dcf1-72e1-48cc-b434-e7c27d62d67cid: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 451
ht-degree: 90%

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
>Consulte [Ofuscación de direcciones IP](../../features/administration/ip-obfuscation.md) para obtener información sobre cómo habilitar la ofuscación de direcciones [!DNL IP] en la interfaz de usuario de Audience Manager.

Consulte el siguiente vídeo para comprender cómo funciona la ofuscación de direcciones [!DNL IP] en Audience Manager.

>[!VIDEO](https://video.tv.adobe.com/v/27218/)

**Segmentación geográfica:** Si habilita la ofuscación de direcciones [!DNL IP], los octetos restantes de la [!DNL IP] aún se pueden usar para la segmentación geográfica y creación de informes en Audience Manager. Si no habilita la ofuscación de direcciones [!DNL IP], Audience Manager utilizará la [!DNL IP] completa. Puede utilizar la función Segmentación geográfica que le permite identificar una ubicación de [!DNL IP] por área geográfica en cualquier caso, pero con una ligera pérdida de precisión cuando se utiliza la ofuscación de [!DNL IP]. Es muy probable que la obtención de información por ciudad se vea significativamente afectada por la ofuscación de la dirección [!DNL IP]. La obtención de información por región y país solo debería verse ligeramente afectada. Los datos de segmentación geográfica se detallan solamente hasta el nivel de ciudad o de código postal y no a nivel individual. Obtenga más información sobre [Segmentación geográfica](../../features/traits/trait-geotarget-keys.md) y cómo establecer rasgos con variables geográficas.

## Retención de datos en Audience Manager {#data-retention}

La aplicación de políticas de retención de datos apropiadas, seguras y oportunas a sus datos es una parte importante del cumplimiento de las normas de privacidad de datos. Los clientes de Audience Manager pueden establecer períodos de retención personalizados en rasgos y segmentos mediante la definición del TTL requerido (tiempo de vida). Consulte [Preguntas frecuentes sobre la retención de datos](../../faq/faq-privacy.md) para obtener más información sobre los períodos de retención.

## Transferencias de datos internacionales {#data-transfers}

Cuando Audience Manager transfiere datos personales de los clientes a otros países, lo hace cumpliendo las leyes correspondientes. Visite el [Centro de privacidad de Adobe](https://www.adobe.com/es/privacy/eudatatransfers.html) para obtener más información.
