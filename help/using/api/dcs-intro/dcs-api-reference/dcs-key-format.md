---
description: Al realizar una llamada, el DCS acepta datos de clave-valor en formato estándar o serializado. Consulte esta sección para obtener información sobre el formato de datos de clave-valor estándar y serializados.
seo-description: When making a call, the DCS accepts key-value data in standard or serialized format. Review this section for information about how to format standard and serialized key-value data.
seo-title: Formatting Key-Value Pairs in DCS Calls
solution: Audience Manager
title: Formato de pares de clave-valor en llamadas DCS
uuid: af02f2a1-4388-4074-ab4e-66ee82023f1c
feature: DCS
exl-id: ff2d9ff6-7d5b-4a0d-b831-5d9bc79b32a1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 11%

---

# Formato de pares de clave-valor en llamadas DCS {#formatting-key-value-pairs-in-dcs-calls}

Al realizar una llamada, la variable [!DNL DCS] acepta datos de clave-valor en formato estándar o serializado. Consulte esta sección para obtener información sobre el formato de datos de clave-valor estándar y serializados.

## Pares de clave-valor estándar y serializados {#standard-serialized}

<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo clave-valor </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Ejemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Estándar</b> </td> 
   <td colname="col2"> <p>Un par clave-valor estándar consta de una sola clave y un solo valor. Esta estructura organiza los datos en pares clave-valor independientes. Cada clave se indica explícitamente, incluso cuando se utiliza de nuevo para definir un valor diferente. Esta es la forma más común de enviar datos al DCS. </p> </td>
   <td colname="col3"> <code> key1=val1&amp;key2=val2&amp;key3=val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Serializado</b> </td> 
   <td colname="col2"> <p>Un par clave-valor serializado consta de una sola clave y varios valores. Puede ser una forma eficaz de organizar los datos, pero los pares de clave-valor serializados requieren símbolos específicos para separar cada clave y cada conjunto de clave-valor. </p> </td> 
   <td colname="col3"> <code> key1=val1,val2,val3</code> </td> 
  </tr>
 </tbody>
</table>

## Delimitadores y separadores para pares clave-valor serializados {#delimiters-separators}

Con pares de clave-valor serializados, debe especificar los marcadores que separan los valores dentro de estas variables y entre ellas. Audience Manager requiere los siguientes delimitadores y separadores:

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Requisitos para </th> 
   <th colname="col2" class="entry"> Símbolo </th> 
   <th colname="col3" class="entry"> Separa al individuo </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Delimitadores</b> </td> 
   <td colname="col2"> Ampersand &amp; </td> 
   <td colname="col3"> <p>Pares de clave-valor: </p> <p><code> key1=val1&amp;key2=val2,val3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Separadores</b> </td> 
   <td colname="col2"> Coma , </td> 
   <td colname="col3"> <p>Valores dentro de pares clave-valor: </p> <p><code> key1=val1,val2,val3&amp;key2=valA,valB,valC</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Envío de datos al DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [Prefijos de clave-valor y variables compatibles con el DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [Pares de clave-valor explicados](../../../reference/key-value-pairs-explained.md)

