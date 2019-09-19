---
description: Define y describe pares de clave-valor estándar y serializados.
keywords: integration code
seo-description: Define y describe pares de clave-valor estándar y serializados.
seo-title: Pares de clave-valor explicados
solution: Audience Manager
title: Pares de clave-valor explicados
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Pares de clave-valor explicados{#key-value-pairs-explained}

Define y describe pares de clave-valor estándar y serializados.

<!-- 

c_key_value_explained.xml

 -->

Un par clave-valor consta de dos elementos de datos relacionados: Clave, que es una constante que define el conjunto de datos (por ejemplo, sexo, color, precio) y un valor, que es una variable que pertenece al conjunto (por ejemplo, hombre/mujer, verde, 100). Totalmente formado, un par clave-valor podría tener el siguiente aspecto:

* `gender = male`
* `color = green`
* `price > 100`

## Pares de clave-valor estándar y serializados {#standard-serialized-pairs}

Los destinos aceptan datos de clave-valor en *`standard`* o *`serialized`* formato. El formato estándar organiza los datos en pares clave-valor independientes. Cada clave se indica explícitamente, incluso cuando se utiliza nuevamente para definir un valor diferente. Por el contrario, el formato serializado comprime varios valores en un conjunto definido por una sola clave. Además, en un par serializado, se utiliza un indicador especial para separar los valores dentro del conjunto de valor clave. Finalmente, los valores de clave estándar y serializados pueden contener uno o varios valores. En la tabla siguiente se proporcionan ejemplos de formatos de clave-valor estándar y serie.

| Formato | Clave única | Par de clave-valor |
|---|---|---|
| **Estándar** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Serializado** | `x=1;2` | `x=1;2&y=3;4` |



## Teclas, delimitadores y separadores {#keys-delimiters-separators}

Al trabajar con datos serializados, debe especificar los caracteres que separan los valores *dentro* y *entre* los pares clave-valor. Los elementos de los pares de clave-valor se definen de la siguiente manera:

* **** Clave: Identificador único en el par clave-valor.
* **** Delimitador de valores: Separa pares clave-valor individuales.
* **** Separador clave-valor: Separa una clave de los valores de un par clave-valor.
* **** Separador de serie: Separa valores individuales dentro de pares de clave-valor serializados.

## Elementos de valor clave estándar y serializados {#standard-serialized-key-value-elements}

<table id="table_62B0498441034A719C9DB57276777D40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo </th> 
   <th colname="col2" class="entry"> Ejemplo </th> 
   <th colname="col3" class="entry"> Clave </th> 
   <th colname="col4" class="entry"> Separador de clave-valor </th> 
   <th colname="col5" class="entry"> Delimitador de valor clave </th> 
   <th colname="col6" class="entry"> Separador de serie </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Clave única</b> <p>(standard) </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col4" morerows="3"> = </td> 
   <td colname="col5" morerows="1"> &amp; </td> 
   <td colname="col6" morerows="1"> n.d. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Par clave-valor</b> <p>(standard) </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2&amp;y=3&amp;y=4 </code> </td> 
   <td colname="col3"> x, y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Clave única</b> <p>(serie) </p> </td> 
   <td colname="col2"> <code> x=1;2;3 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col5"> n.d. </td> 
   <td colname="col6" morerows="1"> ; </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Par</b> clave-valor (serie) </td> 
   <td colname="col2"> <code> x=1;2&amp;y=3;4 </code> </td> 
   <td colname="col3"> x, y </td> 
   <td colname="col5"> &amp; </td> 
  </tr> 
 </tbody> 
</table>

