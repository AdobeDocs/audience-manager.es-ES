---
description: Recomendaciones y casos de uso para la resegmentación de segmentos y la cualificación de segmentos personalizados con el gráfico del dispositivo Vínculo de perfil.
seo-description: Recomendaciones y casos de uso para la resegmentación de segmentos y la cualificación de segmentos personalizados con el gráfico del dispositivo Vínculo de perfil.
seo-title: Casos de uso de Device Graph de vínculo de perfil
solution: Audience Manager
title: Casos de uso de Device Graph de vínculo de perfil
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# Casos de uso de Device Graph de vínculo de perfil {#profile-link-device-graph-use-cases}

Recomendaciones y casos de uso para la resegmentación de segmentos y la cualificación de segmentos personalizados con el [!UICONTROL Profile Link Device Graph].

## Recomendaciones {#recommendations}

Considere el gráfico del [!UICONTROL Profile Link] dispositivo para campañas que:

* Tener un alto nivel de autenticación en sus propiedades digitales. Utilice una opción [de gráfico de dispositivos](merge-rule-definitions.md#device-options) externos si tiene una pequeña cantidad de usuarios autenticados.
* Requiere una segmentación precisa de las audiencias conocidas. El [!UICONTROL Profile Link Device Graph] se crea con datos autenticados de origen.
* Diríjase a audiencias conocidas en sus estados autenticados y no autenticados en tiempo real.

![](assets/merge-rule-triangle2.png)

## Segmentación entre dispositivos {#cross-device-personalization}

Supongamos que John posee tres dispositivos que utiliza regularmente para buscar ofertas de paquetes de vacaciones: su portátil ([!DNL Device 1]), su smartphone ([!DNL Device 2]) y su tablet ([!DNL Device 3]). Sin embargo, John utiliza sus dispositivos para buscar diferentes artículos de las ofertas de paquetes:

* Usa su laptop para buscar vuelos;
* Usa su smartphone para buscar hoteles;
* Utiliza su tableta para buscar visitas guiadas.

Incluso si John no está autenticado en los tres dispositivos mencionados anteriormente, mediante la regla **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]** , un proveedor de paquetes de vacaciones puede asociar estos dispositivos al perfil autenticado de John, suponiendo que fue la última persona en autenticarse en los tres dispositivos.

![último dispositivo-gráfico](assets/last-device-graph.png)

Dado que Audience Manager califica todos los perfiles de dispositivo que participaron en la combinación de perfiles para un segmento, los tres perfiles de dispositivo se segmentan. Esto [!UICONTROL Profile Link Device Graph] permite a Audience Manager observar el comportamiento en los tres dispositivos y calificar cada dispositivo para un segmento para el que ningún perfil de dispositivo por sí solo cumple los requisitos.

Esto [!UICONTROL Profile Merge Rule] permite a los especialistas en marketing ofrecer una experiencia uniforme a todos los dispositivos propiedad de una persona, en función de la actividad del usuario en lugar de la actividad individual del dispositivo.

![personalización entre dispositivos](assets/cross-device-personalization.png)

>[!MORE_LIKE_THIS]
>
>* [Ejemplos de uso de los Gráficos de dispositivos externos](external-graph-use-cases.md)
>* [Casos generales de uso de reglas de combinación de perfiles](merge-rule-targeting-options.md)
>* [Preguntas más frecuentes sobre las reglas de combinación de perfiles](../../faq/faq-profile-merge.md)

