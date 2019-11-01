---
description: La dessegmentación describe los procesos que descalifican y eliminan perfiles de dispositivos de los segmentos. Su capacidad para eliminar un perfil de dispositivo de un segmento depende de la opción de dispositivo utilizada para crear una regla de combinación de perfiles.
seo-description: La dessegmentación describe los procesos que descalifican y eliminan perfiles de dispositivos de los segmentos. Su capacidad para eliminar un perfil de dispositivo de un segmento depende de la opción de dispositivo utilizada para crear una regla de combinación de perfiles.
seo-title: Reglas de combinación de perfiles y procesos de dessegmentación de dispositivos
solution: Audience Manager
title: Reglas de combinación de perfiles y procesos de dessegmentación de dispositivos
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Reglas de combinación de perfiles y procesos de dessegmentación de dispositivos {#profile-merge-rules-and-device-un-segmentation-processes}

La dessegmentación describe los procesos que descalifican y eliminan perfiles de dispositivos de los segmentos. Su capacidad para eliminar un perfil de dispositivo de un segmento depende de la opción de dispositivo utilizada para crear un [!UICONTROL Profile Merge Rule].

## Opciones de dispositivo disponibles {#device-options}

Como recordatorio, los [!UICONTROL Device Options] están disponibles en la [!UICONTROL Profile Merge Rules Setup] sección al crear o editar un [!UICONTROL Profile Merge Rule].

## Opción de perfil de dispositivo actual y dessegmentación del dispositivo {#current-device-profile-options}

**[!UICONTROL Device Profile]** es la opción de perfil de dispositivo predeterminada para un [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] Puede eliminar un perfil de dispositivo de un segmento cuando [!UICONTROL Profile Merge Rule] utilice la **[!UICONTROL Device Profile]** opción. En estas condiciones, la dessegmentación se produce cuando:

* El perfil del dispositivo ha estado inactivo durante 120 días. Un proceso semanal de limpieza de datos elimina los perfiles de dispositivo inactivos de los segmentos.
* El dispositivo ya no cumple los requisitos para un segmento porque las actualizaciones o los cambios en el perfil del dispositivo lo descalifican. Esto sucede cuando cambian los criterios de calificación de segmentos, o cuando se aplica un [!DNL AND NOT] operador a una regla de segmento, o se especifican condiciones de [actualización y frecuencia](../segments/recency-and-frequency.md) que utilizan la configuración menor o igual que. Los casos de uso se describen en la documentación de Supresión [entre dispositivos](instant-cross-device-suppression.md) instantánea.

![solo dispositivo](assets/device-only.png)

## Sin opción de dispositivo y sin segmentación de dispositivos {#no-device-option}

[!DNL Audience Manager] Puede quitar un ID entre dispositivos de un segmento cuando [!UICONTROL Profile Merge Rule] utilice la opción **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** . En estas condiciones, la dessegmentación se produce cuando el ID entre dispositivos ya no cumple los requisitos para un segmento porque las actualizaciones o los cambios en el perfil entre dispositivos lo descalifican. Esto sucede cuando cambian los criterios de calificación de segmentos, o cuando se aplica un [!UICONTROL AND NOT] operador a una regla de segmento, o se especifican condiciones de [actualización y frecuencia](../segments/recency-and-frequency.md) que utilizan la configuración menor o igual que. Los casos de uso se describen en la documentación de Supresión [entre dispositivos](instant-cross-device-suppression.md) instantánea.

![](assets/current-no-device.png)

## Opciones de Device Graph y dessegmentación de dispositivos {#device-graph-options-unsegmentation}

[!DNL Audience Manager] Puede eliminar varios perfiles de dispositivo de un segmento cuando [!UICONTROL Profile Merge Rule] utilice una opción de gráfico de dispositivo. La dessegmentación se produce cuando el perfil combinado del dispositivo del gráfico del dispositivo ya no cumple los requisitos para el segmento porque las actualizaciones o los cambios realizados en este perfil combinado lo descalifican del segmento. Esto sucede cuando cambian los criterios de calificación de segmentos, o cuando se aplica un [!UICONTROL AND NOT] operador a una regla de segmento, o se especifican condiciones de [actualización y frecuencia](../segments/recency-and-frequency.md) que utilizan la configuración menor o igual que. Los casos de uso se describen en la documentación de Supresión [entre dispositivos](instant-cross-device-suppression.md) instantánea.

>[!NOTE]
>
>**Límite de 100 dispositivos para la evaluación y descalificación**de segmentos.
>Audience Manager combina hasta 100 dispositivos al evaluar segmentos con una regla de combinación de perfiles que utiliza un gráfico de dispositivos. Audience Manager evalúa el dispositivo actual y hasta 99 dispositivos vinculados al dispositivo actual mediante un perfil [](../../reference/visitor-authentication-states.md) autenticado (ID entre dispositivos). Si se emite la señal de dessegmentación, el dispositivo actual y los dispositivos adicionales se eliminarán del segmento en el destino.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [Preguntas más frecuentes sobre las reglas de combinación de perfiles y Device Graph](../../faq/faq-profile-merge.md)
>* [Eliminación instantánea entre dispositivos](instant-cross-device-suppression.md)

