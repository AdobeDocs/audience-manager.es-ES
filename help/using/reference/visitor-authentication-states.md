---
description: El estado de autenticación de visitante en Audience Manager determina si la nueva información de rasgos se escribe en el perfil autenticado del visitante o en el perfil del dispositivo desde el que se recopilaron los datos. El Audience Manager gestiona los estados de autenticación de ID de visitante UNKNOWN y LOGGED_OUT en las llamadas de evento del mismo modo.
keywords: dpm.demdex.net
seo-description: El estado de autenticación de visitante en Audience Manager determina si la nueva información de rasgos se escribe en el perfil autenticado del visitante o en el perfil del dispositivo desde el que se recopilaron los datos. El Audience Manager gestiona los estados de autenticación de ID de visitante UNKNOWN y LOGGED_OUT en las llamadas de evento del mismo modo.
seo-title: Estados de autenticación de Visitante en Audience Manager
solution: Audience Manager
title: Estados de autenticación de Visitante en Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: 'Referencia '
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
source-git-commit: c3c829ef1335d1e073b719f8252103fa578bb4e6
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 7%

---

# Estados de autenticación de Visitante en Audience Manager{#visitor-authentication-states-in-audience-manager}

El estado de autenticación de visitante en Audience Manager determina si la nueva información de rasgos se escribe en el perfil autenticado del visitante o en el perfil del dispositivo desde el que se recopilaron los datos. El Audience Manager gestiona los estados de autenticación de ID de visitante UNKNOWN y LOGGED_OUT en las llamadas de evento del mismo modo.

A partir del [!DNL Experience Cloud] servicio de ID v1.5+, el método `setCustomerID` incluye el objeto opcional `AuthState` . `AuthState` identifica a los visitantes en función de su estado de  [autenticación](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] gestiona los rasgos realizados de forma diferente, según el estado de autenticación pasado en la llamada y la  [regla de combinación de ](../features/profile-merge-rules/merge-rules-dashboard.md) perfiles que utilice para la segmentación.

## Estado de autenticación: DESCONOCIDO {#auth-status-unknown}

| Valor de solicitud | Leer información del perfil autenticado | Escribir nuevos rasgos en el perfil autenticado |
|---|---|---|
| 0 | <ul><li>Sí, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>No, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] o [!UICONTROL No Authenticated Profile].</li></ul> | No, los datos de rasgos se añaden al perfil del dispositivo. |

Llamada de ejemplo (se resalta el valor de solicitud correspondiente al estado de autenticación):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Estado de autenticación: AUTENTICADO {#auth-status-authenticated}

| Valor de solicitud | Leer información del perfil autenticado | Escribir nuevos rasgos en el perfil autenticado |
|---|---|---|
| 1 | <ul><li>Sí, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] o [!UICONTROL Last Authenticated Profiles].</li><li>No, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile].</li></ul> | Sí, los datos de rasgos se añaden al perfil autenticado. |

Llamada de ejemplo (se resalta el valor de solicitud correspondiente al estado de autenticación):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Estado de autenticación: LOGGED_OUT {#auth-status-logged-out}

| Valor de solicitud | Leer información del perfil autenticado | Escribir nuevos rasgos en el perfil autenticado |
|---|---|---|
| 2 | <ul><li>Sí, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>No, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] o [!UICONTROL No Authenticated Profile].</li></ul> | No, los datos de rasgos se escriben en el perfil del dispositivo. |

Llamada de ejemplo (se resalta el valor de solicitud correspondiente al estado de autenticación):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] realiza una sincronización de ID entre  [CID y ](../reference/ids-in-aam.md) UUID en los tres casos.

>[!MORELIKETHIS]
>
>* [ID de cliente y estados de autenticación](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

