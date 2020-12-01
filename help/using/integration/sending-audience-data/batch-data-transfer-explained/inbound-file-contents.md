---
description: Campos requeridos, sintaxis y reglas que debe seguir al dar formato a un archivo de datos de características de entrada.
seo-description: Campos requeridos, sintaxis y reglas que debe seguir al dar formato a un archivo de datos de características de entrada.
seo-title: Sintaxis del contenido del archivo de datos de entrada, caracteres no válidos, variables y ejemplos
solution: Audience Manager
title: Sintaxis del contenido del archivo de datos de entrada, caracteres no válidos, variables y ejemplos
uuid: 88699b29-1502-4183-a9a4-be70692a02bb
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1193'
ht-degree: 4%

---


# Contenido del archivo de datos de entrada: sintaxis, caracteres no válidos, variables y ejemplos {#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

Campos requeridos, sintaxis y reglas que debe seguir al dar formato a un archivo de datos de características de entrada.

## Sintaxis del contenido del archivo {#file-content-syntax}

Los campos del archivo de datos de entrada deben aparecer en el orden que se muestra a continuación. En este ejemplo, se han agregado los símbolos `<` `>` para ayudar a separar visualmente cada elemento. No es necesario incluirlos en el archivo de datos.

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

Para ver otros formatos de contenido de archivo aceptados, consulte [Integraciones de socio personalizadas](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>Tenemos un límite de 200 líneas que podemos procesar por cada ID de usuario enviado en el archivo de datos de entrada. Por ejemplo, si envía 300 líneas para un ID de usuario, se conservan las primeras 200 líneas y se descartan las 100 líneas adicionales. En el ejemplo siguiente, es bueno porque está enviando 3 líneas para el ID de usuario 1 y el ID de usuario 2. No se impone un límite en el número de atributos o pares de clave-valor que se incluyen en una línea.
>
>
```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## Variables de archivo definidas {#file-variables-defined}

La tabla lista y define las variables utilizadas en un archivo de datos de entrada con el formato correcto. La letra en *cursiva* indica un marcador de posición de variable.

<table id="table_FE043CE392B34D5194111188E5C39671"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>User ID </i> </code> </p> </td> 
   <td colname="col2"> <p>Un ID de usuario puede ser: </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B">ID de usuario único asignado por el Audience Manager <span class="keyword"> </span> ( <a href="../../../reference/ids-in-aam.md"> UUID de Audience Manager </a>). </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">Un ID de usuario único asignado en el sistema CRM ( <a href="../../../reference/ids-in-aam.md"> DPUUID, en el Audience Manager </a>). </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">Un ID de dispositivo móvil Android o iOS en su formulario original sin modificar tal como lo expone el sistema operativo móvil. </li> 
     </ul> </p> <p>Para ID móviles: </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">Formato IDFA: Los ID deben escribirse en mayúsculas y no con hash. Por ejemplo, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Formato Android: Los ID deben escribirse en minúsculas y no con hash. Por ejemplo, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Separe el ID de usuario y los ID de rasgo con un único delimitador de tabulación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>trait ID </i> </code> </p> </td> 
   <td colname="col2"> <p>El ID de característica <span class="keyword"> del Audience Manager </span>. Le pedimos que incluya <i>sólo características integradas</i> en los archivos de datos de entrada. No procesamos ningún otro tipo de característica en la transferencia de datos de entrada. </p> <p> <p>Nota:  La ID de característica se puede encontrar utilizando el método de GET que devuelve detalles sobre todas sus características. Para obtener más información, consulte <a href="../../../api/rest-api-main/api-traits.md"> Métodos de API de características </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Formato [!UICONTROL Trait IDs] {#formatting-trait-ids}

En la tabla siguiente se describen los prefijos que identifican [!UICONTROL trait] nombres o ID en un archivo de datos de entrada. Consulte los [archivos de ejemplo](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples) para ver ejemplos.

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prefijo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_sid= </code> </p> </td> 
   <td colname="col2"> <p>El prefijo <code> d_sid </code> indica a nuestro sistema que el ID es un ID de rasgo <span class="keyword"> </span> del Audience Manager. Es el mismo ID que se muestra en la interfaz de usuario. También puede devolver ID de características con el método API <code> GET </code>. Consulte <a href="../../../api/rest-api-main/api-traits.md"> Métodos de API de características </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_unsid= </code> </p> </td> 
   <td colname="col2"> <p>Los datos con el prefijo <code> d_unsid </code> quitan a los usuarios de esa característica. El prefijo <code> d_unsid </code> se omite en un archivo <code> overwrite </code>. </p> <p>El prefijo <code> d_unsid= </code> indica a nuestro sistema que el ID es un ID de rasgo <span class="keyword"> </span> del Audience Manager. Es el mismo ID que se muestra en la interfaz de usuario. También puede devolver ID de características con el método API <code> GET </code>. Consulte <a href="../../../api/rest-api-main/api-traits.md"> Métodos de API de características </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> Las reglas de características  </a> permiten establecer criterios para la calificación de características. Si da formato a una regla de características como <code> ic == trait ID </code>, puede enviar características en una lista sencilla con formato de coma. </p> <p>Por ejemplo, supongamos que crea estas 3 reglas de características: </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic == "123" </code> </li>
      <li> <code> ic == "456" </code> </li>
      <li> <code> ic == "789" </code> </li>
     </ul> </p> <p>Estas características están asociadas con la clave <code> ic </code>. Esto le permite crear una lista de rasgos más sencilla en el archivo de datos. Y no es necesario incluir el prefijo <code> ic </code>. Como resultado, el contenido del archivo de datos podría tener este aspecto: </p> <p>
     <code> 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
      <i>user ID</i>&nbsp;&lt;TAB&gt;&nbsp;123,456,789 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Par clave-valor </p> </td> 
   <td colname="col2"> <p>Los datos de características se pueden formatear como pares de clave-valor mediante cadenas alfanuméricas. Existen varias formas de dar formato a los pares clave-valor, como se muestra a continuación: </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> "key" = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> "key" = "value" </code> </li> 
     </ul><code> "age"="32" </code> ,  <code> "gender"=m </code> ,  <code> model = "pickup truck" </code> todos  <code> product = tablet </code> son ejemplos de pares de clave-valor con formato correcto. </p> </td> 
  </tr>
 </tbody>
</table>

## Caracteres no válidos en los pares [!UICONTROL Trait IDs], [!UICONTROL User IDs] y clave-valor {#invalid-chars}

### [!UICONTROL Trait IDs]

[!UICONTROL Trait IDs] consiste únicamente en caracteres numéricos. Le pedimos que incluya *sólo[!UICONTROL onboarded traits]* en los archivos de datos de entrada. No procesamos ningún otro tipo [!UICONTROL trait] en la transferencia de datos de entrada.

### [!UICONTROL User IDs]

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
   <td colname="col2"> <p><i>No </i> utilice dos puntos (  <code> %3A </code>) codificados ni dos puntos (: ) en DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de dispositivo móvil iOS (IDFA) o Android </p> </td> 
   <td colname="col2"> <p>Los ID de dispositivos móviles deben tener un formato estricto, como se muestra a continuación: </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">Formato IDFA: Los ID deben escribirse en mayúsculas y no con hash. Por ejemplo, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Formato Android: Los ID deben escribirse en minúsculas y no con hash. Por ejemplo, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Par de clave-valor

Los nombres de valores con formato incorrecto en un par de clave-valor también causan problemas. Siga estas reglas cuando cree o asigne un nombre al valor en un par clave-valor:

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Carácter </th> 
   <th colname="col2" class="entry"> Requisito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Carácter de comillas (") </p> </td> 
   <td colname="col2"> <p>Puede utilizar el carácter de comillas en la clave y en la parte de valor del par clave-valor, de este modo: </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_city = "New York", d_city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> "d_city" = "New York", "d_city" = "San Francisco" </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Carácter de guión (-) </p> </td> 
   <td colname="col2"> <p>Ignoramos las señales de guiones en el inicio de las llaves. Por ejemplo, <code> -product = camera </code> se interpreta como <code> product = camera </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>No </i> realice ninguna acción  <code> TAB </code> en lugar de valores vacíos en pares clave-valor. Utilice sólo <code> TAB </code> para separar variables en el archivo de datos de entrada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \n, \t </code> </p> </td> 
   <td colname="col2"> <p>No utilice la nueva línea o los caracteres de tabulación ( <code> \n, \t </code>) en claves o en valores. </p> </td> 
  </tr>
 </tbody>
</table>

## Ejemplos de archivos de datos {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formato de archivo de datos </th> 
   <th colname="col2" class="entry"> Descripción y ejemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Con <code> d_sid </code> o <code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>Este archivo de datos muestra un usuario cualificado para las características 24, 26, 27 y que se ha eliminado de las características 28 y 29. </p> <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;&amp;nbsp;d_sid=24,d_sid=26,d_sid=27,d_unsid=28,d_unsid=29 
     </code> </p> <p>Nota:  <p>En lugar de utilizar d_unsid, también puede eliminar características de perfiles de usuario mediante la siguiente sintaxis: </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:0,&amp;nbsp;29:0 
      </code> </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:-1,&amp;nbsp;29:-1 
      </code> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>con <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>Estas características se han agregado a una regla de características con el prefijo <code> ic </code>. Como tal, puede agregarlos al archivo de datos separados por comas, como se muestra. Una ficha separa el UUID y los ID de características. El prefijo <code> ic </code> no es necesario en el archivo. </p> <p><b>ID numéricos</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;30608,50354,50338,50352,30626 
     </code> </p> <p><b>ID de cadena</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;ic=52,ic=55 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Con pares de clave-valor </p> </td> 
   <td colname="col2"> Los datos de este archivo utilizan pares clave-valor para pasar datos al <span class="keyword"> Audience Manager </span>. <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;“gender”=”female”,“luxury_shopper”=”yes” 
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[](assets/ftp_dpm_1234_1445374061.overwrite) Descargue el archivo de datos de ejemplo si necesita ejemplos adicionales. El archivo de descarga tiene una extensión de archivo `.overwrite`. Puede abrirlo con un editor de texto sencillo.

## Matriz de ejemplos {#examples-matrix}

El gráfico siguiente muestra ejemplos de la forma correcta de dar formato a los archivos entrantes, según el [tipo de ID](../../../reference/ids-in-aam.md) y el método por el cual desee agregar [!UICONTROL traits] a los perfiles.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de ID / Operación </th> 
   <th colname="col2" class="entry"> Usar d_sid para agregar características a un perfil de usuario </th> 
   <th colname="col3" class="entry"> Usar d_unsid para eliminar características de un perfil de usuario </th> 
   <th colname="col4" class="entry"> Enviar pares de clave-valor para agregar características a un perfil de usuario </th> 
   <th colname="col5" class="entry"> Utilice el prefijo ic para agregar características a un perfil de usuario </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>UUID de Audience Manager </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-1"> Ejemplo 1 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-2"> Ejemplo 2 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-3"> Ejemplo 3  </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-4"> Ejemplo 4  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de publicidad de Google para dispositivos Android </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-5"> Ejemplo 5  </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-6"> Ejemplo 6  </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-7"> Ejemplo 7  </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-8"> Ejemplo 8  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apple IDFA para dispositivos iOS </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-9"> Ejemplo 9  </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-10"> Ejemplo 10  </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11"> Ejemplo 11  </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-12"> Ejemplo 12  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Su propio ID de CRM (DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> Ejemplo 13  </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> Ejemplo 14  </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> Ejemplo 15  </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> Ejemplo 16  </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Ejemplo 1 {#example-1}

Utilice [!UICONTROL trait IDs] para enviar información de calificación [!UICONTROL trait] para [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Ejemplo 2 {#example-2}

Utilice [!UICONTROL trait IDs] para enviar [!UICONTROL trait] información de descalificación para [!DNL Audience Manager] [!DNL UUIDs].

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

### Ejemplo 3 {#example-3}

Envíe pares de clave-valor para agregar información de calificación [!UICONTROL trait] para [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

o

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Ejemplo 4 {#example-4}

Utilice el prefijo `ic` para enviar información de calificación [!UICONTROL trait] para [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

o

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Ejemplo 5 {#example-5}

Utilice [!UICONTROL trait IDs] para enviar información de calificación [!UICONTROL trait] para dispositivos [!DNL Android].

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Ejemplo 6 {#example-6}

Utilice [!UICONTROL trait IDs] para enviar [!UICONTROL trait] información de descalificación para dispositivos [!DNL Android].

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

### Ejemplo 7 {#example-7}

Envíe pares de clave-valor para agregar información de calificación [!UICONTROL trait] para dispositivos [!DNL Android].

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

o

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Ejemplo 8 {#example-8}

Utilice el prefijo `ic` para enviar información de calificación [!UICONTROL trait] para dispositivos [!DNL Android].

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

o

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Ejemplo 9 {#example-9}

Utilice [!UICONTROL trait IDs] para enviar información de calificación [!UICONTROL trait] para dispositivos [!DNL iOS].

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Ejemplo 10 {#example-10}

Utilice [!UICONTROL trait IDs] para enviar [!UICONTROL trait] información de descalificación para dispositivos [!DNL iOS].

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

### Ejemplo 11 {#example-11}

Envíe pares de clave-valor para agregar información de calificación [!UICONTROL trait] para dispositivos [!DNL iOS].

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

o

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Ejemplo 12 {#example-12}

Utilice el prefijo `ic` para enviar información de calificación [!UICONTROL trait] para dispositivos [!DNL iOS].

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

o

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Ejemplo 13 {#example-13}

Utilice [!UICONTROL trait IDs] para enviar información de calificación [!UICONTROL trait] para [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Ejemplo 14 {#example-14}

Utilice [!UICONTROL trait IDs] para enviar [!UICONTROL trait] información de descalificación para [!DNL DPUUIDs].

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

### Ejemplo 15 {#example-15}

Envíe pares de clave-valor para agregar información de calificación [!UICONTROL trait] para [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

o

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Ejemplo 16 {#example-16}

Utilice el prefijo `ic` para enviar información de calificación [!UICONTROL trait] para [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

o

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORELIKETHIS]
>
>* [Generador de rasgos ](../../../features/traits/about-trait-builder.md)

