---
description: La eliminación instantánea entre dispositivos corresponde a la capacidad de eliminar usuarios de varios dispositivos a la vez, siempre que los usuarios estén conectados a ellos, cuando en uno de los dispositivos se produce una experiencia particular. Utilice esta capacidad para ofrecer a los usuarios una experiencia coherente en distintos dispositivos. Esta experiencia es posible gracias a las capacidades de desegmentación en tiempo real de Audience Manager.
seo-description: La eliminación instantánea entre dispositivos corresponde a la capacidad de eliminar usuarios de varios dispositivos a la vez, siempre que los usuarios estén conectados a ellos, cuando en uno de los dispositivos se produce una experiencia particular. Utilice esta capacidad para ofrecer a los usuarios una experiencia coherente en distintos dispositivos. Esta experiencia es posible gracias a las capacidades de desegmentación en tiempo real de Audience Manager.
seo-title: Eliminación instantánea entre dispositivos
title: Eliminación instantánea entre dispositivos
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 15%

---


# Eliminación instantánea entre dispositivos {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] es la capacidad de suprimir usuarios en varios dispositivos conectados a ellos cuando se produce una experiencia concreta en cualquiera de estos dispositivos. Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. Esta experiencia es posible gracias a las capacidades de desegmentación en tiempo real de Audience Manager.

## Información general {#overview}

[!UICONTROL Instant Cross-Device Suppression] ofrece dos casos de uso clave: mejora de la experiencia del usuario y de la eficacia de los medios.

* **Una experiencia** de usuario mejorada: Los usuarios que ya hayan comprado su producto o servicio no verán los mismos elementos creativos que antes de la compra. En su lugar, puede mostrar mensajes de venta cruzada o de venta vertical para productos o servicios que sabe que no han comprado.
* **Eficiencia** de los medios: Optimice el gasto en campaña aplicando un límite de frecuencia global en todas [!DNL DSP]las aplicaciones. El límite de frecuencia se puede accionar en tiempo real para varios dispositivos que pertenecen a un usuario.

Los detalles técnicos de la dessegmentación en tiempo real se describen en detalle en Reglas de combinación de [Perfiles y Procesos](merge-rule-unsegment.md)de dessegmentación de dispositivos. Siga leyendo para la implementación práctica de los casos de uso descritos anteriormente.

## No convertir el Destinatario una vez {#do-not-target-once}

Asegúrese de que los usuarios que ya han realizado la conversión (han adquirido un producto, han adquirido una suscripción, etc.) no verá los mismos mensajes que antes de la conversión. Puede obtener esto mediante la [!UICONTROL AND NOT] lógica siguiente.

1. Cree un segmento con dos características y utilice la [!UICONTROL AND NOT] lógica, como se muestra en la siguiente imagen. Debe utilizar una característica basada en reglas para definir el evento de conversión para que el dessegmento se active en tiempo real. Obtenga más información sobre cómo [crear características](../traits/create-onboarded-rule-based-traits.md)basadas en reglas.
2. Asigne el segmento a cualquier número de destinos de servidor a servidor en tiempo real. Obtenga información sobre cómo agregar segmentos a destinos [](../destinations/add-edit-segments.md)de servidor a servidor.

Sus visitantes cumplen los requisitos para el segmento siempre y cuando no se hayan convertido. Tan pronto como cumplen los requisitos para la característica de conversión, dejan de seguir la regla de segmento y se eliminan instantáneamente del segmento.

![](assets/and_not_use_case.png)

## No Destinatario después de x impresiones {#do-not-target-after-x}

Puede asegurarse de no inundar a los usuarios con el mismo elemento creativo estableciendo controles de actualización y frecuencia. En este escenario, cree un segmento con dos características, como se describe en los pasos a continuación.

1. Cree un segmento con dos características y utilice la [!UICONTROL AND] lógica, como se muestra en la siguiente imagen. Debe utilizar una característica basada en reglas para definir el evento de impresión para que el dessegmento se active en tiempo real. Obtenga más información sobre cómo [crear características](../traits/create-onboarded-rule-based-traits.md)basadas en reglas.
   >[!NOTE]
   >
   >Puede usar [!UICONTROL Actionable Log Files] o [!UICONTROL Pixel Calls] crear características basadas en impresiones de usuario. Obtenga más información sobre los archivos de registro [procesables](../../integration/media-data-integration/actionable-log-files.md) y las llamadas de [píxel](../../integration/media-data-integration/impression-data-pixels.md).
2. Aplicar controles de frecuencia a la segunda característica. Si lo desea, también puede agregar controles de actualización. Obtenga más información sobre [cómo aplicar los controles](../segments/recency-and-frequency.md)de frecuencia y actualización.
3. Asigne el segmento a cualquier número de destinos de servidor a servidor en tiempo real. Obtenga información sobre cómo agregar segmentos a destinos [](../destinations/add-edit-segments.md)de servidor a servidor.

En este escenario, una vez que los usuarios hayan acumulado más de tres impresiones, se eliminarán de este segmento y ya no verán este elemento creativo en particular.

![](assets/impressions_use_case.png)

## Aspectos importantes que hay que tener en cuenta: procesamiento {#processing-notes}

Tenga en cuenta los siguientes aspectos relacionados con el procesamiento:

* Para que funcione la capacidad de dessegmentación en tiempo real, debe asignar los segmentos deseados a destinos de servidor a servidor en tiempo real.
* Para los dispositivos conectados a un dispositivo mediante un gráfico [de](profile-link-use-case.md#recommendations)dispositivos, se impone un límite de cuatro dispositivos en cuanto a evaluación y dessegmentación. Esta limitación se describe en Opciones [de Device Graph y Dessegmentación](merge-rule-unsegment.md#device-graph-options-unsegmentation)de dispositivos. &#x200B;
* El comando unsegment se incluirá en un archivo por lotes, que se envía a destinos cada 24 horas, para varios dispositivos conectados por el gráfico del dispositivo.
* El dispositivo debe verse en tiempo real (en [Edge](../../reference/system-components/components-edge.md) para solicitar la evaluación del segmento en tiempo real). En el caso de características que tienen un [!UICONTROL time-to-live (TTL)] momento en el que [!DNL TTL] se cumple la característica, el dispositivo se dessegmentará automáticamente en un plazo de 24 horas a través del archivo por lotes. &#x200B; Obtenga más información sobre cómo [establecer un intervalo de caducidad](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval)de rasgo.
* Si está utilizando las características [!UICONTROL DCS API] a bordo basadas en reglas en tiempo real, puede activar el dessegmento con el uso de la [!UICONTROL AND NOT] lógica. Obtenga más información sobre el [envío de datos a la API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)de DCS. &#x200B;

## Aspectos importantes a tener en cuenta: Temporización {#timing-notes}

Tenga en cuenta estos aspectos relacionados con el tiempo:

* Un segmento se almacenará en [Edge](../../reference/system-components/components-edge.md) durante el mismo período de tiempo en el que se almacena un perfil del dispositivo en el [!UICONTROL Edge], es decir, 14 días desde la última interacción en tiempo real. Obtenga más información sobre la retención de datos en nuestras preguntas más frecuentes [sobre retención](../../faq/faq-privacy.md#data-retention-faq)de datos.
* La operación de dessegmentación tarda aproximadamente 24 horas en propagarse por [!DNL DCS] regiones. Lea más sobre nuestras [!DNL DCS] regiones [aquí](../..//reference/system-components/components-data-collection.md) y [aquí](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
