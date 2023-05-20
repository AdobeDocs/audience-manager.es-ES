---
description: Con las reglas de combinación de perfiles, puede controlar los conjuntos de datos utilizados para la segmentación y puede dirigirse a una persona con precisión en varios dispositivos.
seo-description: With Profile Merge Rules you get control over the data sets used for segmentation and can target a person accurately across multiple devices.
seo-title: Profile Merge Rules Overview
solution: Audience Manager
title: Información general sobre las reglas de combinación de Perfiles
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profile Merge
exl-id: 5d1f5bea-0fca-4684-a2b4-585d9e38d9ef
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 3%

---

# [!UICONTROL Profile Merge Rules] Información general {#profile-merge-rules-overview}

Con [!UICONTROL Profile Merge Rules] puede controlar qué conjuntos de datos se utilizan para la segmentación y puede dirigirse a los usuarios con precisión en varios dispositivos.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Recopilación y direccionamiento de datos con perfiles anónimos y autenticados {#data-collection-targeting}

Normalmente, la segmentación de audiencia y la segmentación se basan en datos recopilados de todos los usuarios en un dispositivo. La recopilación de datos y la segmentación basada en datos de nivel de dispositivo tienen algunas desventajas. Por ejemplo, no se puede distinguir entre varios usuarios que comparten un dispositivo o que se dirigen a usuarios con precisión en varios dispositivos. La recopilación de datos centrada en el dispositivo ya no es suficiente para las campañas de marketing digital o la segmentación entre dispositivos.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] cambia fundamentalmente cómo [!DNL Audience Manager] recopila datos y segmentos de usuarios para la segmentación. Permite trabajar con 2 tipos distintos de perfiles, un perfil de dispositivo y un [perfil autenticado](../../reference/visitor-authentication-states.md).

| Tipo de perfil | Descripción |
|---|---|
| [!UICONTROL Device Profile] | A [!UICONTROL device profile] está vinculado a un ID para un dispositivo determinado, como un [!UICONTROL cookie] ID de o ID de dispositivo móvil.<br><br> Incluye:<ul><li>[!UICONTROL Rule-based traits] se registra cuando un usuario no está autenticado.</li><li>[!UICONTROL Onboarded traits] vinculado a un ID de dispositivo como [!UICONTROL cookie-based], datos de terceros.</li></ul> |
| [!UICONTROL Authenticated Profile] | El [!UICONTROL authenticated profile] está vinculado a un ID de usuario que se pasa cuando una persona inicia sesión en el sitio.<br><br>Incluye:<ul><li>[!UICONTROL Rule-based traits] se recopilan entre dispositivos cuando se autentica a un usuario.</li><li>[!UICONTROL Onboarded traits] en un archivo sin conexión vinculado al mismo ID de usuario.</li></ul> |

Estos diferentes perfiles controlan los datos que puede utilizar para la segmentación. Por ejemplo, con un [perfil autenticado](../../reference/visitor-authentication-states.md), puede generar informes precisos [!UICONTROL segments] basado en datos de varios dispositivos para un solo usuario. Esto significa que puede ofrecer una experiencia de marca coherente a los clientes en varios dispositivos. [!DNL Audience Manager] lo consigue almacenando la asignación de los diferentes dispositivos que una persona utiliza para sus actividades en línea a sus [perfil autenticado](../../reference/visitor-authentication-states.md). Estas asignaciones se denominan [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Ventajas {#advantages}

Con [!UICONTROL Profile Merge Rules] puede:

* Usuarios de destino según [perfil autenticado](../../reference/visitor-authentication-states.md), perfiles anónimos o combinaciones de ambos.
* Dirigirse a un cliente específico en todos sus dispositivos.
* Cree un gráfico de dispositivos basado en datos deterministas.
* Ajuste de los datos de su [!UICONTROL segments] en función de diferentes perfiles.
* Obtenga información adicional sobre su audiencia.
