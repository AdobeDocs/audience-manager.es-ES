---
description: Este mapa contiene los principales sistemas de Audience Manager. Representa visualmente cómo los datos fluyen dentro, fuera y entre los componentes del Audience Manager.
seo-description: Este mapa contiene los principales sistemas de Audience Manager. Representa visualmente cómo los datos fluyen dentro, fuera y entre los componentes del Audience Manager.
seo-title: Mapa del flujo de datos de la arquitectura de plataformas
solution: Audience Manager
title: Mapa del flujo de datos de la arquitectura de plataformas
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 2%

---


# Arquitectura de plataforma: mapa del flujo de datos{#platform-architecture-data-flow-map}

Este mapa contiene los principales sistemas de Audience Manager. Representa visualmente cómo los datos fluyen dentro, fuera y entre los componentes del Audience Manager.

## Cómo leer este mapa {#compmap}

<!-- 

c_compmap.xml

 -->

En el mapa, el cuadro gris contiene [!DNL Audience Manager] sistemas. Algunos componentes son completamente internos y otros se encuentran en el límite entre [!DNL Audience Manager] y el mundo exterior. Como cliente [!DNL Audience Manager], los componentes internos suelen ser transparentes o inaccesibles. Sin embargo, a veces puede interactuar con estos sistemas a través de la interfaz de usuario o integraciones de datos. Los sistemas que se encuentran en el borde de la caja recopilan y envían datos entre [!DNL Audience Manager] y el mundo exterior.

Los colores definen el tipo de datos que entran y salen de [!DNL Audience Manager]. El verde son los datos del cliente, el azul los datos del cliente (personas que visitan el sitio) y el naranja los datos utilizados para el sistema de informes.

Para obtener descripciones y resúmenes del sistema, consulte las secciones de datos [acción](../../reference/system-components/components-data-action.md), [recopilación](../../reference/system-components/components-data-collection.md), [procesamiento](../../reference/system-components/components-data-processing.md) y [administración de etiquetas](../../reference/system-components/components-tag-management.md).

![](assets/flowmap.png)

