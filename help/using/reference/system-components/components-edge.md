---
description: El Audience Manager utiliza topologías distribuidas y de vanguardia para satisfacer las exigencias que las fuentes externas imponen a nuestros sistemas.
seo-description: El Audience Manager utiliza topologías distribuidas y de vanguardia para satisfacer las exigencias que las fuentes externas imponen a nuestros sistemas.
seo-title: Explicación del centro de datos de Edge
solution: Audience Manager
title: Explicación del centro de datos de Edge
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---


# Explicación del centro de datos de Edge{#understanding-the-edge-data-center}

El Audience Manager utiliza topologías distribuidas y de vanguardia para satisfacer las exigencias que las fuentes externas imponen a nuestros sistemas.

## Conceptos básicos de Edge Data Center {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

La informática perimetral ofrece un rendimiento mejorado en respuesta a una demanda difusa en toda Internet, ya que el &quot;borde&quot; en sí es un límite global. Esto significa que [!DNL Audience Manager] coloca dinámicamente el procesamiento más cerca de las fuentes de demanda y devuelve datos por la ruta más corta posible. La informática de Edge ayuda a mantener el rendimiento del sitio, lo que, a su vez, preserva la experiencia del usuario en el sitio web. El centro de datos Edge es una puerta de enlace clave para mover datos de [!DNL Audience Manager].

El centro de datos perimetral [!DNL Audience Manager] incluye:

* **Servidores principales:** Estos son los principales  [!DNL Audience Manager] sistemas. Actualizan y proporcionan datos a los servidores Edge.

* **Servidores Edge:** normalmente son servidores Web o de aplicaciones. Se sientan en el límite entre [!DNL Audience Manager] e Internet. Los servidores Edge, como los sistemas [!DNL DCS] o Akamai, generalmente administran datos y solicitudes que entran y salen de [!DNL Audience Manager].

* **Equilibradores de carga:** Administre las demandas desiguales de procesamiento/computación inherentes a las aplicaciones de Internet. Estos equilibradores impiden que los clústeres de servidores se sobrecarguen mientras que otros permanecen inactivos.

En el diagrama siguiente se ilustra el entorno del centro de datos perimetral Audience Manager.

![](assets/edge_data_center.png)

## Distribución geográfica y equilibrio de carga {#geo-dist-balance}

Consulte la sección [!DNL DCS] en [Componentes de recopilación de datos](../../reference/system-components/components-data-collection.md).
