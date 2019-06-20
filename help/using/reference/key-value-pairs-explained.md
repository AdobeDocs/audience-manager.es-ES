---
description: Define y describe pares de clave-valor estándar y serializados.
keywords: integration code
seo-description: Define y describe pares de clave-valor estándar y serializados.
seo-title: Pares de clave-valor explicados
solution: Audience Manager
title: Pares de clave-valor explicados
uuid: f 1435742-81 ca -4964-8370-accf 2 f 1 c 47 a 5
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Key-Value Pairs Explained{#key-value-pairs-explained}

Define y describe pares de clave-valor estándar y serializados.

<!-- 

c_key_value_explained.xml

 -->

Un par clave-valor consta de dos elementos de datos relacionados: Una clave, que es una constante que define el conjunto de datos (por ejemplo: sexo, color, precio) y un valor, que es una variable que pertenece al conjunto (p. ej. hombre/mujer, verde, 100). Completamente formado, un par de valores clave podría verse así:

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serialized Key-Value Pairs {#standard-serialized-pairs}

Destinations accept key-value data in *`standard`* or *`serialized`* format. El formato estándar organiza los datos en pares de clave-valor separados. Cada clave se indica explícitamente, incluso cuando se vuelve a utilizar para definir un valor diferente. Por el contrario, el formato serializado condensa varios valores en un conjunto definido por una sola clave. Además, en un par serializado, se utiliza un indicador especial para separar los valores dentro del conjunto de valores clave. Por último, los valores clave y serializados pueden contener valores únicos o múltiples. En la tabla siguiente se proporcionan ejemplos de formatos estándar y de valor clave de serie.

| Formato | Clave única | Pares clave-valor |
|---|---|---|
| **Estándar** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Serializado** | `x=1;2` | `x=1;2&y=3;4` |



## Keys, Delimiters, and Separators {#keys-delimiters-separators}

When working with serialized data, you must specify the characters that separate values *within* and *between* the key-value pairs. Los elementos en pares de clave-valor se definen de la siguiente manera:

* **Clave:** Identificador único en el par clave-valor.
* **Delimitador de valores:** Separa pares de clave-valor individuales.
* **Separador de valor clave:** Separa una clave de los valores dentro de un par de valores clave.
* **Separador de serie:** Separa valores individuales dentro de pares de clave-valor serializados.

## Standard and Serialized Key-Value Elements {#standard-serialized-key-value-elements}

<table id="table_62B0498441034A719C9DB57276777D40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo </th> 
   <th colname="col2" class="entry"> Ejemplo </th> 
   <th colname="col3" class="entry"> Clave </th> 
   <th colname="col4" class="entry"> Separador de valor clave </th> 
   <th colname="col5" class="entry"> Delimitador de valor clave </th> 
   <th colname="col6" class="entry"> Separador de serie </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Clave única</b> <p>(standard) </p> </td> 
   <td colname="col2"> <code> x = 1 &amp; x = 2 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col4" morerows="3"> = </td> 
   <td colname="col5" morerows="1"> &amp; </td> 
   <td colname="col6" morerows="1"> n.d. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pares clave-valor</b> <p>(standard) </p> </td> 
   <td colname="col2"> <code> x = 1 &amp; x = 2 &amp; y = 3 &amp; y = 4 </code> </td> 
   <td colname="col3"> x, y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Clave única</b> <p>(serial) </p> </td> 
   <td colname="col2"> <code> x = 1; 2; 3 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col5"> n.d. </td> 
   <td colname="col6" morerows="1"> ; </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pares clave-valor</b> (serial) </td> 
   <td colname="col2"> <code> x = 1; 2 &amp; y = 3; 4 </code> </td> 
   <td colname="col3"> x, y </td> 
   <td colname="col5"> &amp; </td> 
  </tr> 
 </tbody> 
</table>

