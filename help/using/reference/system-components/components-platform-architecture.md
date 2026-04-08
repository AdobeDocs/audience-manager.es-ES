---
description: Este mapa contiene los principales sistemas de Audience Manager. Representa visualmente cómo fluyen los datos hacia y desde los componentes de Audience Manager, así como entre ellos.
seo-description: This map contains the major Audience Manager systems. It visually represents how data flows into, out of, and among Audience Manager components.
seo-title: Platform Architecture  Data Flow Map
solution: Audience Manager
title: Mapa del flujo de datos de arquitectura de plataforma
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: System Components
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
TQID: https://experienceleague.adobe.com/AuYZKnavjMq-XyilPWgEeWASzFB3K5HuAqx-wsE-H9k
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 170
ht-degree: 0%

---

# Arquitectura de plataforma: mapa del flujo de datos{#platform-architecture-data-flow-map}

Este mapa contiene los principales sistemas de Audience Manager. Representa visualmente cómo fluyen los datos hacia y desde los componentes de Audience Manager, así como entre ellos.

## Cómo leer este mapa {#compmap}

<!-- 

c_compmap.xml

 -->

En el mapa, el cuadro gris contiene [!DNL Audience Manager] sistemas. Algunos componentes son completamente internos y otros se sitúan en el límite entre [!DNL Audience Manager] y el mundo exterior. Como cliente de [!DNL Audience Manager], los componentes internos suelen ser transparentes o inaccesibles. Sin embargo, a veces puede interactuar con estos sistemas a través de la interfaz de usuario o las integraciones de datos. Los sistemas del extremo del cuadro recopilan y envían datos entre [!DNL Audience Manager] y el mundo exterior.

Los colores definen el tipo de datos que fluyen dentro y fuera de [!DNL Audience Manager]. Verde son los datos del cliente, azul son los datos del cliente (personas que visitan el sitio) y naranja son los datos utilizados para el sistema de informes.

Para obtener descripciones y resúmenes del sistema, consulte las secciones de datos [action](../../reference/system-components/components-data-action.md), [collection](../../reference/system-components/components-data-collection.md), [processing](../../reference/system-components/components-data-processing.md) y [tag management](../../reference/system-components/components-tag-management.md).

![](assets/flowmap.png)
