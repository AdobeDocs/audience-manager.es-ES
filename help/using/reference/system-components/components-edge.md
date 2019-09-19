---
description: Audience Manager utiliza topologías informáticas distribuidas y de vanguardia para satisfacer las demandas que las fuentes externas imponen a nuestros sistemas.
seo-description: Audience Manager utiliza topologías informáticas distribuidas y de vanguardia para satisfacer las demandas que las fuentes externas imponen a nuestros sistemas.
seo-title: Explicación del centro de datos de Edge
solution: Audience Manager
title: Explicación del centro de datos de Edge
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Explicación del centro de datos de Edge{#understanding-the-edge-data-center}

Audience Manager utiliza topologías informáticas distribuidas y de vanguardia para satisfacer las demandas que las fuentes externas imponen a nuestros sistemas.

## Conceptos básicos de Edge Data Center {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

La informática perimetral ofrece un rendimiento mejorado en respuesta a una demanda difusa en toda Internet, ya que el "borde" en sí es un límite global. Esto significa que coloca [!DNL Audience Manager] dinámicamente el procesamiento más cerca de las fuentes de demanda y devuelve los datos por la ruta más corta posible. La informática de Edge ayuda a mantener el rendimiento del sitio, lo que, a su vez, preserva la experiencia del usuario en el sitio web. El centro de datos de Edge es una puerta de enlace clave para mover y extraer datos de [!DNL Audience Manager].

El centro de datos [!DNL Audience Manager] edge incluye:

* **** Servidores principales: Estos son los principales [!DNL Audience Manager] sistemas. Actualizan y proporcionan datos a los servidores Edge.

* **** Servidores Edge: Generalmente, son servidores Web y/o de aplicaciones. Se sientan en el límite entre [!DNL Audience Manager] e Internet. Los servidores Edge, como los sistemas [!UICONTROL DCS] o Akamai, generalmente administran datos y solicitudes que entran y salen de [!DNL Audience Manager].

* **** Equilibradores de carga: Administre las demandas desiguales de procesamiento y computación inherentes a las aplicaciones de Internet. Estos equilibradores impiden que los clústeres de servidores se sobrecarguen mientras que otros permanecen inactivos.

El diagrama siguiente ilustra el entorno del centro de datos perimetral de Audience Manager.

![](assets/edge_data_center.png)

## Distribución geográfica y equilibrio de carga {#geo-dist-balance}

Consulte la [!UICONTROL DCS] sección en Componentes [de recopilación](../../reference/system-components/components-data-collection.md)de datos.
