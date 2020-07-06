---
description: Audience Manager le ayuda a recopilar y administrar datos de origen, así como de segundo nivel y de terceros.
seo-description: Audience Manager le ayuda a recopilar y administrar datos de origen, así como de segundo nivel y de terceros.
seo-title: Tipos de datos recopilados
solution: Audience Manager
title: Tipos de datos recopilados
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
feature: overview
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 73%

---


# Tipos de datos recopilados {#types-of-data-collected}

[!DNL Audience Manager] le ayuda a recopilar y administrar datos de origen, así como de segundo nivel y de terceros.

Desbloquear los activos de la información de los clientes, que están almacenados en varios silos, es uno de los mayores desafíos que enfrentan las compañías en la actualidad en relación a los datos. From [!DNL CRM] databases, to registration systems, to ad servers, and so forth, companies require tools that help centralize valuable data and manage customer/audience information as a single strategic data asset. [!DNL Audience Manager] le ayuda a desbloquear la información aislada de los clientes y a administrar la recopilación de datos a partir de varias fuentes. Collected data can be managed based on data element time-to-live ([!DNL TTL]) values, which helps the publisher control data expiration across all sources. [!DNL Audience Manager] está diseñado para ayudarle a administrar los siguientes tipos de datos:

| Tipo de datos | Procedencia de los datos |
|---|---|
| **Datos de origen** | Clientes. Los datos se recopilan en línea (a partir de las interacciones de los consumidores en sus sitios web) o sin conexión. |
| **De segundo nivel** | Socios estratégicos y anunciantes. |
| **Terceros** | Proveedores de datos e intercambios. Los datos pueden incluir información sobre la intención, detalles demográficos, de estilo de vida, interacción social, psicográficos, etc. |

## Recopilación de datos de origen {#first-party-data}

First-party data collection is a main [!DNL Audience Manager] feature. Esta competencia básica responde a las necesidades de nuestros clientes (editores o anunciantes), que desean que los datos que tienen en propiedad sean un pilar básico en sus programas de marketing o para segmentar y construir modelos para compararlos con otras fuentes de datos.

[!DNL Audience Manager] trabaja con los clientes para comprender su estrategia de datos y, a continuación, asigna esa estrategia a un plan de recopilación de datos personalizado. Nuestro equipo de Soluciones para socios colabora con usted para evaluar los sitios, las señales de datos sin procesar y otras interacciones del usuario en sus sitios web. Con esta información, contribuiremos a crear una estrategia de recopilación de datos hecha a su medida, que capture las señales de datos de usuario a partir de diversas páginas de su inventario. Los datos capturados se almacenan y se reasignan a una taxonomía predefinida, que se puede actualizar en cualquier momento, a medida que cambien sus necesidades comerciales.

El siguiente ejemplo muestra cómo se pueden capturar los elementos de datos potenciales desde una página de venta de muestra.

![shopping-cart-data](assets/shopping-cart-data.png)

| Elemento | Descripción |
|---|---|
| 1 | **Género**. El nombre de un comprador suele indicar su género. En nuestro ejemplo, el nombre del comprador es Mary, así que sabemos que el comprador es una mujer. Audience Manager nunca almacena los nombres. |
| 2 | **Intereses**. Los artículos del carro de compras pueden indicar diversos intereses. En nuestro ejemplo, Mary gasta mucho dinero en equipos de fitness. |
| 3 | **Tipo de vivienda**. En función de las direcciones de envío o facturación, se puede deducir si Mary compra equipos de fitness para sí misma o para una empresa. |
| 4 | **Ubicación**. [!DNL ZIP] los códigos son más fiables que [!DNL IP] las direcciones cuando se trata de localizar una ubicación. |
| 5 | **Afinidad de promociones**. Si un comprador utiliza códigos promocionales o tarjetas regalo, probablemente sea un cazador de gangas en busca de las mejores ofertas. |
| 6 | **Poder adquisitivo**. Price data correlated with [!DNL ZIP+4] codes indicate spending power of a given location. |

After the raw data is collected, it gets mapped back to customer-defined traits within the [!DNL Audience Manager] platform. Tanto la taxonomía como las asignaciones de datos se pueden ajustar en cualquier momento sin realizar cambios en el código de recopilación de datos.

## Recopilación de datos de segundo nivel {#second-party-data}

Los datos de segundo nivel provienen de un socio comercial estratégico (no son datos del editor). Se recopilan y administran igual que los datos de origen.

En el caso de los datos de segundo nivel, los anunciantes envían sus propios activos de datos a los editores para que puedan combinar esa información con los datos del editor y, a continuación, ejecutar un programa de publicidad más segmentado. Además, los editores pueden ampliar su grupo de audiencias asociándose con sus anunciantes. In most cases, these arrangements involve contractual relationships limited to putting the [!DNL Audience Manager] container tag on the partner site to facilitate data collection and sharing.

Un ejemplo de recopilación y remarketing de datos de segundo nivel sería este: un vendedor de ropa al por menor recopila datos sobre sus productos y luego comparte esa información con socios clave. In this case, the retailed could serve different ads across an [!DNL Audience Manager] partner site for consumers who chose various jacket colors and sizes.

![](assets/shopping-cart-traits.png)

## Recopilación de datos de terceros {#third-party-data}

Los datos de terceros consisten en información recopilada y compartida por proveedores externos a [!DNL Audience Manager].

Third-party data can be used to qualify existing data [!UICONTROL segments] (for example, age, household income, and so forth), provide data that is in demand but not otherwise available, or be used in lookalike modeling against a known user base from first-party and second-party data. [!DNL Audience Manager] trabaja con muchos proveedores de datos de terceros y le ayudará a comprender el tipo de datos que estos recopilan para que pueda cerrar los acuerdos estratégicos adecuados con cada proveedor.

>[!NOTE]
>
>Para obtener una lista completa de los proveedores de datos de terceros admitidos por [!DNL Audience Manager], consulte el [Adobe Audience Finder](https://www.adobe-audience-finder.com/).

[!DNL Audience Manager] se integra con otros proveedores de datos en función de sus conjuntos de datos [!DNL APIs] y de su disponibilidad. La recopilación de datos funciona en tiempo real cuando un usuario navega por el sitio o a través de metodologías fuera de banda, en las que los ID se sincronizan entre socios y los datos se transfieren entre servidores una vez que un usuario ha abandonado el sitio. In either case, [!DNL Audience Manager] clients get the benefit of having third-party data synchronized on our platform, which means each client, or domain, does not have to perform its own synchronization. Esto permite aumentar el alcance y reducir las llamadas al servidor desde la página.

## Concordancia de socios {#match-partners}

Muchos clientes eligen trabajar con socios que aporten concordancias de datos de terceros. Estas entidades están relacionadas con sitios que tienen requisitos de registro y pueden procesar archivos de datos de clientes al hacerlos coincidir (en tiempo real) según su red de registro.

![data-provider-match](assets/data-provider-match.png)
