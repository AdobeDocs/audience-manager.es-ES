---
description: La eliminación instantánea entre dispositivos corresponde a la capacidad de eliminar usuarios de varios dispositivos a la vez, siempre que los usuarios estén conectados a ellos, cuando en uno de los dispositivos se produce una experiencia particular. Utilice esta capacidad para ofrecer a los usuarios una experiencia coherente en distintos dispositivos. Esta experiencia es posible gracias a las capacidades de desegmentación en tiempo real de Audience Manager.
seo-description: La eliminación instantánea entre dispositivos corresponde a la capacidad de eliminar usuarios de varios dispositivos a la vez, siempre que los usuarios estén conectados a ellos, cuando en uno de los dispositivos se produce una experiencia particular. Utilice esta capacidad para ofrecer a los usuarios una experiencia coherente en distintos dispositivos. Esta experiencia es posible gracias a las capacidades de desegmentación en tiempo real de Audience Manager.
seo-title: Eliminación instantánea entre dispositivos
title: Eliminación instantánea entre dispositivos
uuid: cb 11 b 9 cb -6 d 7 d -4 aa 9-91 b 0-c 2715857 d 821
translation-type: tm+mt
source-git-commit: 86b23cc4097057fceadd4d0f7c5fad0db4f4232b

---


# Eliminación instantánea entre dispositivos {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] es la capacidad para eliminar usuarios en varios dispositivos conectados cuando una experiencia concreta se produce en cualquiera de estos dispositivos. Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. Esta experiencia es posible gracias a las capacidades de desegmentación en tiempo real de Audience Manager.

## Información general {#overview}

[!UICONTROL Instant Cross-Device Suppression] entrega dos casos de uso clave: mejora de la experiencia del usuario y la eficiencia de los medios.

* **Una experiencia de usuario mejorada**: Los usuarios que ya compraron su producto o servicio no verán los mismos elementos creativos que antes de la compra. En su lugar, podría mostrar mensajes de venta cruzada o venta cruzada para productos o servicios que sepa que no han comprado.
* **Eficiencia de los medios**: Optimizar la inversión de la campaña aplicando un límite de frecuencia global a todas [!DNL DSP]las s. El límite de frecuencia puede procesarse en tiempo real para varios dispositivos pertenecientes a un usuario.

Los detalles técnicos de la dessegmentación en tiempo real se describen en detalle en las reglas de combinación [de perfiles y en los procesos de segmentación de dispositivos](../../features/profile-merge-rules/merge-rule-unsegment.md). Lea la información sobre la implementación práctica de los casos de uso descritos anteriormente.

## No dirigir una vez convertido {#do-not-target-once}

Asegúrese de que los usuarios que ya hayan sido convertidos (compraron un producto, hayan adquirido una suscripción, etc.) no verá el mismo mensaje que antes de la conversión. Puede obtenerlo con [!UICONTROL AND NOT] la lógica de la siguiente manera.

1. Cree un segmento utilizando dos características y utilice [!UICONTROL AND NOT] la lógica, como se muestra en la siguiente imagen. Debe utilizar una característica basada en reglas para definir el evento de conversión para que el dessegmento se active en tiempo real. Obtenga más información sobre cómo [crear características basadas en reglas](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
1. Asigne el segmento a cualquier número de destinos de servidor a servidor en tiempo real. Lea cómo agregar segmentos a [destinos de servidor a servidor](../../features/destinations/add-edit-segments.md).

Los visitantes se califican para el segmento mientras no hayan convertido. Tan pronto como reúnan los requisitos para la característica de conversión, dejan de seguir la regla de segmento y se eliminan instantáneamente del segmento.

![](assets/and_not_use_case.png)

## No segmentar después de x impresiones {#do-not-target-after-x}

Puede asegurarse de no estar inundando los usuarios con el mismo elemento creativo configurando los controles de actualización y frecuencia. En este escenario, cree un segmento con dos características, tal como se describe en los pasos a continuación.

1. Cree un segmento utilizando dos características y utilice [!UICONTROL AND] la lógica, como se muestra en la siguiente imagen. Debe utilizar una característica basada en reglas para definir el evento de impresión para que el dessegmento se active en tiempo real. Obtenga más información sobre cómo [crear características basadas en reglas](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
   >[!NOTE]
   >
   >Puede utilizar [!UICONTROL Actionable Log Files] o [!UICONTROL Pixel Calls] crear características basadas en impresiones de usuario. Obtenga más información sobre [los archivos de registro procesables](../../integration/media-data-integration/actionable-log-files.md) y [las llamadas de píxeles](../../integration/media-data-integration/impression-data-pixels.md).
1. Aplicar controles de frecuencia al segundo rasgo. Si lo desea, también puede agregar controles de actualización. Obtenga más información sobre [cómo aplicar controles de frecuencia y actualización](../../features/segments/recency-and-frequency.md).
1. Asigne el segmento a cualquier número de destinos de servidor a servidor en tiempo real. Lea cómo agregar segmentos a [destinos de servidor a servidor](../../features/destinations/add-edit-segments.md).

En este escenario, una vez que los usuarios hayan acumulado más de tres impresiones, se eliminarán de este segmento y ya no verán este elemento creativo en particular.

![](assets/impressions_use_case.png)

## Aspectos importantes a la nota: procesamiento {#processing-notes}

Tenga en cuenta estos aspectos relacionados con el procesamiento:

* Para que funcione la capacidad de dessegmento en tiempo real, debe asignar los segmentos deseados a destinos de servidor a servidor en tiempo real.
* Para dispositivos conectados a un dispositivo mediante un gráfico [](../../features/profile-merge-rules/profile-link-use-case.md#recommendations)de dispositivos, aplicamos un límite de cuatro dispositivos con respecto a la evaluación y dessegmentación. Esta limitación se describe en [Opciones de gráfico de dispositivo y Dessegmentación de dispositivos](../../features/profile-merge-rules/merge-rule-unsegment.md#device-graph-options-unsegmentation).
* El comando unsegment se incluirá en un archivo por lotes, que se envía a los destinos cada 24 horas, para varios dispositivos conectados mediante el gráfico de dispositivos.
* El dispositivo se debe ver en tiempo real (en [Edge](../../reference/system-components/components-edge.md)) para solicitar la evaluación de segmentos. Para las características que tienen [!UICONTROL time-to-live (TTL)] un valor, incluso si se cumple una característica [!DNL TTL] , el dispositivo *no* se dessegmentará automáticamente hasta que el dispositivo se vea a continuación en tiempo real. Obtenga más información sobre [cómo establecer un intervalo de caducidad de características](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Si utiliza características [!UICONTROL DCS API] basadas en reglas en tiempo real, puede activar el dessegmento con el uso de [!UICONTROL AND NOT] la lógica. Obtenga más información sobre [el envío de datos a la API de DCS](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Aspectos importantes a la nota: Temporización {#timing-notes}

Tenga en cuenta estos aspectos relacionados con la temporización:

* Un segmento se almacenará en [Edge](../../reference/system-components/components-edge.md) para el mismo período de tiempo que un perfil de dispositivo se almacena en [!UICONTROL Edge], concretamente 14 días desde la última interacción en tiempo real. Obtenga más información sobre la retención de datos en nuestras preguntas frecuentes sobre retención [de datos](../../faq/faq-privacy.md#data-retention-faq).
* La operación sin segmentos tarda aproximadamente 24 horas en propagarse entre [!UICONTROL DCS] regiones. Obtenga más información sobre nuestras [!UICONTROL DCS] regiones [aquí](../../reference/system-components/components-data-collection.md) y [aquí](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).