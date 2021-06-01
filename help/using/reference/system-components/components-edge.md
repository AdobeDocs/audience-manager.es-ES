---
description: El Audience Manager utiliza topologías distribuidas y de vanguardia para satisfacer las demandas que las fuentes externas imponen a nuestros sistemas.
seo-description: El Audience Manager utiliza topologías distribuidas y de vanguardia para satisfacer las demandas que las fuentes externas imponen a nuestros sistemas.
seo-title: Explicación del centro de datos de Edge
solution: Audience Manager
title: Explicación del centro de datos de Edge
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: 'Componentes del sistema '
exl-id: 28958b49-3075-4601-9271-ef2913721a66
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 6%

---

# Explicación del centro de datos de Edge{#understanding-the-edge-data-center}

El Audience Manager utiliza topologías distribuidas y de vanguardia para satisfacer las demandas que las fuentes externas imponen a nuestros sistemas.

## Conceptos básicos del centro de datos de Edge {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

La computación perimetral proporciona un rendimiento mejorado en respuesta a una demanda difusa en todo Internet porque la &quot;ventaja&quot; en sí es un límite global. Esto significa que [!DNL Audience Manager] coloca dinámicamente el procesamiento más cerca de las fuentes de demanda y devuelve los datos por la ruta más corta posible. La informática perimetral ayuda a mantener el rendimiento del sitio, lo que a su vez preserva la experiencia del usuario en el sitio web. El centro de datos perimetrales es una puerta de enlace clave para mover datos dentro y fuera de [!DNL Audience Manager].

El [!DNL Audience Manager] centro de datos perimetrales incluye:

* **Servidores principales:** Estos son los principales  [!DNL Audience Manager] sistemas. Actualizan y proporcionan datos a los servidores Edge.

* **Servidores Edge:** normalmente son servidores web o de aplicaciones. Se sientan en el límite entre [!DNL Audience Manager] e Internet. Los servidores Edge, como los sistemas [!DNL DCS] o Akamai, suelen gestionar los datos y las solicitudes que entran y salen de [!DNL Audience Manager].

* **Balanceadores de carga:** Administre las demandas desiguales de computación/procesamiento inherentes a las aplicaciones de Internet. Estos equilibradores impiden que los clústeres de servidores se sobrecarguen mientras que otros permanecen inactivos.

El diagrama siguiente ilustra el entorno del centro de datos perimetral del Audience Manager.

![](assets/edge_data_center.png)

## Distribución geográfica y equilibrio de carga {#geo-dist-balance}

Consulte la sección [!DNL DCS] en [Componentes de recopilación de datos](../../reference/system-components/components-data-collection.md).
