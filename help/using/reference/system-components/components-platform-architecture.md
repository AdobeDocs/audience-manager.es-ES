---
description: Este mapa contiene los principales sistemas de Audience Manager. Representa visualmente cómo fluyen, extraen y entre los componentes de Audience Manager los datos.
seo-description: Este mapa contiene los principales sistemas de Audience Manager. Representa visualmente cómo fluyen, extraen y entre los componentes de Audience Manager los datos.
seo-title: Mapa de flujo de datos de arquitectura de plataforma
solution: Audience Manager
title: Mapa de flujo de datos de arquitectura de plataforma
uuid: d 845 af 1 d-f 448-4 f 4 c -948 e-b 2 c 89 f 125086
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Platform Architecture: Data Flow Map{#platform-architecture-data-flow-map}

Este mapa contiene los principales sistemas de Audience Manager. Representa visualmente cómo fluyen, extraen y entre los componentes de Audience Manager los datos.

## How to read this map {#compmap}

<!-- 

c_compmap.xml

 -->

In the map, the gray box contains [!DNL Audience Manager] systems. Some components are completely internal and others sit on the boundary between [!DNL Audience Manager] and the outside world. As an [!DNL Audience Manager] customer, internal components are often transparent or inaccessible. Sin embargo, a veces puede interactuar con estos sistemas mediante la interfaz de usuario o integraciones de datos. Systems on the edge of the box collect and send data between [!DNL Audience Manager] and the outside world.

Colors define the type of data that flows in and out of [!DNL Audience Manager]. Verde es datos del cliente, azul es datos de clientes (personas que visitan el sitio) y naranja son datos utilizados para los informes.

For system descriptions and summaries see the data [action](../../reference/system-components/components-data-action.md), [collection](../../reference/system-components/components-data-collection.md), [processing](../../reference/system-components/components-data-processing.md), and [tag management](../../reference/system-components/components-tag-management.md) sections.

![](assets/flowmap.png)

