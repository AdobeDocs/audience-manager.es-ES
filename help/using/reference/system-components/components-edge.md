---
description: Audience Manager utiliza topologías distribuidas y de informática Edge para satisfacer las demandas realizadas en nuestros sistemas por fuentes externas.
seo-description: Audience Manager utiliza topologías distribuidas y de informática Edge para satisfacer las demandas realizadas en nuestros sistemas por fuentes externas.
seo-title: Explicación del Centro de datos Edge
solution: Audience Manager
title: Explicación del Centro de datos Edge
uuid: 4177 e 666-99 f 4-453 d -94 dd -058 c 6182 c 8 d 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Understanding the Edge Data Center{#understanding-the-edge-data-center}

Audience Manager utiliza topologías distribuidas y de informática Edge para satisfacer las demandas realizadas en nuestros sistemas por fuentes externas.

## Edge Data Center Basics {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

La informática Edge proporciona un rendimiento mejorado en respuesta a la demanda difusa en Internet porque el propio «edge» es un límite global. This means [!DNL Audience Manager] dynamically places processing closest to the sources of demand and returns data by the shortest possible path. La informática Edge ayuda a mantener el rendimiento del sitio, que a su vez conserva la experiencia del usuario en el sitio web. The edge data center is a key gateway for moving data in and out of [!DNL Audience Manager].

The [!DNL Audience Manager] edge data center includes:

* **Servidores principales:** Son [!DNL Audience Manager] los sistemas principales. Actualizan y proporcionan datos a los servidores Edge.

* **Servidores Edge:** Generalmente, son servidores web o de aplicación. They sit at the boundary between [!DNL Audience Manager] and the Internet. Edge servers, such as the [!UICONTROL DCS] or Akamai systems, typically handle data and requests flowing into and out of [!DNL Audience Manager].

* **Equilibradores de carga:** Administre las demandas de procesamiento y computación desiguales inherentes a las aplicaciones de Internet. Estos equilibradores evitan que se sobrecargue clústeres de servidores mientras que otros permanecen inactivos.

El siguiente diagrama ilustra el entorno del centro de datos Edge de Audience Manager.

![](assets/edge_data_center.png)

## Geographic Distribution and Load Balancing {#geo-dist-balance}

See the [!UICONTROL DCS] section in [Data Collection Components](../../reference/system-components/components-data-collection.md).
