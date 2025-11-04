---
description: La eliminación instantánea entre dispositivos corresponde a la capacidad de eliminar usuarios de varios dispositivos a la vez, siempre que los usuarios estén conectados a ellos, cuando en uno de los dispositivos se produce una experiencia particular. Utilice la capacidad de eliminación instantánea entre dispositivos para ofrecer una experiencia coherente entre dispositivos a los usuarios. Esta experiencia es posible gracias a las capacidades de desegmentación en tiempo real de Audience Manager.
seo-description: Instant Cross-Device Suppression is the ability to suppress users across multiple devices connected to them when a particular experience occurs on any of these devices. Use the Instant Cross-Device Suppression capability to deliver a consistent experience across devices to your users. This experience is made possible by the real-time unsegment capabilities in Audience Manager.
seo-title: Instant Cross-Device Suppression
title: Eliminación instantánea entre dispositivos
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 6%

---

# Eliminación instantánea entre dispositivos {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] es la capacidad de suprimir usuarios en varios dispositivos conectados a ellos cuando se produce una experiencia concreta en cualquiera de estos dispositivos. Utilice la capacidad [!UICONTROL Instant Cross-Device Suppression] para ofrecer una experiencia coherente entre dispositivos a los usuarios. Esta experiencia es posible gracias a las capacidades de desegmentación en tiempo real de Audience Manager.

## Información general {#overview}

[!UICONTROL Instant Cross-Device Suppression] ofrece dos casos de uso clave: experiencia del usuario mejorada y eficiencia de los medios.

* **Una experiencia de usuario mejorada**: Los usuarios que ya compraron su producto o servicio no verán los mismos elementos creativos que antes de la compra. En su lugar, puede mostrar mensajes de ventas adicionales o de ventas cruzadas de productos o servicios que sabe que no han adquirido.
* **Eficiencia de los medios**: optimice el gasto en campañas aplicando un límite de frecuencia global en todos los [!DNL DSP]s. El límite de frecuencia se puede actuar en tiempo real para varios dispositivos pertenecientes a un usuario.

Los detalles técnicos de la eliminación de la segmentación en tiempo real se describen detalladamente en [Reglas de combinación de perfiles y procesos de eliminación de la segmentación de dispositivos](merge-rule-unsegment.md). Siga leyendo para conocer la implementación práctica de los casos de uso descritos anteriormente.

## No segmentar una vez convertido {#do-not-target-once}

Asegúrese de que los usuarios que ya se hayan convertido (hayan comprado un producto, adquirido una suscripción, etc.) no vean los mismos mensajes que antes de la conversión. Puede obtenerla mediante la lógica [!UICONTROL AND NOT], de la siguiente manera.

1. Cree un segmento con dos características y use la lógica [!UICONTROL AND NOT], como se muestra en la siguiente imagen. Debe utilizar un rasgo basado en reglas para definir el evento de conversión para que la eliminación de la segmentación se active en tiempo real. Obtenga más información sobre cómo [crear características basadas en reglas](../traits/create-onboarded-rule-based-traits.md).
2. Asigne el segmento a cualquier número de destinos de servidor a servidor en tiempo real. Más información sobre cómo agregar segmentos a [destinos de servidor a servidor](../destinations/add-edit-segments.md).

Sus visitantes cumplen los requisitos para el segmento siempre y cuando no se hayan convertido. Tan pronto como cumplen los requisitos para la característica de conversión, dejan de seguir la regla del segmento y se eliminan instantáneamente del segmento.

![](assets/and_not_use_case.png)

## No segmentar después de impresiones x {#do-not-target-after-x}

Puede asegurarse de que no inunda a los usuarios con el mismo elemento creativo configurando los controles de actualización y frecuencia. En este escenario, cree un segmento con dos características, tal como se describe en los pasos siguientes.

1. Cree un segmento con dos características y use la lógica [!UICONTROL AND], como se muestra en la siguiente imagen. Debe utilizar un rasgo basado en reglas para definir el evento de impresión para que la eliminación de la segmentación se active en tiempo real. Obtenga más información sobre cómo [crear características basadas en reglas](../traits/create-onboarded-rule-based-traits.md).

   >[!NOTE]
   >
   >Puede usar [!UICONTROL Actionable Log Files] o [!UICONTROL Pixel Calls] para crear características basadas en las impresiones del usuario. Obtenga más información sobre [archivos de registro procesables](../../integration/media-data-integration/actionable-log-files.md) y [llamadas en píxeles](../../integration/media-data-integration/impression-data-pixels.md).

1. Aplique controles de frecuencia al segundo rasgo. Si lo desea, también puede agregar controles de actualización. Más información sobre [cómo aplicar controles de actualización y frecuencia](../segments/recency-and-frequency.md).
1. Asigne el segmento a cualquier número de destinos de servidor a servidor en tiempo real. Más información sobre cómo agregar segmentos a [destinos de servidor a servidor](../destinations/add-edit-segments.md).

En esta situación, una vez que los usuarios hayan acumulado más de tres impresiones, se eliminarán de este segmento y ya no verán este elemento creativo en particular.

![](assets/impressions_use_case.png)

## Aspectos importantes a tener en cuenta: procesamiento {#processing-notes}

Tenga en cuenta estos aspectos relacionados con el procesamiento:

* Para que funcione la capacidad de eliminación de segmentos en tiempo real, debe asignar los segmentos deseados a destinos de servidor a servidor en tiempo real.
* Para los dispositivos conectados a un dispositivo mediante un [gráfico de dispositivos](profile-link-use-case.md#recommendations), aplicamos un límite de cuatro dispositivos con respecto a la evaluación y la eliminación de la segmentación. Esta limitación se describe en [Opciones de gráfico de dispositivos y eliminación de la segmentación de dispositivos](merge-rule-unsegment.md#device-graph-options-unsegmentation).&#x200B;
* El comando de eliminación de la segmentación se incluye en un archivo por lotes, que se envía a los destinos cada 24 horas, para varios dispositivos conectados mediante el gráfico de dispositivos.
* El dispositivo se debe ver en tiempo real (en el [Edge](../../reference/system-components/components-edge.md)) para solicitar la evaluación de segmentos en tiempo real. En el caso de los rasgos que tienen un [!UICONTROL time-to-live (TTL)] cuando se cumple el rasgo [!DNL TTL], el dispositivo se dessegmentará automáticamente en un plazo de 24 horas mediante el archivo por lotes..&#x200B; Obtenga más información sobre cómo [establecer un intervalo de caducidad de rasgos](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Si está usando [!UICONTROL DCS API] para incorporar características basadas en reglas en tiempo real, puede almacenar en déclencheur la eliminación de la segmentación con el uso de la lógica [!UICONTROL AND NOT]. Más información sobre [el envío de datos a la API de DCS](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).&#x200B;

## Aspectos importantes que debe tener en cuenta: calendario {#timing-notes}

Tenga en cuenta estos aspectos relacionados con el tiempo:

* Se almacenará un segmento en [Edge](../../reference/system-components/components-edge.md) durante el mismo período de tiempo en el que se almacena un perfil de dispositivo en [!UICONTROL Edge], es decir, 14 días desde la última interacción en tiempo real. Obtenga más información sobre la retención de datos en nuestras [Preguntas frecuentes sobre la retención de datos](../../faq/faq-privacy.md#data-retention-faq).
* La operación de eliminación de la segmentación tarda aproximadamente 24 horas en propagarse en [!DNL DCS] regiones. Obtenga más información sobre nuestras [!DNL DCS] regiones [aquí](../../reference/system-components/components-data-collection.md) y [aquí](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
