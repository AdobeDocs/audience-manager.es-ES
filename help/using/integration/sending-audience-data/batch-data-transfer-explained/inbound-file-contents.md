---
description: Campos obligatorios, sintaxis y reglas que debe seguir al dar formato a un archivo de datos de rasgos de entrada.
solution: Audience Manager
title: 'Contenido del archivo de datos de entrada: sintaxis, caracteres no válidos, variables y ejemplos'
uuid: 88699b29-1502-4183-a9a4-be70692a02bb
feature: Inbound Data Transfers
exl-id: 894f1923-6c78-41d2-b6a2-eebf56eaa29e
source-git-commit: dbb557928a296d3dd5f0646644e2ca0cdc11dfdc
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 3%

---

# Contenido del archivo de datos de entrada: sintaxis, caracteres no válidos, variables y ejemplos {#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

Campos obligatorios, sintaxis y reglas que debe seguir al dar formato a un archivo de datos de rasgos de entrada.

## Sintaxis del contenido del archivo {#file-content-syntax}

Los campos del archivo de datos de entrada deben aparecer en el orden indicado a continuación. En este ejemplo, se han agregado los símbolos `<` `>` para ayudar a separar visualmente cada elemento. No es necesario que los incluya en el archivo de datos.

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

Para ver otros formatos de contenido de archivo aceptados, consulte [Integraciones de socios personalizadas](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>Tenemos un límite de 200 líneas que podemos procesar por cada ID de usuario enviado en el archivo de datos de entrada. Por ejemplo, si envía 300 líneas para un ID de usuario, las 200 primeras líneas se conservan y las 100 líneas adicionales se descartan. En el ejemplo siguiente, tiene razón porque envía tres líneas para el ID de usuario 1 y el ID de usuario 2. No aplicamos un límite al número de características o pares de clave-valor que se incluyen en una línea.
>
>```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## Variables de archivo definidas {#file-variables-defined}

La tabla enumera y define las variables utilizadas en un archivo de datos entrantes correctamente formateado. La letra en *cursiva* indica un marcador de posición de variable.

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
      <li id="li_23829FE2F6464E33859B3E388FCD106B">Identificador de usuario único asignado por el Audience Manager </span> de <span class="keyword"> ( UUID de Audience Manager <a href="../../../reference/ids-in-aam.md"> </a>). </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">Un ID de usuario único asignado en su sistema CRM ( <a href="../../../reference/ids-in-aam.md"> DPUUID, en el Audience Manager </a>). </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">Un ID de dispositivo móvil Android o iOS en su forma original sin modificar según lo expuesto por el sistema operativo móvil. </li> 
     </ul> </p> <p>Para ID móviles: </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">Formato IDFA: Los ID deben estar en mayúsculas y no tener hash. Por ejemplo, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Formato Android: Los ID deben estar en minúsculas y no tener hash. Por ejemplo, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Separe el ID de usuario y los ID de rasgos con un solo delimitador de tabulación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>trait ID </i> </code> </p> </td> 
   <td colname="col2"> <p>El identificador de rasgo del Audience Manager </span> <span class="keyword">. Le rogamos que incluya <i>solo características integradas</i> en los archivos de datos de entrada. No procesamos ningún otro tipo de rasgos en la transferencia de datos de entrada. </p> <p> <p>Nota: El ID de rasgo se puede encontrar mediante el método de GET que devuelve detalles sobre todos los rasgos. Para obtener más información, consulte <a href="../../../api/rest-api-main/api-traits.md"> Métodos de API de rasgos </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Formato [!UICONTROL Trait IDs] {#formatting-trait-ids}

En la tabla siguiente se describen los prefijos que identifican [!UICONTROL trait] nombres o identificadores en un archivo de datos de entrada. Vea los [archivos de ejemplo](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples) para ver ejemplos.

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
   <td colname="col2"> <p>El prefijo <code> d_sid </code> indica a nuestro sistema que el identificador es un identificador de rasgo </span> de Audience Manager <span class="keyword">. Es el mismo ID que se muestra en la interfaz de usuario. También puede devolver ID de rasgos con el método de API <code> GET </code>. Consulte <a href="../../../api/rest-api-main/api-traits.md"> métodos de API de rasgos </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_unsid= </code> </p> </td> 
   <td colname="col2"> <p>Los datos con el prefijo <code> d_unsid </code> quitan a los usuarios de esa característica. El prefijo <code> d_unsid </code> se omite en un archivo <code> overwrite </code>. </p> <p>El prefijo <code> d_unsid= </code> indica a nuestro sistema que el identificador es un identificador de rasgo </span> de Audience Manager <span class="keyword">. Es el mismo ID que se muestra en la interfaz de usuario. También puede devolver ID de rasgos con el método de API <code> GET </code>. Consulte <a href="../../../api/rest-api-main/api-traits.md"> métodos de API de rasgos </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> Las reglas de rasgos </a> le permiten establecer criterios para la clasificación de rasgos. Si da formato a una regla de rasgos como <code> ic == trait ID </code>, puede enviar rasgos en una lista simple con formato de coma. </p> <p>Por ejemplo, supongamos que crea estas 3 reglas de rasgos: </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic == "123" </code> </li>
      <li> <code> ic == "456" </code> </li>
      <li> <code> ic == "789" </code> </li>
     </ul> </p> <p>Estos rasgos están asociados con la clave <code> ic </code>. Esto permite crear una lista de rasgos más sencilla en el archivo de datos. Además, no necesita incluir el prefijo <code> ic </code>. Como resultado, el contenido del archivo de datos podría tener este aspecto: </p> <p>
     <code> 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
      <i>user ID</i>&nbsp;&lt;TAB&gt;&nbsp;123,456,789 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pares clave-valor </p> </td> 
   <td colname="col2"> <p>Los datos de rasgos se pueden formatear como pares clave-valor mediante cadenas alfanuméricas. Existen varias formas de dar formato a los pares clave-valor, como se muestra a continuación: </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> "key" = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> "key" = "value" </code> </li> 
     </ul><code> "age"="32" </code> , <code> "gender"=m </code> , <code> model = "pickup truck" </code> , <code> product = tablet </code> son todos ejemplos de pares clave-valor correctamente formateados. </p> </td> 
  </tr>
 </tbody>
</table>

## Caracteres no válidos en [!UICONTROL Trait IDs], [!UICONTROL User IDs] y pares clave-valor {#invalid-chars}

### [!UICONTROL Trait IDs]

[!UICONTROL Trait IDs] solo consta de caracteres numéricos. Le rogamos que incluya *solamente[!UICONTROL onboarded traits]* en los archivos de datos de entrada. No se procesa ningún otro tipo de [!UICONTROL trait] en la transferencia de datos de entrada.

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
   <td colname="col2"> <p><i>No</i> use un símbolo de dos puntos codificado (<code> %3A </code>) o no codificado ( : ) en los DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de dispositivo móvil iOS (IDFA) o Android </p> </td> 
   <td colname="col2"> <p>Los ID de dispositivos móviles deben tener el formato estricto que se muestra a continuación: </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">Formato IDFA: Los ID deben estar en mayúsculas y no tener hash. Por ejemplo, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Formato Android: Los ID deben estar en minúsculas y no tener hash. Por ejemplo, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Pares de clave-valor

Los nombres de valores con formato incorrecto en un par clave-valor también causan problemas. Siga estas reglas al crear o asignar un nombre al valor en un par clave-valor:

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
   <td colname="col2"> <p>Puede utilizar el carácter de comilla en la parte clave y valor del par clave-valor, de esta manera: </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_city = "New York", d_city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> "d_city" = "New York", "d_city" = "San Francisco" </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Carácter de guión (-) </p> </td> 
   <td colname="col2"> <p>Ignoramos las señales de guion al principio de las teclas. Por ejemplo, <code> -product = camera </code> se interpreta como <code> product = camera </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>No</i> use <code> TAB </code> en lugar de valores vacíos en pares clave-valor. Use solamente <code> TAB </code> para separar variables en el archivo de datos de entrada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \n, \t </code> </p> </td> 
   <td colname="col2"> <p>No utilice los caracteres de nueva línea o tabulación (<code> \n, \t </code>) en claves o valores. </p> </td> 
  </tr>
 </tbody>
</table>

## Ejemplos de archivos de datos {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formato del archivo de datos </th> 
   <th colname="col2" class="entry"> Descripción y ejemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Con <code> d_sid </code> o <code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>Este archivo de datos muestra un usuario cualificado para los rasgos 24, 26, 27 y que se ha eliminado de los rasgos 28 y 29. </p> <p> 
     <code>
       59767559181262060060278870901087098252&nbsp;&nbsp;d_sid=24,d_sid=26,d_sid=27,d_unsid=28,d_unsid=29 
     </code> </p> <p>Nota:  <p>En lugar de utilizar d_unsid, también puede quitar rasgos de los perfiles de usuario mediante la siguiente sintaxis: </p> <p> 
      <code>
        59767559181262060060278870901087098252&nbsp;28:0,&nbsp;29:0 
      </code> </p> <p> 
      <code>
        59767559181262060060278870901087098252&nbsp;28:-1,&nbsp;29:-1 
      </code> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Con <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>Estos rasgos se han agregado a una regla de rasgos con el prefijo <code> ic </code>. Como tal, puede agregarlos al archivo de datos separados por comas como se muestra. Una pestaña separa el UUID y los ID de rasgos. El prefijo <code> ic </code> no es necesario en el archivo. </p> <p><b>ID numéricos</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&nbsp;&nbsp;30608,50354,50338,50352,30626 
     </code> </p> <p><b>Id. de cadena</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&nbsp;&nbsp;ic=52,ic=55 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Con pares clave-valor </p> </td> 
   <td colname="col2"> Estos datos de archivo utilizan pares de clave-valor para pasar datos al Audience Manager <span class="keyword"> </span>. <p> 
     <code>
       59767559181262060060278870901087098252&nbsp;“gender”=”female”,“luxury_shopper”=”yes” 
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[Descargue](assets/ftp_dpm_1234_1445374061.overwrite) el archivo de datos de ejemplo si necesita ejemplos adicionales. El archivo de descarga tiene una extensión de archivo `.overwrite`. Puede abrirlo con un editor de texto sencillo.

## Matriz de ejemplos {#examples-matrix}

El gráfico siguiente muestra ejemplos de la forma correcta de dar formato a los archivos de entrada, según el [tipo de identificadores](../../../reference/ids-in-aam.md) y el método por el cual desee agregar [!UICONTROL traits] a los perfiles.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de ID/Operación </th> 
   <th colname="col2" class="entry"> Usar d_sid para agregar características a un perfil de usuario </th> 
   <th colname="col3" class="entry"> Use d_unsid para eliminar rasgos de un perfil de usuario </th> 
   <th colname="col4" class="entry"> Envíe pares de clave-valor para añadir características a un perfil de usuario </th> 
   <th colname="col5" class="entry"> Utilice el prefijo ic para añadir rasgos a un perfil de usuario </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>UUID DE AUDIENCE MANAGER </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-1"> Ejemplo 1 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-2"> Ejemplo 2 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-3"> Ejemplo 3 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-4"> Ejemplo 4 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Google Advertising ID para dispositivos Android </p> </td> 
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

### Ejemplo 1 {#example-1}

Use [!UICONTROL trait IDs] para enviar información de calificación [!UICONTROL trait] para [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Ejemplo 2 {#example-2}

Use [!UICONTROL trait IDs] para enviar información de descalificación de [!UICONTROL trait] para [!DNL Audience Manager] [!DNL UUIDs].

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

Use el prefijo `ic` para enviar la información de calificación [!UICONTROL trait] para [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

o

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Ejemplo 5 {#example-5}

Use [!UICONTROL trait IDs] para enviar información de calificación de [!UICONTROL trait] para [!DNL Android] dispositivos.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Ejemplo 6 {#example-6}

Use [!UICONTROL trait IDs] para enviar información de descalificación de [!UICONTROL trait] para [!DNL Android] dispositivos.

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

Envíe pares de clave-valor para agregar información de calificación [!UICONTROL trait] para [!DNL Android] dispositivos.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

o

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Ejemplo 8 {#example-8}

Use el prefijo `ic` para enviar información de calificación [!UICONTROL trait] para dispositivos [!DNL Android].

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

o

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Ejemplo 9 {#example-9}

Use [!UICONTROL trait IDs] para enviar información de calificación de [!UICONTROL trait] para [!DNL iOS] dispositivos.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Ejemplo 10 {#example-10}

Use [!UICONTROL trait IDs] para enviar información de descalificación de [!UICONTROL trait] para [!DNL iOS] dispositivos.

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

Envíe pares de clave-valor para agregar información de calificación [!UICONTROL trait] para [!DNL iOS] dispositivos.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

o

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Ejemplo 12 {#example-12}

Use el prefijo `ic` para enviar información de calificación [!UICONTROL trait] para dispositivos [!DNL iOS].

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

o

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Ejemplo 13 {#example-13}

Use [!UICONTROL trait IDs] para enviar información de calificación [!UICONTROL trait] para [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Ejemplo 14 {#example-14}

Use [!UICONTROL trait IDs] para enviar información de descalificación de [!UICONTROL trait] para [!DNL DPUUIDs].

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

Envíe pares de clave-valor para agregar la información de calificación [!UICONTROL trait] para [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

o

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Ejemplo 16 {#example-16}

Use el prefijo `ic` para enviar la información de calificación [!UICONTROL trait] para [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

o

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORELIKETHIS]
>
>* [Generador de rasgos](../../../features/traits/about-trait-builder.md)
