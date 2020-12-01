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
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 5%

---


# Estados de autenticación de Visitante en Audience Manager{#visitor-authentication-states-in-audience-manager}

El estado de autenticación de visitante en el Audience Manager determina si la nueva información de características se escribe en el perfil autenticado del visitante o en el perfil del dispositivo, desde donde se recopilaron los datos. El Audience Manager gestiona los estados de autenticación de ID de visitante UNKNOWN y LOGGED_OUT en las llamadas de evento del mismo modo.

A partir del [!DNL Experience Cloud] servicio de ID v1.5+, el método `setCustomerID` incluye el objeto opcional `AuthState`. `AuthState` identifica los visitantes según su estado [ ](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)de autenticación. [!DNL Audience Manager] gestiona las características realizadas de forma diferente, según el estado de autenticación pasado en la llamada y la regla de combinación de  [Perfiles que ](../features/profile-merge-rules/merge-rules-dashboard.md) utilice para la segmentación.

## Estado de autenticación: DESCONOCIDO {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valor de solicitud </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Información </b> de lectura del perfil autenticado </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Características de </b> escritura en el perfil autenticado </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>Sí, si la regla de combinación de opciones autenticada = "Últimos Perfiles autenticados". </p> </td> 
   <td colname="col3" morerows="1"> <p>No, los datos de características se agregan al perfil del dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>No, si la regla de combinación de opciones autenticada = "Perfiles autenticados actuales" o "Ningún Perfil autenticado". </p> </td> 
  </tr> 
 </tbody> 
</table>

Ejemplo de llamada (se resalta el valor de solicitud correspondiente al estado de autenticación):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Estado de autenticación: AUTENTICADO {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valor de solicitud </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Información </b> de lectura del perfil autenticado </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Características de </b> escritura en el perfil autenticado </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>Sí, si la regla de combinación de opciones autenticadas = "Perfiles autenticados actuales" o "Últimos Perfiles autenticados". </p> </td> 
   <td colname="col3" morerows="1"> <p>Sí, los datos de características se agregan al perfil autenticado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>No, si la regla de combinación de opciones autenticada = "Sin Perfil autenticado". </p> </td> 
  </tr> 
 </tbody> 
</table>

Ejemplo de llamada (se resalta el valor de solicitud correspondiente al estado de autenticación):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Estado de autenticación: LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valor de solicitud </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Información </b> de lectura del perfil autenticado </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Características de </b> escritura en el perfil autenticado </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 2 </code> </p> </td> 
   <td colname="col2"> Sí, si la regla de combinación de opciones autenticadas = "Últimos Perfiles autenticados" </td> 
   <td colname="col3" morerows="1"> <p>No, los datos de características se escriben en el perfil del dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> No, si la regla de combinación de opciones autenticadas = "Perfiles autenticados actuales" o "Ningún Perfil autenticado" </td> 
  </tr> 
 </tbody> 
</table>

Ejemplo de llamada (se resalta el valor de solicitud correspondiente al estado de autenticación):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] realiza una sincronización de ID entre  [CID y ](../reference/ids-in-aam.md) UUID en los tres casos.

>[!MORELIKETHIS]
>
>* [ID de cliente y estados de autenticación](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

