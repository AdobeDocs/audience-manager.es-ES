---
description: Comience aquí para obtener información sobre cómo hacer /event llamadas al DCS. Esta sección incluye información sobre la sintaxis, los parámetros, el formato y el ejemplo de solicitud de la llamada.
seo-description: Comience aquí para obtener información sobre cómo hacer /event llamadas al DCS. Esta sección incluye información sobre la sintaxis, los parámetros, el formato y el ejemplo de solicitud de la llamada.
seo-title: Enviar datos al DCS
solution: Audience Manager
title: Enviar datos al DCS
uuid: 024 e 307 d-bfcb -46 cf-ac 3 a-fc 71 df 0248 fe
translation-type: tm+mt
source-git-commit: 9c692ae41a309b4f1d8323a501619c02d2aef6a0

---


# Enviar datos al DCS {#send-data-to-the-dcs}

Comience aquí para obtener información sobre cómo `/event` realizar llamadas al [!UICONTROL DCS]. Esta sección incluye información sobre la sintaxis, los parámetros, el formato y el ejemplo de solicitud de la llamada.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Sustituya un valor real del marcador de posición cuando envíe datos al [!UICONTROL DCS] con este método.

## Sintaxis de la llamada {#dcs-call-syntax}

Una cadena básica `URL` que envía datos a los [!UICONTROL DCS] utiliza la sintaxis que se muestra a continuación.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>También puede enviar datos a [!UICONTROL DCS] través del `POST` método. La sintaxis de la llamada se describe en [Métodos de API DCS](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md).

## Parámetros de llamada {#dcs-call-parameters}

La tabla siguiente define los componentes básicos de [!UICONTROL DCS] una llamada sencilla.

<table id="table_5F6A5B324EB848168543386516FBF384"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Componente </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> domain alias. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>Esta parte de la llamada contiene: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">El alias de dominio asignado por <span class="keyword"> Audience Manager</span> (p. ej. <code> my_ domain. demdex. net</code>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Dominio de destino, que siempre es <code> demdex. net</code>. Consulte <a href="../../../reference/demdex-calls.md">Explicación de las llamadas al dominio Demdex</a>. </li> 
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
   <td colname="col2"> <p>Identificador único en el par clave-valor. </p> <p>Estos pares de clave-valor utilizan un prefijo específico para identificar el tipo de datos que envía al <span class="wintitle"> DCS</span>. For more information, see <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Supported Attributes for DCS API Calls</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>Un valor de variable que pertenece a un conjunto definido por una clave en el par clave-valor. </p> <p>Al trabajar con valores: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Encierre los datos de cadena entre comillas dobles (por ejemplo <code> , edad = "41 a 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">Puede pasar múltiples claves en un único valor (por ejemplo <i><code>, clave</i>=<i>val 1, val 2, val 3</i></code></i>). </i></li> 
     </ul> </p> <p>Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> Formato de pares de clave-valor en llamadas DCS</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_ dst = 1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_ rtbd = json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_ cb =<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>Parámetros opcionales de respuesta. </p> <p> No se requiere ninguna de ellas para enviar datos al <span class="wintitle"> DCS</span>. Sin embargo, si desea que <span class="wintitle"> el DCS</span> devuelva una respuesta, debe incluir <code> d_ rtbd = json</code> en su solicitud. </p> <p>Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_ Key-Value Pares definidos</a>. </p> </td> 
  </tr>
 </tbody>
</table>

## Llamada de muestra {#dcs-sample-call}

Este ejemplo muestra la empresa ficticia [!DNL Acme, Inc.] que envía datos a [!UICONTROL DCS] través [!DNL HTTP] de una llamada. Tenga en cuenta que esta llamada incluye los parámetros `d_dst=1`opcionales, `d_rtbd=json`y `d_cb=callback`. Indican que [!DNL Acme] desean recibir [!DNL JSON] una respuesta de la función [!UICONTROL DCS] de llamada de retorno. Recuerde, esto es sólo un ejemplo. No corte ni pegue este código.

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## Pasos siguientes {#dcs-next-steps}

Ahora que ya está familiarizado con el envío de datos a [!UICONTROL DCS], es hora de consultar cómo recuperar datos y analizarlos. Consulte [Recepción de datos del DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORE_ LIKE_ THIS]
>
>* [Pares de clave-valor explicados](../../../reference/key-value-pairs-explained.md)

