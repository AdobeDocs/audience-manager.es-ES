---
description: A [!DNL key-value pair] consiste en [!DNL related elements]. Clave, que es una constante que define el conjunto de datos (por ejemplo, sexo, color, precio) y un valor, que es una variable que pertenece al conjunto (por ejemplo, hombre/mujer, verde, 100). El Generador de destinos envía datos formateados como pares clave-valor.
solution: Audience Manager
title: Estándar y serie [!DNL Key-value pairs]
uuid: 43789419-5b3f-4e62-b2e0-2722340bdd41
feature: Conceptos básicos de destino
exl-id: b37c829b-66be-4c31-8198-bc032371279e
source-git-commit: 0dfe96a4644c61fb5bc22e4791bfd09c574dcf34
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 2%

---

# Par de clave-valor estándar y serie {#standard-and-serial-key-value-pairs}

Un par clave-valor consta de elementos relacionados: Una clave, que es una constante que define el conjunto de datos (p. ej.: sexo, color, precio) y un valor, que es una variable que pertenece al conjunto (por ejemplo, hombre/mujer, verde, 100). [!UICONTROL Destination Builder] envía datos formateados como pares clave-valor.

## Pares clave-valor básicos {#basic-key-value-pairs}

Totalmente formado, un conjunto básico de pares de clave-valor podría tener el siguiente aspecto:

* `gender = male`
* `color = green`
* `price > 100`

## Par de clave-valor estándar y serie {#standard-serial-key-value-pairs}

Los destinos aceptan datos de clave-valor en formato *`standard`* o *`serialized`* .

* **Pares de clave-valor estándar:** da formato a los datos de destino en pares de clave-valor independientes. Cada clave se indica explícitamente, incluso cuando se utiliza de nuevo para definir un valor diferente.
* **Pares clave-valor serializados:** condensa varios valores en un único par clave-valor. En un par clave-valor serializado, un indicador especial separa los valores del conjunto clave-valor.

Los valores de clave estándar y serializados pueden contener uno o varios valores. En la tabla siguiente se proporcionan ejemplos de formatos de clave-valor estándar y serie.

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formato </th>
   <th colname="col2" class="entry"> Pares de clave-valor único </th>
   <th colname="col3" class="entry"> Varios pares de clave-valor </th>
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
   <td colname="col2"> <p> <code> x = 1 ; 2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x = 1 ; 2 &amp; y = 3 ; 4 </code> </p> </td>
  </tr>
 </tbody>
</table>

## Delimitadores y separadores {#delimiters-separators}

Los caracteres que separan valores entre claves y valores se conocen como *`delimiters`* y *`separators`*. Esto resulta especialmente importante cuando se envían segmentos a un destino en formato de serie. La serialización permite pasar varios valores con una sola clave y combinar pares clave-valor. Los delimitadores y separadores se definen de la siguiente manera:

* **Separador clave-valor:** separa una clave y un valor de un par clave-valor.
* **Delimitador de clave-valor:** separa conjuntos de pares de clave-valor.
* **Separador de serie:** separa varios valores dentro de conjuntos de pares de clave-valor serializados.

## Ejemplos {#examples}

Con [!UICONTROL Destination Builder] puede dar formato a los datos clave-valor de varias formas diferentes. Veamos algunos ejemplos de cada tipo.

<table id="table_C2FBDC887C8C4CC88B1B2A7CF8E2795F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ejemplos de pares de clave-valor </th> 
   <th colname="col2" class="entry"> Ejemplo </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Clave única estándar</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 </code> </p> </td> 
   <td colname="col3"> <p>Conjunto sencillo de pares clave-valor. El ejemplo contiene estos elementos: </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">Clave: X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">Valores: 1, 2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">Separador: = </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">Delimitador de clave-valor: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Varios pares de clave-valor</b>  (no seriales) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>Conjunto de varios pares de clave-valor que pasan valores con conjuntos de clave-valor independientes. El ejemplo contiene estos elementos: </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">Claves: X, Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">Valores: 1, 2, 3, 4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">Separador: = </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">Delimitador de clave-valor: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Clave individual serie</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 ; 3 </code> </p> </td> 
   <td colname="col3"> <p>Conjunto de clave-valor que pasa varios valores con una sola clave. Como esta clave tiene varios valores, se conoce como par de clave-valor serializado. El ejemplo contiene estos elementos: </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">Clave: X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">Valores: 1, 2, 3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">Separador: = </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">Separador de serie: punto y coma </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Varios pares de clave-valor</b>  (serie) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 &amp; Y = 3 ; 4 </code> </p> </td> 
   <td colname="col3"> <p>Conjunto de varios pares de clave-valor que pasan varios valores en claves independientes. El ejemplo contiene estos elementos: </p> 
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

## Serialización de destino {#destination-serialized}

Un destino serializado combina varios rasgos en una sola cadena y envía esa información a un destino.

<!-- c_dest_serialized.xml -->

La transmisión de datos serializada ayuda a mejorar la eficacia, ya que múltiples características se activan secuencialmente, en lugar de en paralelo. Esto proporciona al servidor de destino tiempo suficiente para recibir, procesar y devolver datos antes de responder a solicitudes adicionales.

### Destinos admitidos

En [!DNL Audience Manager], puede serializar y enviar datos a casi cualquier destino con el que desee trabajar. Sin embargo, antes de utilizar esta función, deberá conocer el destino [!DNL URL] y dónde colocar algunas macros opcionales o obligatorias. Solicite la información sobre la colocación de macros a su socio de destino. Consulte [Macros de destino definidas](../../features/destinations/destination-macros.md#destination-macros-defined) para obtener más información.
