---
description: El estado de autenticación del visitante en Audience Manager determina si la nueva información de rasgos se escribe en el perfil autenticado del visitante o en el perfil del dispositivo, desde donde se recopilaron los datos. Audience Manager administra los estados de autenticación UNKNOWN y LOGGED_OUT de ID de visitante en las llamadas de evento de la misma manera.
keywords: dpm.demdex.net
seo-description: The visitor authentication status in Audience Manager determines if the new trait information is written to the visitor's authenticated profile or to the device profile, where the data was collected from. Audience Manager handles the visitor ID authentication statuses UNKNOWN and LOGGED_OUT in event calls in the same way.
seo-title: Visitor Authentication States in Audience Manager
solution: Audience Manager
title: Estados de autenticación de visitantes en Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: Reference
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 2%

---

# Estados de autenticación de visitantes en Audience Manager{#visitor-authentication-states-in-audience-manager}

El estado de autenticación del visitante en Audience Manager determina si la nueva información de rasgos se escribe en el perfil autenticado del visitante o en el perfil del dispositivo, desde donde se recopilaron los datos. Audience Manager administra los estados de autenticación UNKNOWN y LOGGED_OUT de ID de visitante en las llamadas de evento de la misma manera.

A partir del servicio de ID [!DNL Experience Cloud] de la versión 1.5 (o posterior), el método `setCustomerID` incluye el objeto `AuthState` opcional. `AuthState` identifica a los visitantes según su [estado de autenticación](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] administra los rasgos realizados de forma diferente, según el estado de autenticación pasado en la llamada y la [regla de combinación de perfiles](../features/profile-merge-rules/merge-rules-dashboard.md) que use para la segmentación.

## Estado de autenticación: DESCONOCIDO {#auth-status-unknown}

| Solicitar valor | Leer información del perfil autenticado | Escribir nuevas características en el perfil autenticado |
|---|---|---|
| 0 | <ul><li>Sí, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>No, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] o [!UICONTROL No Authenticated Profile].</li></ul> | No, los datos de rasgos se añaden al perfil del dispositivo. |

Llamada de ejemplo (se resalta el valor de solicitud correspondiente al estado de autenticación):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Estado de autenticación: AUTHENTICATED {#auth-status-authenticated}

| Solicitar valor | Leer información del perfil autenticado | Escribir nuevas características en el perfil autenticado |
|---|---|---|
| 1 | <ul><li>Sí, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] o [!UICONTROL Last Authenticated Profiles].</li><li>No, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile].</li></ul> | Sí, los datos de rasgos se añaden al perfil autenticado. |

Llamada de ejemplo (se resalta el valor de solicitud correspondiente al estado de autenticación):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Estado de autenticación: LOGGED_OUT {#auth-status-logged-out}

| Solicitar valor | Leer información del perfil autenticado | Escribir nuevas características en el perfil autenticado |
|---|---|---|
| 2 | <ul><li>Sí, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>No, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] o [!UICONTROL No Authenticated Profile].</li></ul> | No, los datos de rasgos se escriben en el perfil del dispositivo. |

Llamada de ejemplo (se resalta el valor de solicitud correspondiente al estado de autenticación):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] realiza una sincronización de ID entre [CID y UUID](../reference/ids-in-aam.md) en los tres casos.

>[!MORELIKETHIS]
>
>* [ID de cliente y estados de autenticación](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)
