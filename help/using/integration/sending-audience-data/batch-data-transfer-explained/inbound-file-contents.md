---
description: Campos obligatorios, sintaxis y reglas que se deben seguir al formatear un fichero de datos de rasgos de entrada.
solution: Audience Manager
title: 'Contenido Archivo de datos de entrada: Sintaxis, caracteres no válidos, variables y ejemplos'
uuid: 88699b29-1502-4183-a9a4-be70692a02bb
feature: Inbound Data Transfers
exl-id: 894f1923-6c78-41d2-b6a2-eebf56eaa29e
source-git-commit: dbb557928a296d3dd5f0646644e2ca0cdc11dfdc
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 3%

---

# Contenido Archivo datos de entrada: Sintaxis, caracteres no válidos, variables y ejemplos {#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

Campos obligatorios, sintaxis y reglas que se deben seguir al formatear un fichero de datos de rasgos de entrada.

## Sintaxis de contenido de Archivo {#file-content-syntax}

Los campos del archivo de datos de entrada deben aparecer en el orden que se muestra a continuación. En este ejemplo, se `<` `>` han agregado los símbolos para ayudar a separar visualmente cada elemento. No necesita incluirlas en el archivo de datos.

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

Para conocer otros formatos aceptados contenido archivos, consulte [Integraciones](/help/using/integration/sending-audience-data/custom-partner-integrations.md) personalizadas de socios.

>[!NOTE]
>
>Tenemos un límite de 200 líneas que podemos procesar para cada ID de usuario enviado en el archivo de datos de entrada. Por ejemplo, si envía 300 líneas para un ID de usuario, las primeras 200 líneas se mantienen y las 100 líneas adicionales se descartan. En el siguiente ejemplo, está bien porque está enviando 3 líneas cada una para usuario ID 1 y usuario ID 2. No imponemos un límite en el número de rasgos o pares clave-valor que se incluyen en una línea.
>
>```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## Variables de Archivo definidas {#file-variables-defined}

La tabla enumera y define las variables utilizadas en un archivo de datos de entrada con el formato correcto. La letra en *cursiva* indica un marcador de posición de variable.

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
      <li id="li_23829FE2F6464E33859B3E388FCD106B">ID de usuario único asignado por <span class="keyword"> Audience Manager </span> ( <a href="../../../reference/ids-in-aam.md"> Audience Manager UUID </a>). </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">ID de usuario únicos asignados en el sistema de CRM ( <a href="../../../reference/ids-in-aam.md"> DPUUID, en Audience Manager </a>). </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">Un ID de dispositivos móvil de Android o iOS en su forma original, sin modificar según lo expuesto por el sistema operativo móvil. </li> 
     </ul> </p> <p>Para los ID móviles: </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">formato IDFA: los ID deben estar en mayúsculas y no tener hash. Por ejemplo, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Android formato: los ID deben estar en minúsculas y no tener hash. Por ejemplo, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Separe el ID de usuario y los ID de características con un único delimitador pestaña. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>trait ID </i> </code> </p> </td> 
   <td colname="col2"> <p>La <span class="keyword"> Audience Manager </span> ID de rasgos. Le pedimos que incluya <i>solo las características integradas en los</i> archivos de datos de entrada. No procesamos ningún otro tipo de rasgo en la transferencia de datos entrante. </p> <p> <p>Nota: El ID de rasgo se puede encontrar mediante la método GET que devuelve detalles sobre todos sus caracteres. Para obtener más información, consulte <a href="../../../api/rest-api-main/api-traits.md"> Métodos </a>de API de rasgos . </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Formateo [!UICONTROL Trait IDs] {#formatting-trait-ids}

La tabla siguiente describe los prefijos que identifican [!UICONTROL trait] nombres o ID en un archivo de datos de entrada. Consulte los archivos[ de ](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples)muestra para ver ejemplos.

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
   <td colname="col2"> <p>El <code> d_sid </code> prefijo le dice a nuestro sistema que el ID es un <span class="keyword"> ID de rasgo Audience Manager </span> . Este es el mismo ID que se muestra en la interfaz de usuario. También puede devolver ID de rasgos con el método API <code> GET </code> . Consulte <a href="../../../api/rest-api-main/api-traits.md"> Métodos de API de </a>rasgos . </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_unsid= </code> </p> </td> 
   <td colname="col2"> <p>Los datos con el prefijo quitan <code> d_unsid </code> a los usuarios de esa característica. El <code> d_unsid </code> prefijo se ignora en un <code> overwrite </code> archivo. </p> <p>El <code> d_unsid= </code> prefijo le dice a nuestro sistema que el ID es un <span class="keyword"> ID de rasgo Audience Manager </span> . Este es el mismo ID que se muestra en la interfaz de usuario. También puede devolver ID de rasgos con el método API <code> GET </code> . Consulte <a href="../../../api/rest-api-main/api-traits.md"> Métodos de API de </a>rasgos . </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> Las reglas de </a> rasgos permiten establecer criterios para la calificación de los rasgos. Si formato un rasgo regla como <code> ic == trait ID </code>, puede enviar características en un simple lista con formato de coma. </p> <p>Por ejemplo, supongamos que crea estas 3 reglas de características: </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic == "123" </code> </li>
      <li> <code> ic == "456" </code> </li>
      <li> <code> ic == "789" </code> </li>
     </ul> </p> <p>Estas características se asocian con la <code> ic </code> clave. Esto permite crear un lista de rasgos más sencillo en el archivo de datos. Y no es necesario que incluya el <code> ic </code> prefijo. Como resultado, el contenido del archivo de datos podría verse gustar esto: </p> <p>
     <code> 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
      <i>user ID</i>&nbsp;&lt;TAB&gt;&nbsp;123,456,789 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pares clave-valor </p> </td> 
   <td colname="col2"> <p>Los datos de rasgos se pueden formatear como pares clave-valor mediante cadenas alfanuméricas. Hay varias formas de dar formato a los pares clave-valor, como se muestra a continuación: </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> "key" = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> "key" = "value" </code> </li> 
     </ul><code> "age"="32" </code> , <code> "gender"=m </code> , <code> model = "pickup truck" </code> , son <code> product = tablet </code> todos ejemplos de pares clave-valor con formato correcto. </p> </td> 
  </tr>
 </tbody>
</table>

## Caracteres no válidos en [!UICONTROL Trait IDs]y [!UICONTROL User IDs] pares Valor clave {#invalid-chars}

### [!UICONTROL Trait IDs]

[!UICONTROL Trait IDs] consisten únicamente en caracteres numéricos. Le pedimos que incluya *solo[!UICONTROL onboarded traits]* en los archivos de datos de entrada. No procesamos ningún otro [!UICONTROL trait] tipo en la transferencia de datos entrante.

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
   <td colname="col2"> <p><i>No</i> utilice dos puntos codificados ( <code> %3A </code>) ni dos puntos no codificados ( : ) en DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de dispositivos móvil de iOS (IDFA) o Android </p> </td> 
   <td colname="col2"> <p>Los ID de dispositivos móviles deben tener un formato estricto como se muestra aquí: </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">formato IDFA: los ID deben estar en mayúsculas y no tener hash. Por ejemplo, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Android formato: los ID deben estar en minúsculas y no tener hash. Por ejemplo, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Pares clave-Valor

El formato incorrecto de los nombres de valores en un par clave-valor también causa problemas. Siga estas reglas al crear o nombrar el valor en un par clave-valor:

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Carácter </th> 
   <th colname="col2" class="entry"> Requisito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Carácter entre comillas (") </p> </td> 
   <td colname="col2"> <p>Puede usar el carácter de comillas en la parte clave y en la parte de valor del par clave-valor, gustar así: </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_city = "New York", d_city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> "d_city" = "New York", "d_city" = "San Francisco" </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Carácter de guión (-) </p> </td> 
   <td colname="col2"> <p>Ignoramos las señales de guión en la inicio de teclas. Por ejemplo, <code> -product = camera </code> se interpreta como <code> product = camera </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>No</i> utilice <code> TAB </code> en lugar de valores vacíos en pares de clave-valor. Solo se utiliza <code> TAB </code> para separar variables en el archivo de datos de entrada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \n, \t </code> </p> </td> 
   <td colname="col2"> <p>No utilice las nuevas líneas ni pestaña caracteres ( <code> \n, \t </code>) en claves o valores. </p> </td> 
  </tr>
 </tbody>
</table>

## Ejemplos de Archivo de datos {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formato Archivo datos </th> 
   <th colname="col2" class="entry"> Descripción y ejemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Con <code> d_sid </code> o <code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>Este archivo de datos muestra un usuario calificado para los rasgos 24, 26, 27 y que se ha eliminado de los rasgos 28 y 29. </p> <p> 
     <code>
       59767559181262060060278870901087098252&nbsp;&nbsp;d_sid=24,d_sid=26,d_sid=27,d_unsid=28,d_unsid=29 
     </code> </p> <p>Nota:  <p>En lugar de usar d_unsid, también puede quitar características de usuario perfiles mediante la siguiente sintaxis: </p> <p> 
      <code>
        59767559181262060060278870901087098252&nbsp;28:0,&nbsp;29:0 
      </code> </p> <p> 
      <code>
        59767559181262060060278870901087098252&nbsp;28:-1,&nbsp;29:-1 
      </code> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Con <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>Estas características se han agregado a una regla de características con el <code> ic </code> prefijo. Como tal, puede agregarlos al archivo de datos separados por comas, como se muestra a continuación. Un pestaña separa el UUID y el ID de rasgo. El <code> ic </code> prefijo no es necesario en el archivo. </p> <p><b>ID numéricas</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&nbsp;&nbsp;30608,50354,50338,50352,30626 
     </code> </p> <p><b>ID de cadena</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&nbsp;&nbsp;ic=52,ic=55 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Con pares de clave-valor </p> </td> 
   <td colname="col2"> Los datos de este archivo utilizan pares de clave-valor para pasar los datos a <span class="keyword"> Audience Manager </span>. <p> 
     <code>
       59767559181262060060278870901087098252&nbsp;“gender”=”female”,“luxury_shopper”=”yes” 
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[Descargue](assets/ftp_dpm_1234_1445374061.overwrite) el archivo de datos de ejemplo si necesita ejemplos adicionales. El archivo descargar tiene una `.overwrite` extensión de archivo. Puede abrirlo con una simple editor de texto.

## Matriz de ejemplos {#examples-matrix}

El siguiente gráfico muestra ejemplos de la forma correcta de formato los archivos entrantes, según el tipo de ID[ y el método mediante el cual desee agregar ](../../../reference/ids-in-aam.md) a los [!UICONTROL traits]perfiles.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de ID / Operación </th> 
   <th colname="col2" class="entry"> Utilice d_sid para agregar características a una usuario perfil </th> 
   <th colname="col3" class="entry"> Utilice d_unsid para eliminar características de una usuario perfil </th> 
   <th colname="col4" class="entry"> Enviar pares de clave-valor para añadir características a una perfil de usuario </th> 
   <th colname="col5" class="entry"> Use el prefijo ic para agregar características a una perfil de usuario </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Audience Manager UUID </p> </td> 
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
   <td colname="col1"> <p>IDFA de Apple para iOS dispositivos </p> </td> 
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

Se utiliza [!UICONTROL trait IDs] para enviar [!UICONTROL trait] información de cualificación para [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Ejemplo 2 {#example-2}

Se utiliza [!UICONTROL trait IDs] para enviar [!UICONTROL trait] información de descalificación para [!DNL Audience Manager] [!DNL UUIDs].

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

Envíe pares de clave-valor para agregar [!UICONTROL trait] información de cualificación para [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

o

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Ejemplo 4 {#example-4}

Utilice el prefijo para enviar información de `ic` cualificación para [!UICONTROL trait] [!DNL Audience Manager].[!DNL UUIDs]

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

o

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Ejemplo 5 {#example-5}

Se utiliza [!UICONTROL trait IDs] para enviar [!UICONTROL trait] información de calificación para [!DNL Android] dispositivos.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Ejemplo 6 {#example-6}

Se utiliza [!UICONTROL trait IDs] para enviar [!UICONTROL trait] información de descalificación para [!DNL Android] dispositivos.

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

Envíe pares de clave-valor para añadir [!UICONTROL trait] información de cualificación para [!DNL Android] dispositivos.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

o

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Ejemplo 8 {#example-8}

Utilice el prefijo para enviar `ic` información de [!UICONTROL trait] calificación para [!DNL Android] dispositivos.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

o

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Ejemplo 9 {#example-9}

Se utiliza [!UICONTROL trait IDs] para enviar [!UICONTROL trait] información de calificación para [!DNL iOS] dispositivos.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Ejemplo 10 {#example-10}

Se utiliza [!UICONTROL trait IDs] para enviar [!UICONTROL trait] información de descalificación para [!DNL iOS] dispositivos.

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

Envíe pares de clave-valor para añadir [!UICONTROL trait] información de cualificación para [!DNL iOS] dispositivos.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

o

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Ejemplo 12 {#example-12}

Utilice el prefijo para enviar `ic` información de [!UICONTROL trait] calificación para [!DNL iOS] dispositivos.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

o

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Ejemplo 13 {#example-13}

Se utiliza [!UICONTROL trait IDs] para enviar [!UICONTROL trait] información de cualificación para [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Ejemplo 14 {#example-14}

Se utiliza [!UICONTROL trait IDs] para enviar [!UICONTROL trait] información de descalificación para [!DNL DPUUIDs].

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

Envíe pares de clave-valor para agregar [!UICONTROL trait] información de cualificación para [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

o

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Ejemplo 16 {#example-16}

Utilice el prefijo para enviar `ic` información de [!UICONTROL trait] cualificación para [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

o

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORELIKETHIS]
>
>* [Generador de rasgo](../../../features/traits/about-trait-builder.md)
