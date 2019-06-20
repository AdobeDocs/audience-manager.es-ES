---
description: El estado de autenticación del visitante en Audience Manager determina si la nueva información de características se escribe en el perfil autenticado del visitante o en el perfil del dispositivo donde se recopilaron los datos. Audience Manager gestiona los estados de autenticación de ID de visitante DESCONOCIDA y LOGGED_ OUT en las llamadas de evento de la misma manera.
keywords: dpm.demdex.net
seo-description: El estado de autenticación del visitante en Audience Manager determina si la nueva información de características se escribe en el perfil autenticado del visitante o en el perfil del dispositivo donde se recopilaron los datos. Audience Manager gestiona los estados de autenticación de ID de visitante DESCONOCIDA y LOGGED_ OUT en las llamadas de evento de la misma manera.
seo-title: Estados de autenticación de visitantes en Audience Manager
solution: Audience Manager
title: Estados de autenticación de visitantes en Audience Manager
uuid: d 748 c 0 c 3-5833-4 fb 9-ab 3 e -793 f 5 f 252 e 47
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Visitor Authentication States in Audience Manager{#visitor-authentication-states-in-audience-manager}

El estado de autenticación del visitante en Audience Manager determina si la nueva información de características se escribe en el perfil autenticado del visitante o en el perfil del dispositivo donde se recopilaron los datos. Audience Manager gestiona los estados de autenticación de ID de visitante DESCONOCIDA y LOGGED_ OUT en las llamadas de evento de la misma manera.

Beginning with [!DNL Experience Cloud] ID service v1.5+, the `setCustomerID` method includes the optional `AuthState` object. `AuthState` identifica a los visitantes según su estado [de autenticación](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). [!DNL Audience Manager] gestiona las características obtenidas de forma diferente, según el estado de autenticación pasado en la llamada y la [regla](../features/profile-merge-rules/merge-rules-dashboard.md) de combinación de perfiles que se utiliza para la segmentación.

## Authentication Status: UNKNOWN {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valor de solicitud </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Leer</b> información del perfil autenticado </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Escribir</b> nuevas características al perfil autenticado </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>Sí, si la regla de combinación de opciones autenticadas = "Últimos perfiles autenticados". </p> </td> 
   <td colname="col3" morerows="1"> <p>No, los datos de características se agregan al perfil del dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>No, si la regla de combinación de opciones autenticadas = "Perfiles autenticados actuales" o "Ningún perfil autenticado". </p> </td> 
  </tr> 
 </tbody> 
</table>

Llamada de muestra (el valor de solicitud correspondiente al estado de autenticación está resaltado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Authentication Status: AUTHENTICATED {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valor de solicitud </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Leer</b> información del perfil autenticado </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Escribir</b> nuevas características al perfil autenticado </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>Sí, si la regla de combinación de opciones autenticadas = "Perfiles autenticados actuales" o "Perfiles autenticados últimos". </p> </td> 
   <td colname="col3" morerows="1"> <p>Sí, los datos de características se agregan al perfil autenticado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>No, si la regla de combinación de opciones autenticadas = "Sin perfil autenticado". </p> </td> 
  </tr> 
 </tbody> 
</table>

Llamada de muestra (el valor de solicitud correspondiente al estado de autenticación está resaltado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Authentication Status: LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valor de solicitud </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Leer</b> información del perfil autenticado </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Escribir</b> nuevas características al perfil autenticado </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code>2</code> </p> </td> 
   <td colname="col2"> Sí, si la regla de combinación de opciones autenticadas = "Últimos perfiles autenticados" </td> 
   <td colname="col3" morerows="1"> <p>No, los datos de características se escriben en el perfil del dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> No, si la regla de combinación de opciones autenticadas = "Perfiles autenticados actuales" o "Perfiles autenticados" </td> 
  </tr> 
 </tbody> 
</table>

Llamada de muestra (el valor de solicitud correspondiente al estado de autenticación está resaltado):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] realiza una sincronización de ID entre [CID y UUID](../reference/ids-in-aam.md) en los tres casos.

>[!MORE_ LIKE_ THIS]
>
>* [ID de cliente y estados de autenticación](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html)

