---
description: La eliminación instantánea entre dispositivos corresponde a la capacidad de eliminar usuarios de varios dispositivos a la vez, siempre que los usuarios estén conectados a ellos, cuando en uno de los dispositivos se produce una experiencia particular. Utilice esta capacidad para ofrecer a los usuarios una experiencia coherente en distintos dispositivos. Esta experiencia es posible gracias a las capacidades de desegmentación en tiempo real de Audience Manager.
seo-description: La eliminación instantánea entre dispositivos corresponde a la capacidad de eliminar usuarios de varios dispositivos a la vez, siempre que los usuarios estén conectados a ellos, cuando en uno de los dispositivos se produce una experiencia particular. Utilice esta capacidad para ofrecer a los usuarios una experiencia coherente en distintos dispositivos. Esta experiencia es posible gracias a las capacidades de desegmentación en tiempo real de Audience Manager.
seo-title: Eliminación instantánea entre dispositivos
title: Eliminación instantánea entre dispositivos
uuid: cb 11 b 9 cb -6 d 7 d -4 aa 9-91 b 0-c 2715857 d 821
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Eliminación instantánea entre dispositivos {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] es la capacidad para eliminar usuarios en varios dispositivos conectados cuando una experiencia concreta se produce en cualquiera de estos dispositivos. Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. Esta experiencia es posible gracias a las capacidades de desegmentación en tiempo real de Audience Manager.

## Información general {#overview}

[!UICONTROL Instant Cross-Device Suppression] entrega dos casos de uso clave: mejora de la experiencia del usuario y la eficiencia de los medios.

* **Una experiencia de usuario mejorada**: Los usuarios que ya compraron su producto o servicio no verán los mismos elementos creativos que antes de la compra. En su lugar, podría mostrar mensajes de venta cruzada o venta cruzada para productos o servicios que sepa que no han comprado.
* **Eficiencia de los medios**: Optimizar la inversión de la campaña aplicando un límite de frecuencia global a todas [!DNL DSP]las s. El límite de frecuencia puede procesarse en tiempo real para varios dispositivos pertenecientes a un usuario.

The technical details of the real-time unsegmentation are described in length in [Profile Merge Rules and Device Un-Segmentation Processes](../../features/profile-merge-rules/merge-rule-unsegment.md). Lea la información sobre la implementación práctica de los casos de uso descritos anteriormente.

## Do Not Target Once Converted {#do-not-target-once}

Asegúrese de que los usuarios que ya hayan sido convertidos (compraron un producto, hayan adquirido una suscripción, etc.) no verá el mismo mensaje que antes de la conversión. You can obtain this using the [!UICONTROL AND NOT] logic, as follows.

1. Create a segment using two traits, and use the [!UICONTROL AND NOT] logic, as shown in the image below. Debe utilizar una característica basada en reglas para definir el evento de conversión para que el dessegmento se active en tiempo real. Read more about how to [create rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
1. Asigne el segmento a cualquier número de destinos de servidor a servidor en tiempo real. Read on about how to add segments to [server-to-server destinations](../../features/destinations/manage-destinations.md#add-edit-segments).

Los visitantes se califican para el segmento mientras no hayan convertido. Tan pronto como reúnan los requisitos para la característica de conversión, dejan de seguir la regla de segmento y se eliminan instantáneamente del segmento.

![](assets/and_not_use_case.png)

## Do Not Target After x Impressions {#do-not-target-after-x}

Puede asegurarse de no estar inundando los usuarios con el mismo elemento creativo configurando los controles de actualización y frecuencia. En este escenario, cree un segmento con dos características, tal como se describe en los pasos a continuación.

1. Create a segment using two traits, and use the [!UICONTROL AND] logic, as shown in the image below. Debe utilizar una característica basada en reglas para definir el evento de impresión para que el dessegmento se active en tiempo real. Read more about how to [create rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
   >[!NOTE]
   >
   >You can use [!UICONTROL Actionable Log Files] or [!UICONTROL Pixel Calls] to create traits based on user impressions. Read more about [Actionable Log Files](../../integration/media-data-integration/actionable-log-files.md) and [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md).
1. Aplicar controles de frecuencia al segundo rasgo. Si lo desea, también puede agregar controles de actualización. Read more about [how to apply recency and frequency controls](../../features/segments/recency-and-frequency.md).
1. Asigne el segmento a cualquier número de destinos de servidor a servidor en tiempo real. Read on about how to add segments to [server-to-server destinations](../../features/destinations/manage-destinations.md#add-edit-segments).

En este escenario, una vez que los usuarios hayan acumulado más de tres impresiones, se eliminarán de este segmento y ya no verán este elemento creativo en particular.

![](assets/impressions_use_case.png)

## Important Aspects to Note - Processing {#processing-notes}

Tenga en cuenta estos aspectos relacionados con el procesamiento:

* Para que funcione la capacidad de dessegmento en tiempo real, debe asignar los segmentos deseados a destinos de servidor a servidor en tiempo real.
* For devices connected to a device by a [device graph](../../features/profile-merge-rules/profile-link-use-case.md#recommendations), we enforce a four-device limit regarding evaluation and unsegmentation. This limitation is described in [Device Graph Options and Device Unsegmentation](../../features/profile-merge-rules/merge-rule-unsegment.md#device-graph-options-unsegmentation).&#x200B;
* El comando unsegment se incluirá en un archivo por lotes, que se envía a los destinos cada 24 horas, para varios dispositivos conectados mediante el gráfico de dispositivos.
* The device must be seen in real-time (on the [Edge](../../reference/system-components/components-edge.md)) to prompt segment evaluation. For traits that have a [!UICONTROL time-to-live (TTL)] value, even if a trait [!DNL TTL] is met, the device will *not* automatically be unsegmented until the device is next seen in real-time.&#x200B; Read more about how to [Set a Trait Expiration Interval](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* If you are using the [!UICONTROL DCS API] to on-board rule-based traits in real-time, you can trigger the unsegment with the use of the [!UICONTROL AND NOT] logic. Read more about [sending data to the DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).&#x200B;

## Important Aspects to Note - Timing {#timing-notes}

Tenga en cuenta estos aspectos relacionados con la temporización:

* A segment will be stored on the [Edge](../../reference/system-components/components-edge.md) for the same time period as a device profile is stored on the [!UICONTROL Edge], namely 14 days since last real-time interaction. Read more about data retention in our [Data Retention FAQ](../../faq/faq-privacy.md#data-retention-faq).
* It takes approximately 24 hours for the unsegment operation to propagate across [!UICONTROL DCS] regions. Read more about our [!UICONTROL DCS] regions [here](../../reference/system-components/components-data-collection.md) and [here](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).