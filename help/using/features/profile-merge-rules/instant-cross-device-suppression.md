---
description: La eliminación instantánea entre dispositivos corresponde a la capacidad de eliminar usuarios de varios dispositivos a la vez, siempre que los usuarios estén conectados a ellos, cuando en uno de los dispositivos se produce una experiencia particular. Utilice esta capacidad para ofrecer a los usuarios una experiencia coherente en distintos dispositivos. Esta experiencia es posible gracias a las capacidades de desegmentación en tiempo real de Audience Manager.
seo-description: La eliminación instantánea entre dispositivos corresponde a la capacidad de eliminar usuarios de varios dispositivos a la vez, siempre que los usuarios estén conectados a ellos, cuando en uno de los dispositivos se produce una experiencia particular. Utilice esta capacidad para ofrecer a los usuarios una experiencia coherente en distintos dispositivos. Esta experiencia es posible gracias a las capacidades de desegmentación en tiempo real de Audience Manager.
seo-title: Eliminación instantánea entre dispositivos
title: Eliminación instantánea entre dispositivos
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Combinación de perfiles
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: 2643bebea8618124d5c96906e8dc89e21024d51a
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 15%

---

# Eliminación instantánea entre dispositivos {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] es la capacidad de suprimir usuarios en varios dispositivos conectados a ellos cuando se produce una experiencia concreta en cualquiera de estos dispositivos. Utilice la capacidad [!UICONTROL Instant Cross-Device Suppression] para ofrecer a los usuarios una experiencia coherente entre dispositivos. Esta experiencia es posible gracias a las capacidades de desegmentación en tiempo real de Audience Manager.

## Información general {#overview}

[!UICONTROL Instant Cross-Device Suppression] ofrece dos casos de uso clave: mejora de la experiencia del usuario y la eficacia de los medios.

* **Una experiencia** de usuario mejorada: Los usuarios que ya hayan comprado su producto o servicio no verán los mismos elementos creativos que antes de la compra. En su lugar, podría mostrar mensajes de ventas cruzadas o de ventas al por mayor para productos o servicios que sepa que no han comprado.
* **Eficiencia de los medios**: Optimice el gasto de su campaña aplicando un límite de frecuencia global en todas  [!DNL DSP]las campañas. El límite de frecuencia se puede accionar en tiempo real para varios dispositivos que pertenecen a un usuario.

Los detalles técnicos de la dessegmentación en tiempo real se describen en detalle en [Reglas de combinación de perfiles y procesos de eliminación de la segmentación de dispositivos](merge-rule-unsegment.md). Siga leyendo para la implementación práctica de los casos de uso descritos anteriormente.

## No establecer objetivo una vez convertido {#do-not-target-once}

Asegúrese de que los usuarios que ya hayan realizado la conversión (hayan comprado un producto, adquirido una suscripción, etc.) no verá la misma mensajería que antes de la conversión. Puede obtener esto mediante la lógica [!UICONTROL AND NOT], de la siguiente manera.

1. Cree un segmento con dos características y utilice la lógica [!UICONTROL AND NOT], como se muestra en la imagen siguiente. Debe utilizar un rasgo basado en reglas para definir el evento de conversión para que el desegmento se active en tiempo real. Obtenga más información sobre cómo [crear características basadas en reglas](../traits/create-onboarded-rule-based-traits.md).
2. Asigne el segmento a cualquier número de destinos de servidor a servidor en tiempo real. Obtenga más información sobre cómo agregar segmentos a [destinos de servidor a servidor](../destinations/add-edit-segments.md).

Los visitantes cumplen los requisitos para el segmento siempre que no se hayan convertido. Tan pronto como cumplen los requisitos para la característica de conversión, dejan de seguir la regla de segmento y se eliminan instantáneamente del segmento.

![](assets/and_not_use_case.png)

## No segmentar después de x Impresiones {#do-not-target-after-x}

Puede asegurarse de no inundar a los usuarios con el mismo elemento creativo estableciendo controles de actualización y frecuencia. En este escenario, cree un segmento con dos características, tal como se describe en los pasos siguientes.

1. Cree un segmento con dos características y utilice la lógica [!UICONTROL AND], como se muestra en la imagen siguiente. Debe utilizar un rasgo basado en reglas para definir el evento de impresión para que la desegmentación se active en tiempo real. Obtenga más información sobre cómo [crear características basadas en reglas](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >Puede utilizar [!UICONTROL Actionable Log Files] o [!UICONTROL Pixel Calls] para crear características basadas en impresiones del usuario. Obtenga más información sobre [Archivos de registro procesables](../../integration/media-data-integration/actionable-log-files.md) y [Llamadas de píxel](../../integration/media-data-integration/impression-data-pixels.md).
2. Aplicar controles de frecuencia al segundo rasgo. Si lo desea, también puede agregar controles de actualización. Obtenga más información sobre [cómo aplicar controles de actualización y frecuencia](../segments/recency-and-frequency.md).
3. Asigne el segmento a cualquier número de destinos de servidor a servidor en tiempo real. Obtenga más información sobre cómo agregar segmentos a [destinos de servidor a servidor](../destinations/add-edit-segments.md).

En este escenario, una vez que los usuarios hayan acumulado más de tres impresiones, se eliminarán de este segmento y ya no verán este elemento creativo en particular.

![](assets/impressions_use_case.png)

## Aspectos importantes a tener en cuenta: procesamiento {#processing-notes}

Tenga en cuenta estos aspectos relacionados con el procesamiento:

* Para que funcione la función de desegmentación en tiempo real, debe asignar los segmentos deseados a destinos de servidor a servidor en tiempo real.
* Para los dispositivos conectados a un dispositivo mediante un [gráfico de dispositivos](profile-link-use-case.md#recommendations), se impone un límite de cuatro dispositivos con respecto a la evaluación y la eliminación de la segmentación. Esta limitación se describe en [Opciones de gráfico de dispositivos y Dessegmentación de dispositivos](merge-rule-unsegment.md#device-graph-options-unsegmentation). &#x200B;
* El comando unsegment se incluye en un archivo por lotes, que se envía a los destinos cada 24 horas, para varios dispositivos conectados por el gráfico de dispositivos.
* El dispositivo debe verse en tiempo real (en [Edge](../../reference/system-components/components-edge.md)) para solicitar la evaluación de segmentos en tiempo real. En el caso de los rasgos que tienen [!UICONTROL time-to-live (TTL)] cuando se cumple el rasgo [!DNL TTL], el dispositivo se dessegmenta automáticamente en un plazo de 24 horas a través del archivo por lotes. &#x200B; Obtenga más información sobre cómo [Establecer un intervalo de caducidad de rasgos](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Si utiliza [!UICONTROL DCS API] para incorporar rasgos basados en reglas en tiempo real, puede almacenar en déclencheur la eliminación de la segmentación con el uso de la lógica [!UICONTROL AND NOT]. Obtenga más información sobre el [envío de datos a la API de DCS](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md). &#x200B;

## Aspectos importantes a tener en cuenta: Temporización {#timing-notes}

Tenga en cuenta estos aspectos relacionados con el tiempo:

* Se almacenará un segmento en [Edge](../../reference/system-components/components-edge.md) durante el mismo período de tiempo en el que se almacenará un perfil de dispositivo en [!UICONTROL Edge], es decir, 14 días desde la última interacción en tiempo real. Obtenga más información sobre la retención de datos en nuestras [Preguntas frecuentes sobre la retención de datos](../../faq/faq-privacy.md#data-retention-faq).
* La operación de desegmentación tarda aproximadamente 24 horas en propagarse entre las regiones [!DNL DCS]. Obtenga más información sobre nuestras [!DNL DCS] regiones [aquí](../../reference/system-components/components-data-collection.md) y [aquí](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
