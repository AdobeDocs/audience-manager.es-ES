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
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 5%

---

# Estados de autenticación de Visitante en Audience Manager{#visitor-authentication-states-in-audience-manager}

El estado de autenticación de visitante en Audience Manager determina si la nueva información de rasgos se escribe en el perfil autenticado del visitante o en el perfil del dispositivo desde el que se recopilaron los datos. El Audience Manager gestiona los estados de autenticación de ID de visitante UNKNOWN y LOGGED_OUT en las llamadas de evento del mismo modo.

A partir del [!DNL Experience Cloud] servicio de ID v1.5+, el método `setCustomerID` incluye el objeto opcional `AuthState` . `AuthState` identifica a los visitantes en función de su estado de  [autenticación](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] gestiona los rasgos realizados de forma diferente, según el estado de autenticación pasado en la llamada y la  [regla de combinación de ](../features/profile-merge-rules/merge-rules-dashboard.md) perfiles que utilice para la segmentación.

## Estado de autenticación: DESCONOCIDO {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valor de solicitud </p> </th> 
   <th colname="col2" class="entry"> <p> <b></b> Leer información del perfil autenticado </p> </th> 
   <th colname="col3" class="entry"> <p> <b></b> Escribir nuevos rasgos en el perfil autenticado </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>Sí, si la regla de combinación de opciones autenticadas = "Últimos perfiles autenticados". </p> </td> 
   <td colname="col3" morerows="1"> <p>No, los datos de rasgos se añaden al perfil del dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>No, si la regla de combinación de opciones autenticadas = "Perfiles autenticados actuales" o "Ningún perfil autenticado". </p> </td> 
  </tr> 
 </tbody> 
</table>

Llamada de ejemplo (se resalta el valor de solicitud correspondiente al estado de autenticación):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Estado de autenticación: AUTENTICADO {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valor de solicitud </p> </th> 
   <th colname="col2" class="entry"> <p> <b></b> Leer información del perfil autenticado </p> </th> 
   <th colname="col3" class="entry"> <p> <b></b> Escribir nuevos rasgos en el perfil autenticado </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>Sí, si la regla de combinación de opciones autenticadas = "Perfiles autenticados actuales" o "Últimos perfiles autenticados". </p> </td> 
   <td colname="col3" morerows="1"> <p>Sí, los datos de rasgos se añaden al perfil autenticado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>No, si la regla de combinación de opciones autenticadas = "Sin perfil autenticado". </p> </td> 
  </tr> 
 </tbody> 
</table>

Llamada de ejemplo (se resalta el valor de solicitud correspondiente al estado de autenticación):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Estado de autenticación: LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valor de solicitud </p> </th> 
   <th colname="col2" class="entry"> <p> <b></b> Leer información del perfil autenticado </p> </th> 
   <th colname="col3" class="entry"> <p> <b></b> Escribir nuevos rasgos en el perfil autenticado </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 2 </code> </p> </td> 
   <td colname="col2"> Sí, si la regla de combinación de opciones autenticadas = "Últimos perfiles autenticados" </td> 
   <td colname="col3" morerows="1"> <p>No, los datos de rasgos se escriben en el perfil del dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> No, si la regla de combinación de opciones autenticadas = "Perfiles autenticados actuales" o "Ningún perfil autenticado" </td> 
  </tr> 
 </tbody> 
</table>

Llamada de ejemplo (se resalta el valor de solicitud correspondiente al estado de autenticación):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] realiza una sincronización de ID entre  [CID y ](../reference/ids-in-aam.md) UUID en los tres casos.

>[!MORELIKETHIS]
>
>* [ID de cliente y estados de autenticación](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

