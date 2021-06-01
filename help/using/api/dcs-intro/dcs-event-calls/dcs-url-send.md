---
description: Comience aquí para obtener información sobre cómo realizar llamadas /event al DCS. Esta sección incluye información sobre la sintaxis de llamada, los parámetros, el formato y un ejemplo de solicitud.
seo-description: Comience aquí para obtener información sobre cómo realizar llamadas /event al DCS. Esta sección incluye información sobre la sintaxis de llamada, los parámetros, el formato y un ejemplo de solicitud.
seo-title: Envío de datos al DCS
solution: Audience Manager
title: Envío de datos al DCS
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
feature: DCS
exl-id: 8a6798c3-aafd-48c8-acd7-a0e29e04dc8e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 6%

---

# Envío de datos al DCS {#send-data-to-the-dcs}

Comience aquí para obtener información sobre cómo realizar `/event` llamadas a [!DNL DCS]. Esta sección incluye información sobre la sintaxis de llamada, los parámetros, el formato y un ejemplo de solicitud.

>[!NOTE]
>
>En el código y los ejemplos, *cursiva* representa un marcador de posición de variable. Sustituya el valor real del marcador de posición cuando envíe datos a [!DNL DCS] con este método.

## Sintaxis de la llamada {#dcs-call-syntax}

Una cadena `URL` básica que envía datos a [!DNL DCS] utiliza la sintaxis que se muestra a continuación.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>También puede enviar datos a [!DNL DCS] utilizando el método `POST` . La sintaxis de la llamada se describe en [DCS API Methods](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md).

## Parámetros de llamada {#dcs-call-parameters}

La siguiente tabla define los componentes básicos de una llamada [!DNL DCS] simple.

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
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Su alias de dominio asignado por el Audience Manager <span class="keyword"></span> (por ejemplo, <code> my_domain.demdex.net</code>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">El dominio de destino, que siempre es <code> demdex.net</code>. Consulte <a href="../../../reference/demdex-calls.md">Explicación de las llamadas al dominio Demdex</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Esta parte de la llamada: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifica la llamada como una llamada de evento. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Define el inicio de la cadena de URL que contiene los datos que desea enviar al <span class="wintitle"> DCS</span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>Identificador único en el par clave-valor. </p> <p>Estos pares clave-valor utilizan un prefijo específico para identificar el tipo de datos que envía al <span class="wintitle"> DCS</span>. Para obtener más información, consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Atributos admitidos para llamadas a la API DCS</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>Valor de variable que pertenece a un conjunto definido por una clave en el par clave-valor. </p> <p>Al trabajar con valores: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Escriba los datos de cadena entre comillas dobles (por ejemplo, <code> age="41 to 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">Puede pasar varias claves en un solo valor (por ejemplo, <i><code>key</i>=<i>val1,val2,val3</i></code></i>). </li> 
     </ul> </p> <p>Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> Formato de pares clave-valor en llamadas DCS</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>Parámetros de respuesta opcionales. </p> <p> No se requiere ninguno de estos elementos para enviar datos al <span class="wintitle"> DCS</span>. Sin embargo, si desea que el <span class="wintitle"> DCS</span> devuelva una respuesta, debe incluir <code> d_rtbd=json</code> en la solicitud. </p> <p>Consulte <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_ Pares de clave-valor definidos</a>. </p> </td> 
  </tr>
 </tbody>
</table>

## Ejemplo de llamada {#dcs-sample-call}

Este ejemplo muestra la empresa ficticia [!DNL Acme, Inc.] que envía datos a [!DNL DCS] mediante una llamada [!DNL HTTP]. Tenga en cuenta que esta llamada incluye los parámetros opcionales `d_dst=1`, `d_rtbd=json` y `d_cb=callback`. Indican que [!DNL Acme] desea recibir una respuesta [!DNL JSON] de [!DNL DCS] con una función de llamada de retorno. Recuerde, este es solo un ejemplo. No corte y pegue este código.

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## Pasos siguientes {#dcs-next-steps}

Ahora que está familiarizado con el envío de datos al [!DNL DCS], es hora de ver cómo obtener los datos de él y analizar esa información. Consulte [Recibir datos del DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORELIKETHIS]
>
>* [Pares de clave-valor explicados](../../../reference/key-value-pairs-explained.md)

