---
description: Describe los campos, sintaxis y convenciones de nomenclatura requeridos que se usan para la sincronización de ID basada en archivos. Asigne un nombre al archivo y organícelo según estas especificaciones.
seo-description: Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Name and organize your file contents according to these specifications.
seo-title: Name and Content Requirements for ID Synchronization Files
solution: Audience Manager
title: Requisitos de nomenclatura y contenido para archivos de sincronización de ID
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
feature: Inbound Data Transfers
exl-id: e6b3a438-f843-4a24-89fd-03ef77d7cf04
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 5%

---

# Requisitos de nomenclatura y contenido para archivos de sincronización de ID {#name-and-content-requirements-for-id-synchronization-files}

Describe los campos, sintaxis y convenciones de nomenclatura requeridos que se usan para la sincronización de ID basada en archivos. Asigne un nombre al archivo y organícelo según estas especificaciones.

>[!NOTE]
>
>Estilos de texto (`monospaced text`, *cursiva*, paréntesis `[ ]` `( )`, etc.) en este documento, indique los elementos y las opciones de código. Consulte [Convenciones de estilo para elementos de código y texto](../../../reference/code-style-elements.md) para obtener más información.

## Sintaxis y ejemplos del nombre del archivo {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

Los nombres de archivo de ID contienen los siguientes elementos obligatorios y opcionales:

*`[adobe_id_]`* *`[c2c_id_]`*`MASTERDPID_DPID`*`[_DPID]`*`_TIMESTAMP.sync`*`[.SPLIT_NUMBER]`*`[.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_id</code> </p> </td> 
   <td colname="col2"> <p>Prefijo estático que identifica el archivo como archivo de sincronización de ID. Utilice este prefijo cuando combine los ID de dispositivo con otros ID de dispositivo o ID de cliente (DPUUID).  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c2c_id</code> </p> </td> 
   <td colname="col2"> <p>Prefijo estático que identifica el archivo como archivo de sincronización de ID para destinos basados en personas. Utilice este prefijo al hacer coincidir los ID de cliente (DPUUID) con las direcciones de correo electrónico con hash para los destinos basados en personas.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> <p>El ID del proveedor de datos maestro es el ID principal de los DPID del nombre del archivo. Además, el primer ID de usuario del archivo de datos corresponde al ID de maestro. Los DPID subsiguientes son otros identificadores que pertenecen al maestro. La sincronización asigna los DPID del nombre de archivo a los UUID del archivo.</p> <p>AAM Este DPID solo debe contener ID de dispositivo, como UUID, GAID, IDFA, etc. de la. No puede contener DPUUID. Al hacerlo, la sincronización puede ser incorrecta.</p>  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>ID del proveedor de datos. Estos ID representan entidades o fuentes de datos asociadas al DPID maestro. La sincronización asigna los DPID del nombre de archivo a los UUID del archivo. </p> <p>El número de DPID del nombre de archivo debe coincidir con el número de UUID del archivo de datos. Por ejemplo, supongamos que su nombre de archivo contiene un DPID maestro y 3 DPID. El archivo de datos debe incluir 4 columnas correspondientes de UUID, con el formato descrito en la sección de contenido del archivo a continuación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>Una marca de tiempo UNIX de 10 dígitos en segundos. La marca de tiempo ayuda a que cada nombre de archivo sea único. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .sync</code> </p> </td> 
   <td colname="col2"> <p>Indica una sincronización normal y completa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>.SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Un entero. Se utiliza al dividir archivos grandes en varios archivos más pequeños. Esto ayuda a mejorar los tiempos de procesamiento. El número indica qué parte del archivo original está enviando. Consulte los ejemplos de nombre de archivo a continuación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Especifica que el archivo se comprime con compresión gzip opcional. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Ejemplos de nombres de archivo

Los siguientes ejemplos muestran nombres de archivos con el formato correcto. Sus nombres de archivo podrían ser similares.

<ul class="simplelist"> 
 <li> <code> adobe_id_111_222_333_444_1454442149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> Para la nomenclatura de archivos de sincronización de ID (prefijo c2c) para People-Based Destinations, consulte [Flujo de trabajo A: personalización basada en toda la actividad en línea combinada con datos sin conexión](../../../features/destinations/people-based-destinations-workflow-combined.md) o [Flujo de trabajo B: personalización basada en datos solo sin conexión](../../../features/destinations/people-based-destinations-workflow-offline.md).

## Sintaxis del contenido del archivo y ejemplos {#file-content-syntax}

El contenido de un archivo de ID incluye los siguientes elementos:

*`UUID`* `<tab>`*`UUID`*`<tab>`*`UUID`*`<tab>`*`UUID`*

El archivo contiene los ID de usuario ([!DNL UUID]). En cada fila, separe los ID con una pestaña. El siguiente ejemplo muestra un archivo de ID con el formato correcto. Su contenido podría ser similar.

```
abc123 def456 ghi789 xyz987
```

### Consideraciones sobre contenido de archivo {#considerations}

Al crear los archivos de entrada, asegúrese de que la primera columna solo se rellena con ID de dispositivo, como [!DNL AAM UUID], [!DNL GAID], [!DNL IDFA], etc. Consulte [Índice de ID en el Audience Manager](../../../reference/ids-in-aam.md) para obtener una explicación detallada de los ID admitidos por el Audience Manager.

>[!IMPORTANT]
>
>No use [DPUUID](../../../reference/ids-in-aam.md) en la primera columna. Al hacerlo, la sincronización puede ser incorrecta.

## La sincronización hace coincidir DPUUID con UUID {#sync-matches-dpuuids-uuids}

El propósito de un archivo de sincronización de ID es sincronizar el [DPUUID](../../../reference/ids-in-aam.md) desde sus propias fuentes de datos con [!DNL Audience Manager] UUID. La sincronización asigna el [!DNL DPUUID]s del patrón [!DNL DPID] y sus aspectos relacionados [!DNL DPID]s a la [!DNL Audience Manager] [!DNL UUID]s. La ubicación de los ID en el nombre de archivo y el cuerpo determinan cómo se asignan estos identificadores entre sí. Por ejemplo, tome los dos archivos de ejemplo que se muestran aquí:

* **Archivo 1:** `adobe_id_0_12345_1476312152.sync`

* **Archivo 2:**  `adobe_id_12345_67890_1476312876.sync`

<br/>

Dado el nombre y el contenido del ejemplo, los ID se asignan de esta manera:

**Archivo 1** ( [Descargar archivo de muestra](assets/adobe_id_0_12345_1476312152.sync))

| DPID 0 = UUID de Adobe Audience Manager | 12345 DPID |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38 |
| 67412682083411995725538770443620307584 | XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM |
| 66552757407517449462805881945288602094 | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M |
| 66184778222667870903738139438735041506 | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw |

Paso 1: el proceso de sincronización de ID sincronizará el [!DNL DPUUID]s de [!DNL DPID] 12345 con el [!DNL Audience Manager] [!DNL UUID]s en la columna izquierda. Tenga en cuenta que la variable [!DNL DPID] &quot;0&quot; en el nombre del archivo representa [!DNL Audience Manager] [!DNL UUID]s.
<br/>

**Archivo 2** ( [Descargar archivo de muestra](assets/adobe_id_12345_67890_1477846458.sync))

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38 | 4598060374 |
| XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 | 4581274262 |
| XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM | 4392434426 |
| XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M | 2351382994 |
| XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw | 4601584763 |

Paso 2: la [!DNL DPUUID]s de [!DNL DPID] Se 12345 sincronizado en el paso 1 con el Audience Manager [!DNL UUID]s. Lo que hará esta sincronización de ID es sincronizar el [!DNL DPUUID]s de [!DNL DPID] 67890 con el Audience Manager [!DNL UUID]s del paso 1.

<br/>

## Otros requisitos de formato {#other-format-reqs}

Los ID de usuario no pueden:

* Tiene pestañas en el propio ID. Las pestañas solo se utilizan para separar ID individuales en el archivo de datos.
* Contener información personal identificable ([!UICONTROL PII]).
* Uso [!DNL URL] codificación. Pasar solo ID sin codificar.

Las filas que terminen con tabulaciones o espacios no se procesarán ni realizarán. Como regla general, asegúrese de mantener el final de las filas despejado.
