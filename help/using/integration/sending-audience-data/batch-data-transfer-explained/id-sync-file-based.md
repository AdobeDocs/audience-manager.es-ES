---
description: Describe los campos, la sintaxis y las convenciones de nomenclatura que se utilizan para la sincronización de ID basada en archivos. Asigne un nombre al contenido del archivo y organice según estas especificaciones.
seo-description: Describe los campos, la sintaxis y las convenciones de nomenclatura que se utilizan para la sincronización de ID basada en archivos. Asigne un nombre al contenido del archivo y organice según estas especificaciones.
seo-title: Requisitos de nombre y contenido para archivos de sincronización de ID
solution: Audience Manager
title: Requisitos de nombre y contenido para archivos de sincronización de ID
uuid: bfe 42 af 9-9149-4 da 3-830 e-f 227 c 4 e 610 c 2
translation-type: tm+mt
source-git-commit: 5624eac36a7f2b8892136688f89fc22af241fc3a

---


# Requisitos de nombre y contenido para archivos de sincronización de ID {#name-and-content-requirements-for-id-synchronization-files}

Describe los campos, la sintaxis y las convenciones de nomenclatura que se utilizan para la sincronización de ID basada en archivos. Asigne un nombre al contenido del archivo y organice según estas especificaciones.

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *cursiva*, paréntesis `[ ]` `( )`, etc.) en este documento indican elementos y opciones de código. Consulte [Convenciones de estilo para elementos de código y texto](../../../reference/code-style-elements.md) para obtener más información.

## Sintaxis y ejemplos del nombre de archivo {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

Los nombres de archivos de ID contienen los siguientes elementos opcionales y requeridos:

`adobe_id_`*`[c2c_id_]`*`MASTERDPID_DPID[_DPID_DPID`*`]_`*`TIMESTAMP`*`.sync[.`*`SPLIT_NUMBER`*`][.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_ id</code> </p> </td> 
   <td colname="col2"> <p>Prefijo estático que identifica el archivo como un archivo de sincronización de ID. Utilice este prefijo cuando copie los ID de dispositivo a otros ID de dispositivo o ID de cliente (dpuuids).  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c 2 c_ id</code> </p> </td> 
   <td colname="col2"> <p>Prefijo estático que identifica el archivo como un archivo de sincronización de ID para destinos basados en personas. Utilice este prefijo cuando copie ID de cliente (dpuuids) en direcciones de correo electrónico hash para destinos basados en personas.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> El ID de proveedor de datos principal es el ID principal de los dpid en el nombre del archivo. Además, el primer ID de usuario del archivo de datos corresponde al ID maestro. Los siguientes dpid son otros identificadores que pertenecen a la maestra. Sincronización Asigna dpids en el nombre del archivo a UUID del archivo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>ID del proveedor de datos. Estos ID representan entidades o fuentes de datos asociadas al DPID maestro. Sincronización Asigna dpids en el nombre del archivo a UUID del archivo. </p> <p>El número de dpid del nombre del archivo debe coincidir con el número de UUID del archivo de datos. Por ejemplo, supongamos que su nombre de archivo contiene un DPID maestro y 3 dpids. El archivo de datos debe incluir 4 columnas correspondientes de UUID, con formato tal como se describe en la sección de contenido de archivos siguiente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>Una marca de tiempo UNIX de 10 dígitos en segundos. La marca de tiempo ayuda a hacer único cada nombre de archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> . sync</code> </p> </td> 
   <td colname="col2"> <p>Indica una sincronización normal y completa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>. SPLIT_ NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Un entero. Se utiliza cuando divide archivos grandes en varios archivos más pequeños. Esto ayuda a mejorar los tiempos de procesamiento. El número indica qué parte del archivo original está enviando. Consulte los ejemplos de nombre de archivo a continuación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Especifica que el archivo se comprime con compresión gzip opcional. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Ejemplos de nombres de archivos

Los ejemplos siguientes muestran nombres de archivos formateados correctamente. Los nombres de archivos podrían tener un aspecto similar.

<ul class="simplelist"> 
 <li> <code> adobe_ id_ 111_ 222_ 333_ 444_ 1454442149. sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> Para la nomenclatura de archivos de sincronización de ID (prefijo c 2 c) para destinos basados en personas, consulte [Flujo de trabajo A - Personalización basada en toda la actividad en línea combinada con datos](../../../features/destinations/people-based-destinations-workflow-combined.md) sin conexión o [flujo de trabajo B - Personalización basada en datos sin conexión](../../../features/destinations/people-based-destinations-workflow-offline.md).

## Sintaxis y ejemplos del contenido de archivos {#file-content-syntax}

El contenido de un archivo de ID incluye los siguientes elementos:

*`UUID`* `<tab>`*`UUID`* `<tab>`*`UUID`*`<tab>` *`UUID`*

El archivo contiene ID de usuario ([!DNL UUID]). En cada fila, separe los ID con una ficha. El siguiente ejemplo muestra un archivo de ID formateado correctamente. Su contenido podría ser similar.

```
abc123 def456 ghi789 xyz987
```

## Sincronización coincide con dpuuids a UUIDS {#sync-matches-dpuuids-uuids}

El propósito de un archivo de sincronización de ID es sincronizar [los dpuuid](../../../reference/ids-in-aam.md) desde sus propias fuentes de datos con [!DNL Audience Manager] UUID. La sincronización asigna las [!DNL DPUUID]s de la maestra [!DNL DPID] y las relacionadas [!DNL DPID]con las [!DNL Audience Manager][!DNL UUID]s. Donde ponga los ID en el nombre del archivo y el cuerpo, determina cómo se asignan estos identificadores entre sí. Por ejemplo, tome los dos archivos de ejemplo que se muestran aquí:

* **Archivo 1:**`adobe_id_0_12345_1476312152.sync`

* **Archivo 2:**`adobe_id_12345_67890_1476312876.sync`

<br/>

Dado el nombre y el contenido de muestra, los ID se asignan juntos de este modo:

**Archivo 1** ( [descargar archivo de ejemplo](assets/adobe_id_0_12345_1476312152.sync))

| DPID 0 = Adobe Audience Manager uuids | DPID 12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ 3017 D_ 2 kzktoxkfyiagwbajoqwrcqkxl-ttrj 6 E 4 njamr 38 |
| 67412682083411995725538770443620307584 | XYZ 3017 BBR 4 dafjwfm 6 D 4 GB 4 ln_ T 5 jk_ f 7 rdecqns 9 wfna 7 h 70 |
| 89159024796760343733111707646026765593 | XYZ 3017 prypid 8 tzfhkee-GE 034 LI -53 Jde 0 utcyciwd 0 A 2 olm |
| 66552757407517449462805881945288602094 | XYZ 3017 qvbddd-bljs 28 dpxiqufmibxe 3_ 55 bvqjmlwregju 2 M |
| 66184778222667870903738139438735041506 | XYZ 3017 q 9 r 60 kuhpoca_ Ek-btcn 2 iu 1 hyvaue 0 rd 412 tzbycmw |

Paso 1: El proceso de sincronización de ID sincronizará los [!DNL DPUUID]s desde [!DNL DPID] 12345 con [!DNL Audience Manager][!DNL UUID]los de la columna izquierda. Observe que "0" [!DNL DPID] en el nombre del archivo representa [!DNL Audience Manager][!DNL UUID]s.<br/>


**Archivo 2** ( [Descargar archivo de muestra](assets/adobe_id_12345_67890_1477846458.sync))

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ 3017 D_ 2 kzktoxkfyiagwbajoqwrcqkxl-ttrj 6 E 4 njamr 38 | 4598060374 |
| XYZ 3017 BBR 4 dafjwfm 6 D 4 GB 4 ln_ T 5 jk_ f 7 rdecqns 9 wfna 7 h 70 | 4581274262 |
| XYZ 3017 prypid 8 tzfhkee-GE 034 LI -53 Jde 0 utcyciwd 0 A 2 olm | 4392434426 |
| XYZ 3017 qvbddd-bljs 28 dpxiqufmibxe 3_ 55 bvqjmlwregju 2 M | 2351382994 |
| XYZ 3017 q 9 r 60 kuhpoca_ Ek-btcn 2 iu 1 hyvaue 0 rd 412 tzbycmw | 4601584763 |

Paso 2: las [!DNL DPUUID]s de [!DNL DPID] 12345 se sincronizaron en el paso 1 con Audience Manager [!DNL UUID]s. Lo que esta sincronización de ID hará es sincronizar [!DNL DPUUID]los s desde [!DNL DPID] 67890 con Audience Manager [!DNL UUID]desde el paso 1.

<br/>

## Otros requisitos de formato {#other-format-reqs}

Los ID de usuario no pueden:

* Tener fichas en el mismo ID. Las fichas solo se utilizan para separar ID individuales en el archivo de datos.
* Contiene información personal identificable ([!UICONTROL PII]).
* Utilice [!DNL URL] la codificación. Pasar solo ID no codificados.

Las filas que finalizan con fichas o espacios no se procesarán ni se realizarán. Como regla, asegúrese de mantener borrado el final de las filas.