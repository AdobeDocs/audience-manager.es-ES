---
description: La dessegmentación describe los procesos que descalifican y eliminan perfiles de dispositivos de los segmentos. Su capacidad para eliminar un perfil de dispositivo de un segmento depende de la opción de dispositivo utilizada para crear una regla de combinación de Perfiles.
seo-description: La dessegmentación describe los procesos que descalifican y eliminan perfiles de dispositivos de los segmentos. Su capacidad para eliminar un perfil de dispositivo de un segmento depende de la opción de dispositivo utilizada para crear una regla de combinación de Perfiles.
seo-title: Reglas de combinación de Perfil y procesos de eliminación de la segmentación de dispositivos
solution: Audience Manager
title: Reglas de combinación de Perfil y procesos de eliminación de la segmentación de dispositivos
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 6%

---


# Reglas de combinación de Perfil y procesos de eliminación de la segmentación de dispositivos {#profile-merge-rules-and-device-un-segmentation-processes}

La dessegmentación describe los procesos que descalifican y eliminan perfiles de dispositivos de los segmentos. Su capacidad para eliminar un perfil de dispositivo de un segmento depende de la opción de dispositivo utilizada para crear un [!UICONTROL Profile Merge Rule].

## Opciones de dispositivo disponibles {#device-options}

Como recordatorio, [!UICONTROL Device Options] está disponible en la sección [!UICONTROL Profile Merge Rules Setup] cuando crea o edita un [!UICONTROL Profile Merge Rule].

## Opción de Perfil de dispositivos actual y dessegmentación de dispositivos {#current-device-profile-options}

**[!UICONTROL Device Profile]** es la opción de perfil de dispositivo predeterminada para un  [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] Puede eliminar un perfil de dispositivo de un segmento cuando  [!UICONTROL Profile Merge Rule] utilice la  **[!UICONTROL Device Profile]** opción. En estas condiciones, la dessegmentación se produce cuando:

* El perfil del dispositivo ha estado inactivo durante 120 días. Un proceso semanal de limpieza de datos elimina los perfiles inactivos del dispositivo de los segmentos.
* El dispositivo ya no cumple los requisitos para un segmento porque las actualizaciones o los cambios en el perfil del dispositivo lo descalifican. Esto sucede cuando cambian los criterios de calificación de segmentos o cuando se aplica un operador [!DNL AND NOT] a una regla de segmento, o se especifican [condiciones de actualización y frecuencia](../segments/recency-and-frequency.md) que utilizan la configuración menor o igual que. Los casos de uso se describen en la documentación de [Supresión instantánea entre dispositivos](instant-cross-device-suppression.md).

![solo dispositivo](assets/device-only.png)

## Sin opción de dispositivo y sin dessegmentación del dispositivo {#no-device-option}

[!DNL Audience Manager] Puede quitar un ID entre dispositivos de un segmento cuando  [!UICONTROL Profile Merge Rule] utilice la  **[!UICONTROL Current Authenticated Profiles]** +  **[!UICONTROL No Device Profile]** opción. En estas condiciones, la dessegmentación se produce cuando el ID entre dispositivos ya no cumple los requisitos para un segmento porque las actualizaciones o los cambios en el perfil entre dispositivos lo descalifican. Esto sucede cuando cambian los criterios de calificación de segmentos o cuando se aplica un operador [!UICONTROL AND NOT] a una regla de segmento, o se especifican [condiciones de actualización y frecuencia](../segments/recency-and-frequency.md) que utilizan la configuración menor o igual que. Los casos de uso se describen en la documentación de [Supresión instantánea entre dispositivos](instant-cross-device-suppression.md).

![](assets/current-no-device.png)

## Opciones de Device Graph y dessegmentación de dispositivos {#device-graph-options-unsegmentation}

[!DNL Audience Manager] Puede eliminar varios perfiles de dispositivo de un segmento cuando  [!UICONTROL Profile Merge Rule] utilice una opción de gráfico de dispositivo. La dessegmentación se produce cuando el perfil combinado del dispositivo del gráfico del dispositivo ya no cumple los requisitos para el segmento porque las actualizaciones o los cambios realizados en este perfil combinado lo descalifican del segmento. Esto sucede cuando cambian los criterios de calificación de segmentos o cuando se aplica un operador [!UICONTROL AND NOT] a una regla de segmento, o se especifican [condiciones de actualización y frecuencia](../segments/recency-and-frequency.md) que utilizan la configuración menor o igual que. Los casos de uso se describen en la documentación de [Supresión instantánea entre dispositivos](instant-cross-device-suppression.md).

>[!NOTE]
>
>**Límite de 100 dispositivos para la evaluación y descalificación** de segmentos.
>Audience Manager combina hasta 100 dispositivos al evaluar segmentos con una regla de combinación de Perfiles que utiliza un gráfico de dispositivos. Audience Manager evalúa el dispositivo actual y hasta 99 dispositivos vinculados al dispositivo actual mediante un [perfil autenticado](../../reference/visitor-authentication-states.md) (ID entre dispositivos). Si se emite la señal de dessegmentación, el dispositivo actual y los dispositivos adicionales se eliminarán del segmento en el destino.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [Preguntas frecuentes sobre las reglas de combinación de perfiles y el gráfico de dispositivos](../../faq/faq-profile-merge.md)
>* [Eliminación instantánea entre dispositivos](instant-cross-device-suppression.md)

