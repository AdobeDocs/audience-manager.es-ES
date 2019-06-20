---
description: Un par clave-valor consta de elementos relacionados, una clave que define el conjunto de datos (por ejemplo, sexo, color, precio) y un valor, que es una variable que pertenece al conjunto (p. ej. hombre/mujer, verde, 100). El Generador de destino envía datos formateados como pares clave-valor.
seo-description: Un par clave-valor consta de elementos relacionados, una clave que define el conjunto de datos (por ejemplo, sexo, color, precio) y un valor, que es una variable que pertenece al conjunto (p. ej. hombre/mujer, verde, 100). El Generador de destino envía datos formateados como pares clave-valor.
seo-title: Pares de clave-valor estándar y de serie
solution: Audience Manager
title: Pares de clave-valor estándar y de serie
uuid: 43789419-5 b 3 f -4 e 62-b 2 e 0-2722340 bdd 41
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Standard and Serial Key-Value Pairs {#standard-and-serial-key-value-pairs}

Un par clave-valor consta de elementos relacionados: Una clave, que es una constante que define el conjunto de datos (por ejemplo: sexo, color, precio) y un valor, que es una variable que pertenece al conjunto (p. ej. hombre/mujer, verde, 100). [!UICONTROL Destination Builder] envía datos formateados como pares clave-valor.

## Basic Key-Value Pairs {#basic-key-value-pairs}

Totalmente formado, un conjunto básico de pares clave-valor podría tener el aspecto siguiente:

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serial Key-Value Pairs {#standard-serial-key-value-pairs}

Destinations accept key-value data in *`standard`* or *`serialized`* format.

* **Pares de clave-valor estándar:** Aplica formato a los datos de destino en pares de clave-valor separados. Cada clave se indica explícitamente, incluso cuando se vuelve a utilizar para definir un valor diferente.
* **Pares de clave-valor serializados:** Condensa varios valores en un solo par clave-valor. En un par de valor clave serializado, un indicador especial separa los valores dentro del conjunto de valores clave.

Los valores de clave estándar y serializados pueden contener valores únicos o múltiples. En la tabla siguiente se proporcionan ejemplos de formatos estándar y de valor clave de serie.

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formato </th>
   <th colname="col2" class="entry"> Pares de clave-valor únicos </th>
   <th colname="col3" class="entry"> Par de valores clave múltiples </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Estándar</b> </p> </td>
   <td colname="col2"> <p> <code> x = 1 &amp; x = 2 </code> </p> </td>
   <td colname="col3"> <p> <code> x = 1 &amp; x = 2 &amp; y = 3 &amp; y = 4 </code> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Serializado</b> </p> </td> 
   <td colname="col2"> <p> <code> x = 1; 2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x = 1; 2 &amp; y = 3; 4 </code> </p> </td>
  </tr>
 </tbody>
</table>

## Delimiters and Separators {#delimiters-separators}

The characters that separate values within and between keys and values are known as *`delimiters`* and *`separators`*. Esto es especialmente importante cuando envía segmentos a un destino en un formato de serie. La serialización permite pasar varios valores con una sola clave y combinar pares clave-valor. Los delimitadores y separadores se definen de la siguiente manera:

* **Separador de valor clave:** Separa una clave y un valor dentro de un par de valores clave.
* **Delimitador de valor clave:** Separa conjuntos de pares de valor clave.
* **Separador de serie:** Separa varios valores dentro de conjuntos de pares de clave-valor serializados.

## Ejemplos {#examples}

With [!UICONTROL Destination Builder] you can format key-value data in several different ways. Veamos algunos ejemplos de cada tipo.

<table id="table_C2FBDC887C8C4CC88B1B2A7CF8E2795F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ejemplos de pares clave-valor </th> 
   <th colname="col2" class="entry"> Ejemplo </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Clave única estándar</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 </code> </p> </td> 
   <td colname="col3"> <p>Un simple conjunto de pares clave-valor. El ejemplo contiene estos elementos: </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">Clave: X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">Valores: 1, 2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">Separador: = </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">Delimitador de valor clave: &amp; &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Varios pares de clave-valor</b> (no serie) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>Conjunto de varios pares de clave-valor que pasan valores con conjuntos de valores clave separados. El ejemplo contiene estos elementos: </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">Claves: X, Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">Valores: 1, 2, 3, 4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">Separador: = </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">Delimitador de valor clave: &amp; &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Clave única de serie</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1; 2; 3 </code> </p> </td> 
   <td colname="col3"> <p>Conjunto de valores clave que pasa varios valores con una sola clave. Dado que esta clave tiene varios valores, se conoce como par de valor clave serializado. El ejemplo contiene estos elementos: </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">Clave: X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">Valores: 1, 2, 3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">Separador: = </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">Separador de serie: punto y coma </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Varios pares de clave-valor</b> (serial) </p> </td> 
   <td colname="col2"> <p> <code> X = 1; 2 &amp; Y = 3; 4 </code> </p> </td> 
   <td colname="col3"> <p>Conjunto de varios pares de clave-valor que pasan varios valores en claves separadas. El ejemplo contiene estos elementos: </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">Claves: X, Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">Valores: 1, 2, 3, 4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">Separador: = </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">Delimitador: &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">Separador de serie: punto y coma </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Destination Serialization {#destination-serialized}

Un destino serializado combina varias características en una sola cadena y envía dicha información a un destino.

<!-- c_dest_serialized.xml -->

La transmisión de datos serializada ayuda a mejorar la eficacia porque varias características se activan secuencialmente, en lugar de en paralelo. Esto proporciona al servidor de destino tiempo suficiente para recibir, procesar y devolver datos antes de responder a solicitudes adicionales.

### Destinos admitidos

In [!DNL Audience Manager], you can serialize and send data to just about any destination you want to work with. However, before using this feature, you will need to know the destination [!DNL URL] and where to place some required or optional macros. Obtenga la información sobre la ubicación de macro de su socio de destino. See [Destination Macros Defined](../../features/destinations/destination-macros.md#destination-macros-defined) for more information.