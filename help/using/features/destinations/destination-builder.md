---
description: El Generador de destinos permite crear destinos URL basados en cookies o DNL. No puede crear destinos de servidor a servidor (S2S) con el Generador de destinos, pero puede administrar sus asignaciones de segmentos. Póngase en contacto con su asesor para configurar un destino de S2S. El Generador de destino se encuentra en Datos de Audiencia > Destinos.
seo-description: El Generador de destinos permite crear destinos URL basados en cookies o DNL. No puede crear destinos de servidor a servidor (S2S) con el Generador de destinos, pero puede administrar sus asignaciones de segmentos. Póngase en contacto con su asesor para configurar un destino de S2S. El Generador de destino se encuentra en Datos de Audiencia > Destinos.
seo-title: Generador de destino
solution: Audience Manager
title: Generador de destino
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 4%

---


# Generador de destino {#destination-builder}

[!UICONTROL Destination Builder] le permite crear  [!DNL URL] destinos o basados en cookies. No se pueden crear destinos de servidor a servidor ([!DNL S2S]) con [!UICONTROL Destination Builder], pero sí administrar sus asignaciones de segmentos. Póngase en contacto con su asesor para configurar un destino [!DNL S2S]. [!UICONTROL Destination Builder] en  **[!UICONTROL Audience Data > Destinations]**.

## Configuración del Generador de destinos {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] consta de las siguientes secciones y configuraciones:

| [!UICONTROL Destination Builder] Sección | Finalidad |
|--- |--- |
| Información básica | Se utiliza para asignar un nombre al destino, describirlo y seleccionar el tipo de destino ([!DNL URL] o [!DNL cookie]) y la plataforma (todos, [!DNL Android], el explorador o [!DNL iOS]). |
| Configuración | Incluye controles para: <br/><ul><li>Pasar datos de valor clave a [!DNL URL] destinos. Puede enviar datos como pares de clave-valor individuales o serializados. Para obtener más información, consulte [Serialización de destino](../../features/destinations/key-value-pairs.md#destination-serialized) y [Pares de clave-valor estándar y serie](../../features/destinations/key-value-pairs.md). </li><li>Elementos de un destino de cookie como nombre de cookie, dominio, tamaño, intervalo de caducidad, formato de datos, etc.</li></ul> |
| Asignaciones de segmentos | Le permite señalar el informe con un: <br/><ul><li>Busque, agregue y administre segmentos asociados con todos los tipos de destino. </li><li>Configure prioridades de envío en segmentos individuales (solo para segmentos basados en [!DNL cookie]).</li></ul> |

## Métodos de Envío de datos {#data-delivery-methods}

Envíe información a un destino pasándola a través de una cadena [!DNL URL], escribiendo en un explorador [!DNL cookie] o a través de transferencias de datos de servidor a servidor sin conexión.

* [!DNL URL] y los destinos basados en cookies transmiten datos sincrónicamente, a medida que un usuario realiza una acción en una página.
* La transmisión de datos de servidor a servidor es asincrónica y puede producirse mucho después de que un usuario haya abandonado la página. El tipo de envío que seleccione dependerá de los requisitos comerciales y de cómo un socio de datos en particular desee o pueda recibir datos.

Consulte [Cómo elegir un tipo de destino](../../features/destinations/destinations.md) para obtener más información.