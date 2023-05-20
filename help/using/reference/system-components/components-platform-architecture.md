---
description: Este mapa contiene los principales sistemas Audience Manager. Representa visualmente cómo los datos fluyen hacia, desde y entre los componentes del Audience Manager.
seo-description: This map contains the major Audience Manager systems. It visually represents how data flows into, out of, and among Audience Manager components.
seo-title: Platform Architecture  Data Flow Map
solution: Audience Manager
title: Mapa del flujo de datos de arquitectura de plataforma
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: System Components
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 2%

---

# Arquitectura de plataforma: mapa del flujo de datos{#platform-architecture-data-flow-map}

Este mapa contiene los principales sistemas Audience Manager. Representa visualmente cómo los datos fluyen hacia, desde y entre los componentes del Audience Manager.

## Cómo leer este mapa {#compmap}

<!-- 

c_compmap.xml

 -->

En el mapa, el cuadro gris contiene [!DNL Audience Manager] sistemas. Algunos componentes son completamente internos y otros se sientan en el límite entre [!DNL Audience Manager] y el mundo exterior. Como un [!DNL Audience Manager] cliente, los componentes internos suelen ser transparentes o inaccesibles. Sin embargo, a veces puede interactuar con estos sistemas a través de la interfaz de usuario o las integraciones de datos. Los sistemas del extremo del cuadro recopilan y envían datos entre [!DNL Audience Manager] y el mundo exterior.

Los colores definen el tipo de datos que fluyen dentro y fuera de [!DNL Audience Manager]. Verde son los datos del cliente, azul son los datos del cliente (personas que visitan el sitio) y naranja son los datos utilizados para el sistema de informes.

Para obtener descripciones del sistema y resúmenes, consulte los datos [acción](../../reference/system-components/components-data-action.md), [colección](../../reference/system-components/components-data-collection.md), [procesamiento](../../reference/system-components/components-data-processing.md), y [administración de etiquetas](../../reference/system-components/components-tag-management.md) secciones.

![](assets/flowmap.png)
