---
description: Con las reglas de combinación de Perfiles, obtiene el control sobre los conjuntos de datos utilizados para la segmentación y puede realizar el destinatario de una persona con precisión en varios dispositivos.
seo-description: Con las reglas de combinación de Perfiles, obtiene el control sobre los conjuntos de datos utilizados para la segmentación y puede realizar el destinatario de una persona con precisión en varios dispositivos.
seo-title: Información general sobre las reglas de combinación de Perfiles
solution: Audience Manager
title: Información general sobre las reglas de combinación de Perfiles
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 4%

---


# [!UICONTROL Profile Merge Rules] Información general {#profile-merge-rules-overview}

Con [!UICONTROL Profile Merge Rules] puede controlar qué conjuntos de datos se utilizan para la segmentación y puede realizar un destinatario preciso de los usuarios en varios dispositivos.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Recopilación y segmentación de datos con perfiles anónimos y autenticados {#data-collection-targeting}

Generalmente, la segmentación y la segmentación de audiencias dependen de los datos recopilados de todos los usuarios en un dispositivo. La recopilación de datos y la determinación de objetivos en función de los datos a nivel de dispositivo tienen algunas desventajas. Por ejemplo, no puede distinguir entre varios usuarios que comparten un dispositivo o que destinatario con precisión a usuarios en varios dispositivos. La recopilación de datos centrada en el dispositivo ya no es suficiente para las campañas de marketing digital o la segmentación entre dispositivos.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] cambia fundamentalmente la forma en que  [!DNL Audience Manager] recopila datos y segmenta a los usuarios para la segmentación. Le permite trabajar con dos tipos distintos de perfiles, un perfil de dispositivo y un [perfil autenticado](../../reference/visitor-authentication-states.md).

| Tipo de perfil | Descripción |
|---|---|
| [!UICONTROL Device Profile] | Un [!UICONTROL device profile] está ligado a un ID para un dispositivo determinado, como un ID de [!UICONTROL cookie] o un ID de dispositivo móvil.<br><br> Incluye:<ul><li>[!UICONTROL Rule-based traits] se realiza cuando un usuario no está autenticado.</li><li>[!UICONTROL Onboarded traits] vinculado a un ID de dispositivo como, por ejemplo, datos de terceros  [!UICONTROL cookie-based].</li></ul> |
| [!UICONTROL Authenticated Profile] | El [!UICONTROL authenticated profile] está vinculado a un ID de usuario que se pasa cuando una persona inicia sesión en el sitio.<br><br>Incluye:<ul><li>[!UICONTROL Rule-based traits] se recopilan en todos los dispositivos cuando se autentica a un usuario.</li><li>[!UICONTROL Onboarded traits] en un archivo sin conexión vinculado al mismo ID de usuario.</li></ul> |

Estos diferentes perfiles controlan los datos que puede utilizar para la segmentación. Por ejemplo, con un [perfil autenticado](../../reference/visitor-authentication-states.md), puede generar datos precisos [!UICONTROL segments] basados en datos de varios dispositivos para un solo usuario. Esto significa que puede ofrecer una experiencia de marca uniforme a los clientes en varios dispositivos. [!DNL Audience Manager] lo logra almacenando la asignación de los diferentes dispositivos que una persona utiliza para sus actividades en línea a su perfil [ ](../../reference/visitor-authentication-states.md)autenticado. Estas asignaciones se denominan [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Ventajas {#advantages}

Con [!UICONTROL Profile Merge Rules] puede:

* Usuarios de destinatario basados en [perfil autenticado](../../reference/visitor-authentication-states.md), perfiles anónimos o combinaciones de ambos.
* Destinatario a un cliente específico en sus dispositivos.
* Cree un gráfico de dispositivos basado en datos determinísticos.
* Ajuste los datos de su [!UICONTROL segments] basándose en diferentes perfiles.
* Obtenga información adicional sobre su audiencia.
