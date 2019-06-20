---
description: Al realizar una llamada, el DCS acepta datos de valor clave en formato estándar o serializado. Consulte esta sección para obtener información sobre cómo dar formato a los datos de valor clave estándar y serializados.
seo-description: Al realizar una llamada, el DCS acepta datos de valor clave en formato estándar o serializado. Consulte esta sección para obtener información sobre cómo dar formato a los datos de valor clave estándar y serializados.
seo-title: Formato de pares clave-valor en llamadas DCS
solution: Audience Manager
title: Formato de pares clave-valor en llamadas DCS
uuid: af 02 f 2 a 1-4388-4074-ab 4 e -66 ee 82023 f 1 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Formatting Key-Value Pairs in DCS Calls {#formatting-key-value-pairs-in-dcs-calls}

When making a call, the [!UICONTROL DCS] accepts key-value data in standard or serialized format. Consulte esta sección para obtener información sobre cómo dar formato a los datos de valor clave estándar y serializados.

## Standard and Serialized Key-Value Pairs {#standard-serialized}

<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de valor clave </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Variables </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Estándar</b> </td> 
   <td colname="col2"> <p>Un par estándar de valor clave consiste en una sola clave y valor. Esta estructura organiza los datos en pares de clave-valor separados. Cada clave se indica explícitamente, incluso cuando se vuelve a utilizar para definir un valor diferente. Es la manera más común de enviar datos al DCS. </p> </td>
   <td colname="col3"> <code> key 1 = val 1 &amp; key 2 = val 2 &amp; key 3 = val 3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Serializado</b> </td> 
   <td colname="col2"> <p>Un par de valor clave serializado consiste en una sola clave y valores múltiples. Puede ser una manera eficaz de organizar los datos, pero los pares de clave-valor serializados requieren símbolos específicos para separar cada clave y cada conjunto de valores clave. </p> </td> 
   <td colname="col3"> <code> key 1 = val 1, val 2, val 3</code> </td> 
  </tr>
 </tbody>
</table>

## Delimiters and Separators for Serialized Key-Value Pairs {#delimiters-separators}

Con pares de clave-valor serializados, debe especificar los marcadores que separan los valores dentro de estas variables y entre ellas. Audience Manager requiere los siguientes delimitadores y separadores:

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Requisitos para </th> 
   <th colname="col2" class="entry"> Símbolo </th> 
   <th colname="col3" class="entry"> Separar individual </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Delimitadores</b> </td> 
   <td colname="col2"> &amp; &amp; </td> 
   <td colname="col3"> <p>Pares clave-valor: </p> <p><code> key 1 = val 1 &amp; key 2 = val 2, val 3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Separadores</b> </td> 
   <td colname="col2"> Coma , </td> 
   <td colname="col3"> <p>Valores dentro de pares clave-valor: </p> <p><code> key 1 = val 1, val 2, val 3 &amp; key 2 = vala, valb, valc</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Enviar datos al DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [Prefijos y variables de valor clave admitidos por el DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [Pares de clave-valor explicados](../../../reference/key-value-pairs-explained.md)

