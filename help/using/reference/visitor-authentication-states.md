---
description: El estado de autenticación de visitante en el Audience Manager determina si la nueva información de características se escribe en el perfil autenticado del visitante o en el perfil del dispositivo, desde donde se recopilaron los datos. El Audience Manager gestiona los estados de autenticación de ID de visitante UNKNOWN y LOGGED_OUT en las llamadas de evento del mismo modo.
keywords: dpm.demdex.net
seo-description: El estado de autenticación de visitante en el Audience Manager determina si la nueva información de características se escribe en el perfil autenticado del visitante o en el perfil del dispositivo, desde donde se recopilaron los datos. El Audience Manager gestiona los estados de autenticación de ID de visitante UNKNOWN y LOGGED_OUT en las llamadas de evento del mismo modo.
seo-title: Estados de autenticación de Visitante en Audience Manager
solution: Audience Manager
title: Estados de autenticación de Visitante en Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: reference
translation-type: tm+mt
source-git-commit: a41f0beffba686f283a2933ad7066cb124e4d380
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 5%

---


# Estados de autenticación de Visitante en Audience Manager{#visitor-authentication-states-in-audience-manager}

El estado de autenticación de visitante en el Audience Manager determina si la nueva información de características se escribe en el perfil autenticado del visitante o en el perfil del dispositivo, desde donde se recopilaron los datos. El Audience Manager gestiona los estados de autenticación de ID de visitante UNKNOWN y LOGGED_OUT en las llamadas de evento del mismo modo.

A partir del servicio [!DNL Experience Cloud] de ID v1.5+, el `setCustomerID` método incluye el `AuthState` objeto opcional. `AuthState` identifica los visitantes según su estado [](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)de autenticación. [!DNL Audience Manager] gestiona las características realizadas de forma diferente, en función del estado de autenticación pasado en la llamada y de la regla [de combinación de](../features/profile-merge-rules/merge-rules-dashboard.md) Perfiles que utilice para la segmentación.

## Estado de autenticación: DESCONOCIDO {#auth-status-unknown}

| Valor de solicitud | **Leer** información del perfil autenticado | **Escribir** nuevas características en el perfil autenticado |
---------|----------|---------
| 0 | <ul><li>Sí, si la regla de combinación de opciones autenticada = &quot;Últimos Perfiles autenticados&quot;.</li><li>No, si la regla de combinación de opciones autenticada = &quot;Perfiles autenticados actuales&quot; o &quot;Ningún Perfil autenticado&quot;.</li></ul> | No, los datos de características se agregan al perfil del dispositivo. |


Ejemplo de llamada (se resalta el valor de solicitud correspondiente al estado de autenticación):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Estado de autenticación: AUTENTICADO {#auth-status-authenticated}

| Valor de solicitud | **Leer** información del perfil autenticado | **Escribir** nuevas características en el perfil autenticado |
---------|----------|---------
| 1 | <ul><li>Sí, si la regla de combinación de opciones autenticadas = &quot;Perfiles autenticados actuales&quot; o &quot;Últimos Perfiles autenticados&quot;.</li><li>No, si la regla de combinación de opciones autenticada = &quot;Sin Perfil autenticado&quot;.</li></ul> | Sí, los datos de características se agregan al perfil autenticado. |

Ejemplo de llamada (se resalta el valor de solicitud correspondiente al estado de autenticación):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Estado de autenticación: LOGGED_OUT {#auth-status-logged-out}

| Valor de solicitud | **Leer** información del perfil autenticado | **Escribir** nuevas características en el perfil autenticado |
---------|----------|---------
| 2 | <ul><li>Sí, si la regla de combinación de opciones autenticadas = &quot;Últimos Perfiles autenticados&quot;</li><li>No, si la regla de combinación de opciones autenticadas = &quot;Perfiles autenticados actuales&quot; o &quot;Ningún Perfil autenticado&quot;</li></ul> | No, los datos de características se escriben en el perfil del dispositivo. |

Ejemplo de llamada (se resalta el valor de solicitud correspondiente al estado de autenticación):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] realiza una sincronización de ID entre [CID y UUID](../reference/ids-in-aam.md) en los tres casos.

>[!MORELIKETHIS]
>
>* [ID de cliente y estados de autenticación](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

