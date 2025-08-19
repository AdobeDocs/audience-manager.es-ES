---
description: Recommendations y casos de uso para la reorientación segmento y la calificación de segmento personalizada con el gráfico de dispositivos Vínculo de perfil.
seo-description: Recommendations and use cases for segment retargeting and personalized segment qualification with the Profile Link device graph.
seo-title: Profile Link Device Graph Use Cases
solution: Audience Manager
title: Vínculo de perfil Casos de uso de Device Graph
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 4%

---

# Vínculo de perfil Casos de uso de Device Graph {#profile-link-device-graph-use-cases}

Recommendations y casos de uso para la reorientación segmento y la calificación de segmento personalizada con el [!UICONTROL Profile Link Device Graph].

## Las actividades de {#recommendations}

Tenga en cuenta el gráfico de dispositivos [!UICONTROL Profile Link] para campañas que:

* Tienen un alto nivel de autenticación en todas sus propiedades digitales. Utilice una [opción](merge-rule-definitions.md#device-options) de gráfico de dispositivos externo si tiene una pequeña cantidad de usuarios autenticados.
* Requieren un direccionamiento preciso de audiencias conocidas. El [!UICONTROL Profile Link Device Graph] se crea utilizando datos propios y autenticados.
* Target audiencias conocidas en todos sus estados autenticados y no autenticados en tiempo real.

![](assets/merge-rule-triangle2.png)

## Segmentación cruzada por dispositivo {#cross-device-personalization}

Digamos que John posee tres dispositivos que usa regularmente para búsqueda ofertas de paquetes de vacaciones: su computadora portátil ([!DNL Device 1]), su teléfono inteligente ([!DNL Device 2]) y su tableta ([!DNL Device 3]). Sin embargo, John usa su dispositivos para búsqueda diferentes artículos del paquete:

* Usa su computadora portátil para búsqueda para los vuelos;
* Usa su teléfono inteligente para búsqueda para hoteles;
* Usa su tableta para búsqueda visitas guiadas.

Incluso si John no está autenticado en los tres dispositivos mencionados anteriormente, mediante el **[!UICONTROL Last Authenticated Profiles]** uso del regla + **[!UICONTROL Profile Link Device Graph]** , un proveedor de paquetes de vacaciones puede asociar estos dispositivos al perfil autenticado de John, suponiendo que él fue la última persona en autenticarse en los tres dispositivos.

![último gráfico dispositivos](assets/last-device-graph.png)

Dado que Audience Manager califica a todos los dispositivos perfil que participaron en la perfil fusión para una segmento, los tres perfiles dispositivos están segmentados. Esto [!UICONTROL Profile Link Device Graph] Audience Manager permite observar el comportamiento en los tres dispositivos y calificar cada dispositivos para un segmento para el que ningún dispositivos perfil califica por sí solo.

Esto [!UICONTROL Profile Merge Rule] permite a los especialistas en marketing ofrecer un experiencia coherente a todas las dispositivos propiedad de una sola persona, en función del usuario actividad en lugar del dispositivos individual actividad.

![Cross-dispositivos-personalización](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Ejemplos de uso de los Gráficos de dispositivos externos](external-graph-use-cases.md)
>* [Casos generales de uso de las reglas de combinación de Perfiles](merge-rule-targeting-options.md)
>* [Preguntas más frecuentes sobre las reglas de combinación de perfiles](../../faq/faq-profile-merge.md)
