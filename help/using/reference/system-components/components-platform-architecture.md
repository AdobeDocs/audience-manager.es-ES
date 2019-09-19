---
description: Este mapa contiene los principales sistemas de Audience Manager. Representa visualmente el flujo de datos entre los componentes de Audience Manager y dentro de ellos.
seo-description: Este mapa contiene los principales sistemas de Audience Manager. Representa visualmente el flujo de datos entre los componentes de Audience Manager y dentro de ellos.
seo-title: Mapa del flujo de datos de la arquitectura de plataformas
solution: Audience Manager
title: Mapa del flujo de datos de la arquitectura de plataformas
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Arquitectura de plataforma: Mapa del flujo de datos{#platform-architecture-data-flow-map}

Este mapa contiene los principales sistemas de Audience Manager. Representa visualmente el flujo de datos entre los componentes de Audience Manager y dentro de ellos.

## Cómo leer este mapa {#compmap}

<!-- 

c_compmap.xml

 -->

En el mapa, el cuadro gris contiene [!DNL Audience Manager] sistemas. Algunos componentes son completamente internos y otros están en la frontera entre [!DNL Audience Manager] y el mundo exterior. Como [!DNL Audience Manager] cliente, los componentes internos suelen ser transparentes o inaccesibles. Sin embargo, a veces puede interactuar con estos sistemas a través de la interfaz de usuario o integraciones de datos. Los sistemas situados en el borde de la caja recopilan y envían datos entre [!DNL Audience Manager] y el mundo exterior.

Los colores definen el tipo de datos que entran y salen de [!DNL Audience Manager]. El verde son los datos del cliente, el azul los datos del cliente (personas que visitan el sitio) y el naranja los datos utilizados para los informes.

Para obtener descripciones y resúmenes del sistema, consulte las secciones de [acción](../../reference/system-components/components-data-action.md), [recopilación](../../reference/system-components/components-data-collection.md), [procesamiento](../../reference/system-components/components-data-processing.md)y administración [de](../../reference/system-components/components-tag-management.md) etiquetas de datos.

![](assets/flowmap.png)

