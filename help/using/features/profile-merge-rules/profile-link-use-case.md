---
description: Recomendaciones y casos de uso para la resegmentación de segmentos y la cualificación de segmentos personalizados con el gráfico del dispositivo Vínculo de Perfil.
seo-description: Recomendaciones y casos de uso para la resegmentación de segmentos y la cualificación de segmentos personalizados con el gráfico del dispositivo Vínculo de Perfil.
seo-title: Casos de uso de Device Graph de vínculo de Perfil
solution: Audience Manager
title: Casos de uso de Device Graph de vínculo de Perfil
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 1%

---


# Casos de uso de Device Graph de vínculo de Perfil {#profile-link-device-graph-use-cases}

Recomendaciones y casos de uso para la resegmentación de segmentos y la cualificación de segmentos personalizados con el [!UICONTROL Profile Link Device Graph].

## Recomendaciones {#recommendations}

Considere el gráfico del [!UICONTROL Profile Link] dispositivo para campañas que:

* Tener un alto nivel de autenticación en sus propiedades digitales. Utilice una opción [de gráfico de dispositivos](merge-rule-definitions.md#device-options) externos si tiene una pequeña cantidad de usuarios autenticados.
* Requiere una segmentación precisa de audiencias conocidas. El [!UICONTROL Profile Link Device Graph] se crea con datos autenticados de origen.
* Destinatario audiencias conocidas en sus estados autenticados y no autenticados en tiempo real.

![](assets/merge-rule-triangle2.png)

## Targeting cruzado de dispositivos {#cross-device-personalization}

Supongamos que John posee tres dispositivos que utiliza regularmente para buscar ofertas de paquetes de vacaciones: su portátil ([!DNL Device 1]), su smartphone ([!DNL Device 2]) y su tablet ([!DNL Device 3]). Sin embargo, John utiliza sus dispositivos para buscar diferentes artículos de las ofertas de paquetes:

* Usa su laptop para buscar vuelos;
* Usa su smartphone para buscar hoteles;
* Utiliza su tableta para buscar visitas guiadas.

Incluso si John no está autenticado en los tres dispositivos mencionados anteriormente, mediante la regla **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]** , un proveedor de paquetes de vacaciones puede asociar estos dispositivos al perfil autenticado de John, suponiendo que fue la última persona en autenticarse en los tres dispositivos.

![último dispositivo-gráfico](assets/last-device-graph.png)

Dado que Audience Manager califica todos los perfiles de dispositivos que participaron en la combinación de perfiles para un segmento, los tres perfiles de dispositivos se segmentan. El [!UICONTROL Profile Link Device Graph] permite que el Audience Manager observe el comportamiento en los tres dispositivos y califique cada dispositivo para un segmento para el que ningún perfil de dispositivo se califica por sí solo.

Esto [!UICONTROL Profile Merge Rule] permite a los especialistas en marketing ofrecer una experiencia uniforme a todos los dispositivos propiedad de una persona, en función de la actividad del usuario en lugar de la actividad del dispositivo individual.

![personalización entre dispositivos](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Ejemplos de uso de los Gráficos de dispositivos externos](external-graph-use-cases.md)
>* [Casos generales de uso de las reglas de combinación de Perfiles](merge-rule-targeting-options.md)
>* [Preguntas más frecuentes sobre las reglas de combinación de Perfiles](../../faq/faq-profile-merge.md)

