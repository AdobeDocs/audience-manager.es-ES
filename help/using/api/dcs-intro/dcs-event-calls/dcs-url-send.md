---
description: Inicio aquí para obtener información sobre cómo realizar llamadas /evento al DCS. Esta sección incluye información sobre la sintaxis de llamada, los parámetros, el formato y un ejemplo de solicitud.
seo-description: Inicio aquí para obtener información sobre cómo realizar llamadas /evento al DCS. Esta sección incluye información sobre la sintaxis de llamada, los parámetros, el formato y un ejemplo de solicitud.
seo-title: Envío de datos al DCS
solution: Audience Manager
title: Envío de datos al DCS
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 2%

---


# Envío de datos al DCS {#send-data-to-the-dcs}

Inicio aquí para obtener información sobre cómo realizar `/event` llamadas al [!DNL DCS]. Esta sección incluye información sobre la sintaxis de llamada, los parámetros, el formato y un ejemplo de solicitud.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Sustituya el valor real del marcador de posición cuando envíe datos al [!DNL DCS] con este método.

## Sintaxis de la llamada {#dcs-call-syntax}

Una `URL` cadena básica que envía datos a los usuarios [!DNL DCS] utiliza la sintaxis que se muestra a continuación.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>También puede enviar datos al [!DNL DCS] mediante el `POST` método . La sintaxis de la llamada se describe en Métodos [de API de](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)DCS.

## Parámetros de llamada {#dcs-call-parameters}

La siguiente tabla define los componentes básicos de una [!DNL DCS] llamada simple.

<table id="table_5F6A5B324EB848168543386516FBF384"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Componente </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> domain alias.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Esta parte de la llamada contiene: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Su alias de dominio asignado por <span class="keyword"> el Audience Manager</span> (por ejemplo, <code> my_domain.demdex.net</code>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Dominio de destino, que siempre es <code> demdex.net</code>. Consulte <a href="../../../reference/demdex-calls.md">Explicación de las llamadas al dominio Demdex</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Esta parte de la llamada: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifica la llamada como una llamada de evento. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Define el inicio de la cadena URL que contiene los datos que desea enviar al <span class="wintitle"> DCS</span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>Identificador único en el par clave-valor. </p> <p>Estos pares clave-valor utilizan un prefijo específico para identificar el tipo de datos que envía al <span class="wintitle"> DCS</span>. For more information, see <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Supported Attributes for DCS API Calls</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>Un valor de variable que pertenece a un conjunto definido por una clave en el par clave-valor. </p> <p>Al trabajar con valores: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Encerrar datos de cadena entre comillas de doble (por ejemplo, <code> age="41 to 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">Puede pasar varias claves en un solo valor (por ejemplo, <i><code>key</i>=<i>val1,val2,val3</i></code></i>). </li> 
     </ul> </p> <p>Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> Formato de pares de clave-valor en llamadas</a>DCS. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>Parámetros de respuesta opcionales. </p> <p> No se requiere ninguno para enviar datos al <span class="wintitle"> DCS</span>. Sin embargo, si desea que el <span class="wintitle"> DCS</span> devuelva una respuesta, debe incluirla <code> d_rtbd=json</code> en la solicitud. </p> <p>Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_ Pares clave-valor definidos</a>. </p> </td> 
  </tr>
 </tbody>
</table>

## Llamada de muestra {#dcs-sample-call}

Este ejemplo muestra la compañía ficticia [!DNL Acme, Inc.] que envía datos al [!DNL DCS] a través de una [!DNL HTTP] llamada. Tenga en cuenta que esta llamada incluye los parámetros `d_dst=1`, `d_rtbd=json`y `d_cb=callback`opcionales. Indican que [!DNL Acme] desea recibir una [!DNL JSON] respuesta de la [!DNL DCS] función de llamada de retorno. Recuerden, este es sólo un ejemplo. No corte y pegue este código.

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## Pasos siguientes {#dcs-next-steps}

Ahora que estamos familiarizados con el envío de datos al [!DNL DCS]sitio, es hora de ver cómo recuperar datos y analizar esa información. Consulte [Recepción de datos desde el DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORELIKETHIS]
>
>* [Pares de clave-valor explicados](../../../reference/key-value-pairs-explained.md)

