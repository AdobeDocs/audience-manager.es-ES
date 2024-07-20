---
description: Recommendations y casos de uso para retargeting de segmentos y calificación de segmentos personalizada con el gráfico del dispositivo de enlace de perfil.
seo-description: Recommendations and use cases for segment retargeting and personalized segment qualification with the Profile Link device graph.
seo-title: Profile Link Device Graph Use Cases
solution: Audience Manager
title: Casos de uso de Device Graph de enlace de perfil
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 4%

---

# Casos de uso de Device Graph de enlace de perfil {#profile-link-device-graph-use-cases}

Recommendations y casos de uso para resegmentación de segmentos y calificación de segmentos personalizada con [!UICONTROL Profile Link Device Graph].

## Las actividades de {#recommendations}

Considere el gráfico del dispositivo [!UICONTROL Profile Link] para las campañas que:

* Tener un alto nivel de autenticación en sus propiedades digitales. Use un gráfico de dispositivos externos [opción](merge-rule-definitions.md#device-options) si tiene una pequeña cantidad de usuarios autenticados.
* Requiere segmentación precisa de audiencias conocidas. [!UICONTROL Profile Link Device Graph] se ha creado usando datos autenticados de origen.
* Segmente audiencias conocidas en sus estados autenticado y no autenticado en tiempo real.

![](assets/merge-rule-triangle2.png)

## Segmentación entre dispositivos {#cross-device-personalization}

Supongamos que John posee tres dispositivos que usa con regularidad para buscar ofertas de paquetes de vacaciones: su portátil ([!DNL Device 1]), su smartphone ([!DNL Device 2]) y su tableta ([!DNL Device 3]). Sin embargo, John utiliza sus dispositivos para buscar diferentes elementos de las ofertas de paquetes:

* Usa su portátil para buscar vuelos;
* Usa su smartphone para buscar hoteles;
* Usa su tableta para buscar visitas guiadas.

Incluso si John no está autenticado en los tres dispositivos mencionados anteriormente, mediante la regla **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]**, un proveedor de paquetes de vacaciones puede asociar estos dispositivos al perfil autenticado de John, suponiendo que fuera la última persona en autenticarse en los tres dispositivos.

![last-device-graph](assets/last-device-graph.png)

Dado que Audience Manager clasifica todos los perfiles de dispositivo que participaron en la combinación de perfiles de un segmento, los tres perfiles de dispositivo se segmentan. El [!UICONTROL Profile Link Device Graph] permite al Audience Manager observar el comportamiento en los tres dispositivos y clasificar cada dispositivo para un segmento para el que ningún perfil de dispositivo se califica por sí solo.

Este(a) [!UICONTROL Profile Merge Rule] permite que los especialistas en mercadotecnia brinden una experiencia coherente a todos los dispositivos propiedad de una persona, en función de la actividad del usuario en lugar de la actividad del dispositivo individual.

![personalización entre dispositivos](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Ejemplos de uso de los Gráficos de dispositivos externos](external-graph-use-cases.md)
>* [Casos generales de uso de las reglas de combinación de Perfiles](merge-rule-targeting-options.md)
>* [Preguntas frecuentes sobre reglas de combinación de perfiles](../../faq/faq-profile-merge.md)
