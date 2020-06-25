---
description: Audience Manager le ayuda a recopilar y administrar datos de origen, de terceros y de terceros.
seo-description: Audience Manager le ayuda a recopilar y administrar datos de origen, de terceros y de terceros.
seo-title: Tipos de datos recopilados
solution: Audience Manager
title: Tipos de datos recopilados
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
feature: overview
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 1%

---


# Tipos de datos recopilados {#types-of-data-collected}

[!DNL Audience Manager] le ayuda a recopilar y administrar datos de origen, de terceros y de terceros.

Desbloquear los activos de información de los clientes almacenados en varios silos es uno de los mayores desafíos de datos que enfrentan las compañías en la actualidad. Desde [!DNL CRM] bases de datos, sistemas de registro, servidores de publicidad, etc., las compañías requieren herramientas que ayuden a centralizar datos valiosos y a administrar la información de clientes y audiencias como un único recurso de datos estratégicos. [!DNL Audience Manager] le ayuda a desbloquear la información aislada de los clientes y a administrar la recopilación de datos de varias fuentes. Los datos recopilados se pueden administrar en función de los valores de tiempo de vida ([!DNL TTL]) del elemento de datos, lo que ayuda al editor a controlar la caducidad de los datos en todas las fuentes. [!DNL Audience Manager] está diseñado para ayudarle a administrar los siguientes tipos de datos:

| Tipo de datos | De dónde provienen los datos |
|---|---|
| **Origen** | Clientes. Los datos se recopilan en línea (a partir de las interacciones de los consumidores en sus sitios web) o sin conexión. |
| **Segundo nivel** | Socios estratégicos y anunciantes. |
| **Terceros** | Proveedores de datos y/o intercambios. Los datos pueden incluir información como intención, demografía, estilo de vida o social, psicografía, etc. |

## First-Party Data Collection {#first-party-data}

La recopilación de datos de origen es una [!DNL Audience Manager] característica principal. Esta competencia básica responde a las necesidades de nuestros clientes (editores o anunciantes) que desean utilizar los datos propios como piedra angular de sus programas de mercadotecnia o para dirigir y modelar en relación con otras fuentes de datos.

[!DNL Audience Manager] trabaja con los clientes para comprender su estrategia de datos y luego asigna esa estrategia a un plan de recopilación de datos personalizado. Nuestro equipo de Soluciones para Socios trabaja con usted para evaluar los sitios, las señales de datos sin procesar y otras interacciones del usuario en sus sitios web. Con esta información, le ayudaremos a crear una estrategia de recopilación de datos personalizada que capture las señales de datos de nivel de usuario de diversas páginas del inventario. Los datos capturados se almacenan y se asignan de nuevo a una taxonomía predefinida, que se puede actualizar en cualquier momento, a medida que cambian las necesidades comerciales.

El siguiente ejemplo ilustra cómo se pueden capturar los elementos de datos potenciales desde una página de compras de muestra.

![shopping-cart-data](assets/shopping-cart-data.png)

| Elemento | Descripción |
|---|---|
| 1 | **Sexo**. El nombre de un comprador suele indicar su sexo. En nuestro ejemplo, el nombre del comprador es Mary, así que sabemos que el comprador es una mujer. El Audience Manager nunca almacena los nombres. |
| 2 | **Intereses**. Los artículos del carro de compras pueden indicar diversos intereses. En nuestro ejemplo, Mary gasta mucho en equipos de fitness. |
| 3 | **Tipo** de vivienda. En función de las direcciones de envío y/o facturación, puede deducir si Mary compra equipos de fitness para sí misma o para una compañía. |
| 4 | **Ubicación**. [!DNL ZIP] los códigos son más fiables que [!DNL IP] las direcciones cuando se trata de localizar una ubicación. |
| 5 | **Afinidad** de promoción. Si un comprador utiliza códigos promocionales o tarjetas de regalo, probablemente sea un cazador de gangas que busca las mejores ofertas. |
| 6 | **Potencia** de gasto. Los datos de precios correlacionados con [!DNL ZIP+4] los códigos indican la potencia de gasto de una ubicación determinada. |

Una vez recopilados los datos sin procesar, se vuelven a asignar a características definidas por el cliente dentro de la [!DNL Audience Manager] plataforma. Tanto la taxonomía como las asignaciones de datos se pueden ajustar en cualquier momento sin realizar cambios en el código de recopilación de datos.

## Recopilación de datos de terceros {#second-party-data}

Los datos de terceros provienen de un socio comercial estratégico (no son datos del editor). Esta información se recopila y gestiona del mismo modo que los datos de origen.

En un escenario de datos de terceros, los anunciantes envían sus propios recursos de datos a los editores para que puedan combinar esa información con los datos del editor y, a continuación, ejecutar un programa de publicidad más dirigido. Además, los editores pueden ampliar su grupo de audiencias asociándose con sus anunciantes. En la mayoría de los casos, estos acuerdos implican relaciones contractuales limitadas a poner la etiqueta de [!DNL Audience Manager] contenedor en el sitio del socio para facilitar la recopilación y el intercambio de datos.

Un ejemplo de recopilación y remercadotecnia de datos de terceros podría consistir en que un comerciante de ropa recopile datos sobre sus productos y luego comparta esa información con asociados clave. En este caso, el minorista podría ofrecer diferentes publicidades en un sitio de [!DNL Audience Manager] socios para los consumidores que elijan varios colores y tamaños de chaqueta.

![](assets/shopping-cart-traits.png)

## Third-Party Data Collection {#third-party-data}

Los datos de terceros son información recopilada y compartida por proveedores externos a [!DNL Audience Manager].

Los datos de terceros se pueden utilizar para calificar los datos existentes [!UICONTROL segments] (por ejemplo, edad, ingresos del hogar, etc.), proporcionar datos que están en demanda pero que no están disponibles de otro modo, o utilizarse en modelos parecidos a los de una base de usuarios conocida a partir de datos de origen y de terceros. [!DNL Audience Manager] trabaja con muchos proveedores de datos de terceros y le ayudará a comprender el tipo de datos que estos proveedores de datos recopilan para que pueda realizar los acuerdos estratégicos adecuados con cada proveedor.

>[!NOTE]
>
>Para obtener una lista completa de los proveedores de datos de terceros admitidos por [!DNL Audience Manager], consulte el buscador de Audiencias de [Adobe](https://www.adobe-audience-finder.com/).

[!DNL Audience Manager] se integra con otros proveedores de datos en función de sus conjuntos de datos [!DNL APIs] y de su disponibilidad. La recopilación de datos funciona en tiempo real, a medida que un usuario navega por el sitio o a través de metodologías fuera de banda en las que los ID se sincronizan entre socios y los datos se transfieren entre servidores después de que un usuario abandona el sitio. En cualquier caso, [!DNL Audience Manager] los clientes obtienen la ventaja de tener datos de terceros sincronizados en nuestra plataforma, lo que significa que cada cliente, o dominio, no tiene que realizar su propia sincronización. Esto ayuda a aumentar el alcance y reduce las llamadas al servidor desde la página.

## Asociados de Negocios de Coincidencia {#match-partners}

Muchos clientes eligen trabajar con socios de coincidencia de datos de terceros. Estas entidades tienen relaciones con sitios que tienen requisitos de registro y pueden procesar archivos de datos de clientes al hacerlos coincidir (en tiempo real) según su red de registro.

![coincidencia de proveedor de datos](assets/data-provider-match.png)
