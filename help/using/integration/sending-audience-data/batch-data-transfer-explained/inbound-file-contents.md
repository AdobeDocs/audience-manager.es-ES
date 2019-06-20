---
description: Campos requeridos, sintaxis y reglas que debe seguir al dar formato a un archivo de datos de características entrantes.
seo-description: Campos requeridos, sintaxis y reglas que debe seguir al dar formato a un archivo de datos de características entrantes.
seo-title: Sintaxis del contenido del archivo de datos de entrada, caracteres no válidos, variables y ejemplos
solution: Audience Manager
title: Sintaxis del contenido del archivo de datos de entrada, caracteres no válidos, variables y ejemplos
uuid: 88699 b 29-1502-4183-a 9 a 4-be 70692 a 02 bb
translation-type: tm+mt
source-git-commit: 5a822460f93bb7295edafff03104ae7626b69a51

---


# Inbound Data File Contents: Syntax, Invalid Characters, Variables, and Examples{#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

Campos requeridos, sintaxis y reglas que debe seguir al dar formato a un archivo de datos de características entrantes.

## File Content Syntax {#file-content-syntax}

Los campos del archivo de datos entrantes deben aparecer en el orden que se muestra a continuación. In this example, the `<` `>` symbols have been added to help separate each element visually. No es necesario incluirlas en el archivo de datos.

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

For other accepted file content formats, see [Custom Partner Integrations](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>Tenemos un límite de 200 líneas que podemos procesar para cada ID de usuario enviado en el archivo de datos de entrada. Por ejemplo, si envía 300 líneas para un ID de usuario, se mantendrán las primeras 200 líneas y se descartarán las 100 líneas adicionales. En el ejemplo siguiente, es bueno porque está enviando 3 líneas cada una para ID de usuario 1 y ID de usuario 2. No imponemos un límite en el número de características o pares clave-valor que incluye en una línea.
>
>```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## File Variables Defined {#file-variables-defined}

La tabla enumera y define las variables utilizadas en un archivo de datos de entrada con formato correcto. La letra en *cursiva* indica un marcador de posición de variable.

<table id="table_FE043CE392B34D5194111188E5C39671"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>ID de usuario </i> </code> </p> </td> 
   <td colname="col2"> <p>Un ID de usuario puede ser: </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B">A unique user ID assigned by <span class="keyword"> Audience Manager </span> ( <a href="../../../reference/ids-in-aam.md"> Audience Manager UUID </a>). </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">A unique user ID assigned in your CRM system ( <a href="../../../reference/ids-in-aam.md"> DPUUID, in Audience Manager </a>). </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">Un ID móvil de Android o iOS en su formulario original sin modificar como expuesto por el sistema operativo móvil. </li> 
     </ul> </p> <p>Para los ID móviles: </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">Formato IDFA: Los ID deben ser mayúsculas y no hash. For example, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Formato de Android: Los ID deben tener letra minúscula y no hash. For example, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Separe los ID de usuario y de características con un solo delimitador de tabuladores. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>ID de característica </i></code> </p> </td> 
   <td colname="col2"> <p>The <span class="keyword"> Audience Manager </span> trait ID. We ask that you include <i>only onboarded traits</i> in inbound data files. No procesamos ningún otro tipo de característica en la transferencia de datos entrantes. </p> <p> <p>Nota: El ID de característica se puede encontrar utilizando el método GET que devuelve detalles sobre todas las características. For more information, see <a href="../../../api/rest-api-main/api-traits.md"> Trait API Methods </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Formatting Trait IDs {#formatting-trait-ids}

En la tabla siguiente se describen los prefijos que identifican los nombres o ID de características en un archivo de datos de entrada. See the [sample files](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples) for examples.

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prefijo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ sid = </code> </p> </td> 
   <td colname="col2"> <p>The <code> d_sid </code> prefix tells our system that the ID is an <span class="keyword"> Audience Manager </span> trait ID. Es el mismo ID que se muestra en la interfaz de usuario. You can also return trait IDs with the API <code> GET </code> method. See <a href="../../../api/rest-api-main/api-traits.md"> Trait API Methods </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_ unsid = </code> </p> </td> 
   <td colname="col2"> <p>Data prefixed with <code> d_unsid </code> removes users from that trait. The <code> d_unsid </code> prefix is ignored in an <code> overwrite </code> file. </p> <p>The <code> d_unsid= </code> prefix tells our system that the ID is an <span class="keyword"> Audience Manager </span> trait ID. Es el mismo ID que se muestra en la interfaz de usuario. You can also return trait IDs with the API <code> GET </code> method. See <a href="../../../api/rest-api-main/api-traits.md"> Trait API Methods </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic = </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> Las reglas de características </a> permiten definir criterios para la cualificación de características. If you format a trait rule as <code> ic == trait ID </code>, you can send in traits in a simple comma formatted list. </p> <p>Por ejemplo, supongamos que crea estas tres reglas de características: </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic = = "123" </code> </li>
      <li> <code> ic = = "456" </code> </li>
      <li> <code> ic = = "789" </code> </li>
     </ul> </p> <p>These traits are associated with the <code> ic </code> key. Esto permite crear una lista de rasgos más sencilla en el archivo de datos. And, you do not need to include the <code> ic </code> prefix. Como resultado, el contenido del archivo de datos podría tener este aspecto: </p> <p>
     <code><i>ID de usuario</i>&lt; TAB &gt; 123.456.789 </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pares clave-valor </p> </td> 
   <td colname="col2"> <p>Los datos de características pueden formatearse como pares clave-valor usando cadenas alfanuméricas. Existen varias formas de dar formato a pares clave-valor, como se muestra a continuación: </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> " key " = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> " key " =" value " </code> </li> 
     </ul><code> «age» = "32" </code> , <code> "gender" = m </code> , <code> model = "pick kup truck" </code> , <code> product = tablet </code> son todos ejemplos de pares de clave-valor con formato correcto. </p> </td> 
  </tr>
 </tbody>
</table>

## Invalid Characters in Trait IDs, User IDs and Key-Value Pairs {#invalid-chars}

### ID de características

Los ID de características sólo constan de caracteres numéricos. We ask that you include *only onboarded traits* in inbound data files. No procesamos ningún otro tipo de característica en la transferencia de datos entrantes.

### ID de usuarios

<table id="table_8C5C7271B813441EA2D45CA2FE2A6C59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de ID </th> 
   <th colname="col2" class="entry"> Requisito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p><i>No</i> utilice dos puntos codificados ( <code> % 3 A </code>) ni dos codificados (: ) en dpuuids. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobile iOS (IDFA) o ID de dispositivo Android </p> </td> 
   <td colname="col2"> <p>Los ID de dispositivos móviles deben tener un formato estricto como se muestra aquí: </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">Formato IDFA: Los ID deben ser mayúsculas y no hash. For example, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Formato de Android: Los ID deben tener letra minúscula y no hash. For example, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Pares clave-valor

Los nombres de valores con formato incorrecto en un par clave-valor también causan problemas. Siga estas reglas al crear o dar nombre al valor en un par clave-valor:

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Carácter </th> 
   <th colname="col2" class="entry"> Requisito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Carácter de cita (") </p> </td> 
   <td colname="col2"> <p>Puede utilizar el carácter de comillas en la clave y en la parte value del par clave-valor, como así: </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_ city = "New York", d_ city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> " d_ city " =" New York "," d_ city " =" San Francisco " </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Carácter de guión (-) </p> </td> 
   <td colname="col2"> <p>Ignoramos los signos de guión al principio de las claves. For example, <code> -product = camera </code> is interpreted as <code> product = camera </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>No</i> utilice <code> TAB </code> en lugar de valores vacíos en pares clave-valor. Only use <code> TAB </code> to separate variables in the inbound data file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \ n,\ t </code> </p> </td> 
   <td colname="col2"> <p>Do not use the new line or tab characters ( <code> \n, \t </code>) in keys or in values. </p> </td> 
  </tr>
 </tbody>
</table>

## Data File Examples {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formato de archivo de datos </th> 
   <th colname="col2" class="entry"> Descripción y ejemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>With <code> d_sid </code> or <code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>Este archivo de datos muestra un usuario cualificado para características 24, 26, 27 y se ha eliminado de trait 28 y 29. </p> <p> 
     <code>59767559181260060060278870901087098252 &amp; amp; nbsp; &amp; amp; nbsp; d_ sid = 24, d_ sid = 26, d_ sid = 27, d_ unsid = 28, d_ unsid = 29 </code>
  </p> <p>Nota:  <p>En lugar de utilizar d_ unsid, también puede eliminar características de perfiles de usuario utilizando la siguiente sintaxis: </p> <p> 
      <code>59767559181260060060278870901087098252 &amp; amp; nbsp; 28:0, &amp; amp; nbsp; 29:0 </code>
  </p> <p> 
      <code>59767559181260060060278870901087098252 &amp; amp; nbsp; 28:-1 y amp; nbsp; 29:-1 </code>
  </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>With <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>These traits have been added to a trait rule with the <code> ic </code> prefix. Como tal, puede agregarlas al archivo de datos separado por comas como se muestra. Una ficha separa el UUID y los ID de características. The <code> ic </code> prefix is not required in the file. </p> <p><b>ID numéricos</b> </p> <p> 
     <code>Dbwfoc 3 dhfmncfbh 2 M 4 F 9 zkjexmnnrdh 2 pxvni 1 &amp; amp; nbsp; &amp; amp; nbsp; 30608,50354,50338,50352,30626 </code>
  </p> <p><b>ID de cadena</b> </p> <p> 
     <code>Dbwfoc 3 dhfmncfbh 2 M 4 F 9 zkjexmnnrdh 2 pxvni 1 &amp; amp; nbsp; &amp; amp; nbsp; ic = 52, ic = 55 </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Con pares clave-valor </p> </td> 
   <td colname="col2"> This file data uses key-value pairs to pass in data to <span class="keyword"> Audience Manager </span>. <p> 
     <code>59767559181260060060278870901087098252 &amp; amp; nbsp; «gender» =» femenino», «luxury_ shopper» =» sí» </code>
  </p> </td> 
  </tr> 
 </tbody> 
</table>

[Descargue](assets/ftp_dpm_1234_1445374061.overwrite) el archivo de datos de ejemplo si necesita ejemplos adicionales. The download file has a `.overwrite` file extension. Puede abrirla con un editor de texto sencillo.

## Examples Matrix {#examples-matrix}

The chart below shows examples of the correct way to format your Inbound files, depending on the [type of IDs](../../../reference/ids-in-aam.md) and the method by which you want to add traits to profiles.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de ID/Operación </th> 
   <th colname="col2" class="entry"> Utilizar d_ sid para agregar características a un perfil de usuario </th> 
   <th colname="col3" class="entry"> Utilizar d_ unsid para eliminar características de un perfil de usuario </th> 
   <th colname="col4" class="entry"> Enviar en pares de clave-valor para agregar características a un perfil de usuario </th> 
   <th colname="col5" class="entry"> Use el prefijo ic para agregar características a un perfil de usuario </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>UUID de Audience Manager </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-1"> Ejemplo 1 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-2"> Ejemplo 2 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-3"> Ejemplo 3 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-4"> Ejemplo 4 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de publicidad de Google para dispositivos Android </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-5"> Ejemplo 5 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-6"> Ejemplo 6 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-7"> Ejemplo 7 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-8"> Ejemplo 8 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apple IDFA para dispositivos iOS </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-9"> Ejemplo 9 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-10"> Ejemplo 10 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11"> Ejemplo 11 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-12"> Ejemplo 12 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Su propio ID de CRM (DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> Ejemplo 13 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> Ejemplo 14 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> Ejemplo 15 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> Ejemplo 16 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Example 1 {#example-1}

Utilice los ID de características para enviar información de cualificación de características para los UUID de Audience Manager.

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Example 2 {#example-2}

Utilice los ID de características para enviar información de descualificación de características para los UUID de Audience Manager.

```
59767559181262060060278870901087098252 <TAB> d_unsid=24, d_unsid=26, d_unsid=27
```

o

```
59767559181262060060278870901087098252 <TAB> 24:0, 26:0, 27:0
```

o

```
59767559181262060060278870901087098252 <TAB> 24:-1, 26:-1, 27:-1
```

### Example 3 {#example-3}

Envíe pares de clave-valor para agregar información de cualificación de características para los UUID de Audience Manager.

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

o

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 4 {#example-4}

Utilice el prefijo ic para enviar información de cualificación de características para UUID de Audience Manager.

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

o

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Example 5 {#example-5}

Utilice los ID de características para enviar información de cualificación de características para dispositivos Android.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 6 {#example-6}

Utilice los ID de características para enviar información de descualificación de características para dispositivos Android.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

o

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:0, 26:0, 27:0
```

o

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:-1, 26:-1, 27:-1
```

### Example 7 {#example-7}

Envíe pares de clave-valor para agregar información de cualificación de características para dispositivos Android.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

o

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 8 {#example-8}

Utilice el prefijo ic para enviar información de cualificación de características para dispositivos Android.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

o

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Example 9 {#example-9}

Utilice los ID de características para enviar información de cualificación de características para dispositivos iOS.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 10 {#example-10}

Utilice los ID de características para enviar información de descualificación de características para dispositivos iOS.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

o

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:0, 26:0, 27:0
```

o

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:-1, 26:-1, 27:-1
```

### Example 11 {#example-11}

Envíe pares de clave-valor para agregar información de cualificación de características para dispositivos iOS.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

o

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Example 12 {#example-12}

Utilice el prefijo ic para enviar información de cualificación de características para dispositivos iOS.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

o

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Example 13 {#example-13}

Utilice los ID de características para enviar información de cualificación de características para los DPUUID.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 14 {#example-14}

Utilice los ID de características para enviar información de descualificación de características para los DPUUID.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

o

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:0, 26:0, 27:0
```

o

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:-1, 26:-1, 27:-1
```

### Example 15 {#example-15}

Envíe pares de clave-valor para agregar información de cualificación de características para dpuuids.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

o

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 16 {#example-16}

Utilice el prefijo ic para enviar información de cualificación de características para dpuuids.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

o

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORE_ LIKE_ THIS]
>
>* [Generador de rasgo](../../../features/traits/about-trait-builder.md)

