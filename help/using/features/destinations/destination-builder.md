---
description: El Generador de destino permite crear destinos de URL basados en cookies o DNL. No puede crear destinos de servidor a servidor (S 2 S) con Generador de destino, pero puede administrar sus asignaciones de segmentos. Póngase en contacto con su asesor para configurar un destino S 2 S. El Generador de destino se encuentra en Datos de audiencia > Destinos.
seo-description: El Generador de destino permite crear destinos de URL basados en cookies o DNL. No puede crear destinos de servidor a servidor (S 2 S) con Generador de destino, pero puede administrar sus asignaciones de segmentos. Póngase en contacto con su asesor para configurar un destino S 2 S. El Generador de destino se encuentra en Datos de audiencia > Destinos.
seo-title: Generador de destino
solution: Audience Manager
title: Generador de destino
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---


# Generador de destino {#destination-builder}

[!UICONTROL Destination Builder] permite crear destinos basados en cookies o [!DNL URL] en destinos. No puede crear destinos de servidor a servidor ([!DNL S2S]) con [!UICONTROL Destination Builder], pero puede administrar sus asignaciones de segmentos. Póngase en contacto con su asesor para configurar [!DNL S2S] un destino. [!UICONTROL Destination Builder] está ubicado **[!UICONTROL Audience Data > Destinations]** en.

## Configuración del Generador de destinos {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] consiste en las siguientes secciones y configuraciones:

| [!UICONTROL Destination Builder] Sección | Finalidad |
|--- |--- |
| Información básica | Se utiliza para nombrar el destino, describirlo y seleccionar tipo de destino ([!DNL URL] o [!DNL cookie]) y plataforma (todo, [!DNL Android]explorador o [!DNL iOS]). |
| Configuración | Incluye controles para: <br/><ul><li>Pasar datos de valor clave a [!DNL URL] destinos. Puede enviar datos como pares de clave-valor individuales o serializados. Para obtener más información, consulte Serialización [de destino](../../features/destinations/key-value-pairs.md#destination-serialized) y [Pares estándar y de clave de serie](../../features/destinations/key-value-pairs.md). </li><li>Elementos de un destino de cookie como nombre de cookie, dominio, tamaño, intervalo de caducidad, formato de datos, etc.</li></ul> |
| Asignaciones de segmentos | Le permite señalar el informe con un: <br/><ul><li>Busque, agregue y administre segmentos asociados con todos los tipos de destino. </li><li>Definir prioridades de entrega en segmentos individuales (solo para segmentos [!DNL cookie]basados en -).</li></ul> |

## Métodos de envío de datos {#data-delivery-methods}

Envíe información a un destino pasando a través de [!DNL URL] una cadena, escribiendo en un navegador [!DNL cookie]o mediante transferencias de datos servidor a servidor sin conexión.

* [!DNL URL] y los destinos basados en cookies transmiten datos sincrónicamente, ya que el usuario realiza acciones en una página.
* La transmisión de datos de servidor a servidor es asincrónica y puede ocurrir mucho después de que el usuario haya abandonado la página. El tipo de entrega que seleccione depende de los requisitos comerciales y de cómo un socio de datos concreto desee recibir datos o puede recibir datos.

Consulte [Cómo elegir un tipo de destino](../../features/destinations/destinations.md) para obtener más información.