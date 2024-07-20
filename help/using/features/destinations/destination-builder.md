---
description: Destination Builder permite crear destinos de URL basados en cookies o DNL. No puede crear destinos de servidor a servidor (S2S) con Destination Builder, pero puede administrar sus asignaciones de segmentos. Póngase en contacto con su consultor de para configurar un destino S2S. El Generador de destinos se encuentra en Datos de audiencia > Destinos.
seo-description: Destination Builder lets you create cookie-based or DNL URL destinations. You cannot create server-to-server (S2S) destinations with Destination Builder, but you can manage their segment mappings. Contact your consultant to set up a S2S destination. Destination Builder is located in Audience Data > Destinations.
seo-title: Destination Builder
solution: Audience Manager
title: Generador de destino
feature: Destination Basics
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# Generador de destino {#destination-builder}

[!UICONTROL Destination Builder] le permite crear destinos basados en cookies o [!DNL URL]. No puede crear destinos de servidor a servidor ([!DNL S2S]) con [!UICONTROL Destination Builder], pero puede administrar sus asignaciones de segmentos. Póngase en contacto con el consultor para configurar un destino de [!DNL S2S]. [!UICONTROL Destination Builder] se encuentra en **[!UICONTROL Audience Data > Destinations]**.

## Configuración del generador de destino {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] consta de las siguientes secciones y configuraciones:

| Sección [!UICONTROL Destination Builder] | Finalidad |
|--- |--- |
| Información básica | Se usa para asignar un nombre al destino, describirlo y seleccionar el tipo de destino ([!DNL URL] o [!DNL cookie]) y la plataforma (todos, [!DNL Android], el explorador o [!DNL iOS]). |
| Configuración | Incluye controles para: <br/><ul><li>Pasando datos de clave-valor a [!DNL URL] destinos. Puede enviar datos como pares de clave-valor individuales o serializados. Para obtener más información, consulte [Serialización de destino](../../features/destinations/key-value-pairs.md#destination-serialized) y [Pares de clave-valor estándar y serie](../../features/destinations/key-value-pairs.md). </li><li>Elementos de un destino de cookie, como nombre de cookie, dominio, tamaño, intervalo de caducidad, formato de datos, etc.</li></ul> |
| Asignaciones de segmentos | Le permite: <br/><ul><li>Busque, añada y administre segmentos asociados a todos los tipos de destino. </li><li>Establezca las prioridades de envío en segmentos individuales (solo para segmentos basados en [!DNL cookie]).</li></ul> |

## Métodos de envío de datos {#data-delivery-methods}

Envíe información a un destino pasándola a través de una cadena [!DNL URL], escribiendo en un explorador [!DNL cookie] o mediante transferencias de datos de servidor a servidor sin conexión.

* [!DNL URL] y los destinos basados en cookies transmiten datos sincrónicamente, a medida que un usuario realiza acciones en una página.
* La transmisión de datos de servidor a servidor es asíncrona y puede producirse mucho después de que un usuario haya abandonado la página. El tipo de entrega que seleccione depende de los requisitos de su empresa y de cómo un socio de datos en particular desee o pueda recibir datos.

Consulte [Cómo elegir un tipo de destino](../../features/destinations/destinations.md) para obtener más información.
