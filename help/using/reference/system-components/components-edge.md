---
description: Audience Manager utiliza topologías distribuidas y de computación de borde para satisfacer las demandas de nuestros sistemas por fuentes externas.
seo-description: Audience Manager uses distributed, edge-computing topologies to meet the demands placed on our systems by external sources.
seo-title: Understanding the Edge Data Center
solution: Audience Manager
title: Explicación del centro de datos de Edge
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: System Components
exl-id: 28958b49-3075-4601-9271-ef2913721a66
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 4%

---

# Explicación del centro de datos de Edge{#understanding-the-edge-data-center}

Audience Manager utiliza topologías distribuidas y de computación de borde para satisfacer las demandas de nuestros sistemas por fuentes externas.

## Conceptos básicos del centro de datos Edge {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

La informática perimetral proporciona un rendimiento mejorado en respuesta a una demanda difusa en todo Internet, ya que el &quot;perímetro&quot; en sí es un límite global. Esto significa que [!DNL Audience Manager] coloca el procesamiento de forma dinámica más cerca de los orígenes de la demanda y devuelve los datos por la ruta más corta posible. La informática de Edge ayuda a mantener el rendimiento del sitio, lo que, a su vez, preserva la experiencia del usuario en el sitio web. El centro de datos Edge es una puerta de enlace clave para mover datos dentro y fuera de [!DNL Audience Manager].

El [!DNL Audience Manager] el centro de datos Edge incluye:

* **Servidores principales:** Estos son los principales [!DNL Audience Manager] sistemas. Actualizan y proporcionan datos a los servidores Edge de.

* **Servidores Edge:** Normalmente, se trata de servidores de aplicaciones o web. Se sientan en el límite entre [!DNL Audience Manager] e Internet. Servidores Edge, como [!DNL DCS] En los sistemas Akamai, normalmente gestiona los datos y las solicitudes que entran y salen de [!DNL Audience Manager].

* **Equilibradores de carga:** Administre las demandas de procesamiento/computación desiguales inherentes a las aplicaciones de Internet. Estos equilibradores evitan que los clústeres de servidores se sobrecarguen mientras otros permanecen inactivos.

El diagrama siguiente ilustra el entorno del centro de datos perimetral Audience Manager.

![](assets/edge_data_center.png)

## Distribución geográfica y equilibrio de carga {#geo-dist-balance}

Consulte la [!DNL DCS] sección en [Componentes de recopilación de datos](../../reference/system-components/components-data-collection.md).
