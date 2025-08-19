---
description: La eliminación de la segmentación describe procesos que descalifican y eliminan perfiles de dispositivos de los segmentos. La posibilidad de quitar un perfil de dispositivo de un segmento depende de la opción de dispositivo que se use para crear una regla de combinación de perfiles.
seo-description: Unsegmentation describes processes that disqualify and remove device profiles from segments. Your ability to remove a device profile from a segment depends on the device option used to create a Profile Merge Rule.
seo-title: Profile Merge Rules and Device Un-Segmentation Processes
solution: Audience Manager
title: Reglas de combinación de perfiles y procesos de eliminación de la segmentación de dispositivos
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profile Merge
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 2%

---

# Reglas de combinación de perfiles y procesos de eliminación de la segmentación de dispositivos {#profile-merge-rules-and-device-un-segmentation-processes}

La eliminación de la segmentación describe procesos que descalifican y eliminan perfiles de dispositivos de los segmentos. La posibilidad de quitar un perfil de dispositivo de un segmento depende de la opción de dispositivo utilizada para crear un(a) [!UICONTROL Profile Merge Rule].

## Opciones de dispositivo disponibles {#device-options}

Como recordatorio, los [!UICONTROL Device Options] están disponibles en la sección [!UICONTROL Profile Merge Rules Setup] cuando crea o edita un [!UICONTROL Profile Merge Rule].

## Opción de perfil de dispositivo actual y eliminación de la segmentación del dispositivo {#current-device-profile-options}

**[!UICONTROL Device Profile]** es la opción de perfil de dispositivo predeterminada para [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] puede quitar un perfil de dispositivo de un segmento cuando su [!UICONTROL Profile Merge Rule] utiliza la opción **[!UICONTROL Device Profile]**. En estas condiciones, la eliminación de la segmentación se produce cuando:

* El perfil del dispositivo ha estado inactivo durante 120 días. Un proceso semanal de limpieza de datos elimina los perfiles de dispositivo inactivos de los segmentos.
* El dispositivo ya no cumple los requisitos para un segmento porque las actualizaciones o cambios en el perfil del dispositivo lo descalifican. Esto sucede cuando cambian los criterios de calificación de segmentos, aplica un operador [!DNL AND NOT] a una regla de segmento o especifica [condiciones de actualización y frecuencia](../segments/recency-and-frequency.md) que utilizan la configuración menor o igual que. Los casos de uso se describen en la documentación de [Eliminación instantánea entre dispositivos](instant-cross-device-suppression.md).

![solo-dispositivo](assets/device-only.png)

## Sin opción de dispositivo y eliminación de la segmentación del dispositivo {#no-device-option}

[!DNL Audience Manager] puede quitar un identificador entre dispositivos de un segmento cuando su [!UICONTROL Profile Merge Rule] use la opción **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]**. En estas condiciones, la eliminación de la segmentación se produce cuando el ID entre dispositivos ya no cumple los requisitos para un segmento porque las actualizaciones o cambios en el perfil entre dispositivos lo descalifican. Esto sucede cuando cambian los criterios de calificación de segmentos, aplica un operador [!UICONTROL AND NOT] a una regla de segmento o especifica [condiciones de actualización y frecuencia](../segments/recency-and-frequency.md) que utilizan la configuración menor o igual que. Los casos de uso se describen en la documentación de [Eliminación instantánea entre dispositivos](instant-cross-device-suppression.md).

![](assets/current-no-device.png)

## Opciones de gráfico de dispositivos y eliminación de la segmentación de dispositivos {#device-graph-options-unsegmentation}

[!DNL Audience Manager] puede quitar varios perfiles de dispositivo de un segmento cuando su [!UICONTROL Profile Merge Rule] usa una opción de gráfico de dispositivo. La eliminación de la segmentación se produce cuando el perfil combinado del dispositivo desde el gráfico del dispositivo ya no cumple los requisitos para el segmento porque las actualizaciones o cambios en este perfil combinado lo descalifican para el segmento. Esto sucede cuando cambian los criterios de calificación de segmentos, aplica un operador [!UICONTROL AND NOT] a una regla de segmento o especifica [condiciones de actualización y frecuencia](../segments/recency-and-frequency.md) que utilizan la configuración menor o igual que. Los casos de uso se describen en la documentación de [Eliminación instantánea entre dispositivos](instant-cross-device-suppression.md).

>[!NOTE]
>
>**Límite de 100 dispositivos para la evaluación y descalificación de segmentos**.
>>Audience Manager combina hasta 100 dispositivos al evaluar segmentos con una regla de combinación de perfiles que utiliza un gráfico de dispositivos. Audience Manager evalúa el dispositivo actual y hasta 99 dispositivos vinculados al dispositivo actual mediante un [perfil autenticado](../../reference/visitor-authentication-states.md) (ID entre dispositivos). Si se emite la señal para anular la segmentación, el dispositivo actual y los dispositivos adicionales se eliminarán del segmento en el destino.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [Preguntas frecuentes sobre las reglas de combinación de perfiles y el gráfico de dispositivos](../../faq/faq-profile-merge.md)
>* [Eliminación instantánea entre dispositivos](instant-cross-device-suppression.md)
