---
description: El Generador de destinos permite crear destinos URL basados en cookies o DNL. No puede crear destinos de servidor a servidor (S2S) con el Generador de destinos, pero sí puede administrar sus asignaciones de segmentos. Póngase en contacto con su consultor para configurar un destino S2S. El Generador de destinos se encuentra en Datos de audiencia > Destinos.
seo-description: El Generador de destinos permite crear destinos URL basados en cookies o DNL. No puede crear destinos de servidor a servidor (S2S) con el Generador de destinos, pero sí puede administrar sus asignaciones de segmentos. Póngase en contacto con su consultor para configurar un destino S2S. El Generador de destinos se encuentra en Datos de audiencia > Destinos.
seo-title: Generador de destino
solution: Audience Manager
title: Generador de destino
feature: Conceptos básicos de destino
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 4%

---

# Generador de destino {#destination-builder}

[!UICONTROL Destination Builder] permite crear  [!DNL URL] destinos o basados en cookies. No puede crear destinos de servidor a servidor ([!DNL S2S]) con [!UICONTROL Destination Builder], pero sí puede administrar sus asignaciones de segmentos. Póngase en contacto con su consultor para configurar un destino [!DNL S2S]. [!UICONTROL Destination Builder] está en  **[!UICONTROL Audience Data > Destinations]**.

## Configuración del generador de destino {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] consta de las siguientes secciones y configuraciones:

| [!UICONTROL Destination Builder] Sección | Finalidad |
|--- |--- |
| Información básica | Se utiliza para asignar un nombre al destino, describirlo y seleccionar el tipo de destino ([!DNL URL] o [!DNL cookie]) y la plataforma (todos, [!DNL Android], el navegador o [!DNL iOS]). |
| Configuración | Incluye controles para: <br/><ul><li>Pasar datos de valor clave a destinos [!DNL URL]. Puede enviar datos como pares de clave-valor individuales o serializados. Para obtener más información, consulte [Destination Serialization](../../features/destinations/key-value-pairs.md#destination-serialized) y [Pares de clave-valor estándar y serie](../../features/destinations/key-value-pairs.md). </li><li>Elementos de un destino de cookie como nombre de cookie, dominio, tamaño, intervalo de caducidad, formato de datos, etc.</li></ul> |
| Asignaciones de segmentos | Le permite señalar el informe con un: <br/><ul><li>Busque, agregue y administre segmentos asociados con todos los tipos de destino. </li><li>Establezca las prioridades de envío en segmentos individuales (solo para segmentos basados en [!DNL cookie]).</li></ul> |

## Métodos de envío de datos {#data-delivery-methods}

Envíe información a un destino pasándola a través de una cadena [!DNL URL], escribiendo a un explorador [!DNL cookie] o a través de transferencias de datos de servidor a servidor sin conexión.

* [!DNL URL] y los destinos basados en cookies transmiten los datos sincrónicamente, ya que un usuario realiza una acción en una página.
* La transmisión de datos de servidor a servidor es asíncrona y puede producirse mucho después de que un usuario haya abandonado la página. El tipo de envío que seleccione depende de los requisitos empresariales y de cómo un socio de datos concreto desee o pueda recibir datos.

Consulte [Cómo elegir un tipo de destino](../../features/destinations/destinations.md) para obtener más información.
