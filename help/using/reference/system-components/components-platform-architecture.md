---
description: Este mapa contiene los principales sistemas de Audience Manager. Representa visualmente cómo fluyen los datos entre los componentes del Audience Manager, entre ellos y dentro de ellos.
seo-description: Este mapa contiene los principales sistemas de Audience Manager. Representa visualmente cómo fluyen los datos entre los componentes del Audience Manager, entre ellos y dentro de ellos.
seo-title: Mapa del flujo de datos de la arquitectura de plataforma
solution: Audience Manager
title: Mapa del flujo de datos de la arquitectura de plataforma
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: 'Componentes del sistema '
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---

# Arquitectura de plataforma: mapa del flujo de datos{#platform-architecture-data-flow-map}

Este mapa contiene los principales sistemas de Audience Manager. Representa visualmente cómo fluyen los datos entre los componentes del Audience Manager, entre ellos y dentro de ellos.

## Leer este mapa {#compmap}

<!-- 

c_compmap.xml

 -->

En el mapa, el cuadro gris contiene [!DNL Audience Manager] sistemas. Algunos componentes son completamente internos y otros se encuentran en el límite entre [!DNL Audience Manager] y el mundo exterior. Como cliente de [!DNL Audience Manager], los componentes internos suelen ser transparentes o inaccesibles. Sin embargo, a veces puede interactuar con estos sistemas a través de la interfaz de usuario o integraciones de datos. Los sistemas ubicados en el borde del cuadro recopilan y envían datos entre [!DNL Audience Manager] y el mundo exterior.

Los colores definen el tipo de datos que entran y salen de [!DNL Audience Manager]. El verde son los datos del cliente, el azul los datos del cliente (personas que visitan el sitio) y el naranja los datos utilizados para los informes.

Para obtener descripciones y resúmenes del sistema, consulte las secciones data [action](../../reference/system-components/components-data-action.md), [collection](../../reference/system-components/components-data-collection.md), [processing](../../reference/system-components/components-data-processing.md) y [tag management](../../reference/system-components/components-tag-management.md).

![](assets/flowmap.png)
