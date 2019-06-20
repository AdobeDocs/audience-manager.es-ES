---
description: Preguntas más frecuentes sobre cómo traer datos sin conexión a Audience Manager.
keywords: ftp o s 3; s 3 o ftp
seo-description: Preguntas más frecuentes sobre cómo traer datos sin conexión a Audience Manager.
seo-title: Preguntas frecuentes sobre la ingesta de datos de clientes de entrada
solution: Audience Manager
title: Preguntas frecuentes sobre la ingesta de datos de clientes de entrada
uuid: 491 e 9 ec 1-4731-46 a 8-86 e 7-d 8 c 613 e 6 cedc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Inbound Customer Data Ingestion FAQ{#inbound-customer-data-ingestion-faq}

Preguntas más frecuentes sobre cómo traer datos sin conexión a Audience Manager.

<br> 

<!-- 

c_inbound_crm_data_ingestion.xml

 -->

**¿Puede resumir el proceso de integración?**

The onboarding process consists of 2 core components described in [Batch Data Transfer Process Described](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process). Esto implica:

* Sincronización de ID
* Inbound Data File ( [!DNL .sync] file or [!DNL .overwrite] file)

<!-- 

Removed the Data Translation File bullet from the list above.

 -->

A continuación encontrará una lista de preguntas y respuestas que puede encontrar útiles después de revisar la documentación.

>[!NOTE]
>
>Los ejemplos de esta sección se simplifican o abrevian para fines de brevedad y demostración. Consulte la documentación de Inserción de datos de entrada para conocer especificaciones detalladas sobre los formatos de archivo y la sintaxis.

<br> 

**¿Puede resumir el proceso de implementación?**

Se recomienda lo siguiente:

* Work with your data provider to format the daily inbound data file according to [!DNL Adobe] specifications.
* Transfer a test data file to [!DNL Adobe] for format verification.
* Work with your [!DNL Adobe] consultant to produce a taxonomy suitable for interpreting the contents of the data file.
* In the staging/development environment, confirm that the ID sync is configured to properly pick up the data provider&#39;s visitor ID and transfer it to the [!DNL Audience Manager] servers in realtime.
* Implemente la sincronización DIL/ID en la producción. La sincronización de ID ya estará configurada como módulo dentro del código DIL por su consultor de Adobe.
* Transfer production data files to [!DNL Audience Manager]. Dadas las dependencias de las asignaciones de sincronización de ID, puede que sea recomendable empezar a transferir datos hasta una semana después de la implementación del código de producción, aunque puede empezar a transferir los archivos de datos en cuanto el código avance en la producción.

<br> 

**¿Qué modo de FTP debo utilizar para transferir archivos comprimidos o cifrados?**

See [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**¿Puedo cargar un archivo de datos de entrada (archivo[!DNL .sync]o[!DNL .overwrite]) antes de implementar[!DNL Audience Manager]el código en la producción?**

* If the data provider is configured to use [Profile Link](../features/profile-merge-rules/merge-rules-overview.md) for cross-device targeting, the data available for targeting shortly after an ID sync identifies to the matching [!DNL Audience Manager] visitor ID.

* If the data provider is not configured to use the [!UICONTROL Profile Link] feature, [!DNL Audience Manager] processes only the data for visitor IDs in the inbound data file that have been previously synced/matched back to an [!DNL Audience Manager] visitor ID.

Consider the following use cases in which the data provider is not configured to use [!UICONTROL Profile Merge]:

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Caso 1</b> </p> </td> 
   <td colname="col2"> <p>El día lunes, un visitante identificado en la base de datos CRM como visitante ABC inicia sesión, lo que inicia una sincronización de ID del lado del cliente. <span class="keyword"> Audience Manager</span> almacena la asignación del visitante ABC al <span class="keyword"> visitante de Audience Manager</span> 123. </p> <p>On Tuesday, the CRM database transfers a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager </span>server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender" = "male", "luxury_ shopper" = "yes"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Reconoce al visitante ABC desde la asignación de sincronización de ID almacenada. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associates the traits <code> male</code> and <code> luxury_shopper</code> with the visitor 123 profile. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Caso 2</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the CRM database pushes a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender" = "female", "wine_ enthusiast" = "yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> no tiene un registro de este visitante (o un ID de visitante asociado) para que este registro no se procese. </p> <p>El martes, DEF inicia sesión. Esta acción inicia la primera sincronización de ID del lado del cliente para ese visitante. This action maps visitor DEF to <span class="keyword"> Audience Manager</span> ID 456. Sin embargo, este visitante no tiene datos CRM asociados con su perfil. As a result, <span class="keyword"> Audience Manager</span> does not go back and reprocess old files. </p> <p>On Wednesday, the CRM database pushes another data file to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender" = "female", "wine_ enthusiast" = "yes", "dma" = "parís"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Reconoce DEF de visitante de la asignación de sincronización de ID almacenada. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associates the traits <code> female</code>, <code> paris</code>, and <code> wine_enthusiast</code> with the visitor 456 profile. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Caso 3</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the <span class="keyword"> Audience Manager</span> server receives two files with the following records: </p> <p> <code> . sync</code> que contiene: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> . overwrite</code> , que contiene: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender" = "male" "wine_ enthusiast" = "no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender" = "female" "wine_ enthusiast" = "yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> contiene un registro asignado del visitante JKL al ID 789, desde una sincronización de ID anterior. </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Reconoce JKL de visitante a partir de la asignación de sincronización de ID almacenada. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associates the traits <code> female</code> and <code> wine_enthusiast</code> with visitor ID 789's profile. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Omite la asociación de rasgos para el GHI del visitante, ya que su ID se sincronizó únicamente en el lote actual. To associate traits with visitor GHI, you need to include them in future <code> .overwrite</code> files. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**¿Qué hora del día debo transferir mi archivo?**

[!DNL Audience Manager] comprueba y procesa los archivos varias veces a lo largo del día. Cargue los datos cada vez que esté listo.

<br> 

**¿Cuánto tiempo toma antes de que los datos de un archivo cargado estén disponibles para el objetivo?**

Los datos están disponibles para segmentación después de 48 horas. Además, no debe interpretar el mensaje de correo electrónico «cargado correctamente» como una afirmación de que los datos están disponibles. This only means that [!DNL Audience Manager] has picked up the file and completed the first step of processing.

<br> 

**¿Con qué frecuencia debo enviar archivos y debo ser archivos completos o incremental?**

Una práctica recomendada es enviar un archivo incremental una vez por día para nuevos visitantes y para visitantes cuyos datos han cambiado. Many [!DNL Audience Manager] customers send a full file once per month. Sin embargo, estos intervalos de archivo e incrementos son flexibles. Debe enviar datos en incrementos y en otras que tengan sentido.

<br> 

**¿Cuánto tiempo conserva Audience Manager mis archivos en el servidor?**

Los archivos FTP se eliminan una vez procesados. [!DNL S3] los archivos se eliminan al cabo de 30 días. Los archivos que no se pueden procesar debido a un formato, sintaxis u otros errores se eliminan. See also, [Privacy and Data Retention FAQ](../faq/faq-privacy.md).

<br> 

**¿Cuál es la diferencia entre archivos completos e incrementales?**

* **Completa:** Un archivo completo sobrescribe todos los perfiles de visitante existentes y los sustituye por los datos del archivo. Full files are identified by the `.overwrite` tag appended to the file name. You can use a `.overwrite` file to reset visitor traits or remove stale, obsolete traits.

   >[!NOTE]
   >
   >[!DNL .overwrite] Los archivos sólo sobrescriben [!DNL Audience Manager] los datos de perfil asociados a este proveedor de datos. In other words, all [!DNL Adobe Analytics] data associated to the visitor remains intact after a [!DNL .overwrite] file has been processed.

* **Aumento:** Un archivo incremental anexa nuevos datos a los perfiles de visitante existentes. Incremental files are identified by the `.sync` tag appended to the file name. El envío de un archivo incremental no borra ni sobrescribe los perfiles existentes.

Los siguientes casos de uso muestran cómo estos tipos de archivos afectan los perfiles almacenados del visitante.

<table id="table_CE43B49508384ABF8B25FA8A8FFE5362"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Incremental y Completo</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_E89301D815174D45B9B238F2CDE6CCC6"> 
      <li id="li_FA841FEEC0534AD59D1AB61DD5B9DEC4">Day 1 <code> .sync</code> file contents: <code> visitor123 = a,b,c</code> </li> 
      <li id="li_0E1A57B04D26481C8C41EBA63ACBEFE0">Day 2 <code> .overwrite</code> file contents: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_497A5604AD9A49A2ADE548C7CE158F0E"> Day 3 visitor profile ID 123 contains <code> c,d,e </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Sólo incremental</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8271C9796BD040E4B8DC64DCE4FE2AD3"> 
      <li id="li_347959BDE83549F794E6661C95097891">Day 1 <code> .sync</code> file contents: <code> visitor123 = a,b,c </code> </li> 
      <li id="li_B25D96526DE94171A3A5DC8DB7A19415">Day 2 <code> .sync</code> file contents: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_6E17809D49C74F4991B0B445469055E6">Day 3 visitor profile ID 123 contains <code> a,b,c,d,e</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Para obtener más información sobre los tipos de archivos completos e incrementales, consulte:

* [Requisitos de tamaño de archivo y nombre de Amazon S 3 para datos de entrada…](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Requisitos de nombre de archivo y nombre de FTP para archivos de datos de entrada…](../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

<br> 

**¿Qué sucede si se envía un archivo con ID para visitantes que nunca han realizado la sincronización de ID en la página?**

During processing, [!DNL Audience Manager] simply skips that record and moves on to the next. Si un DPID (ID del proveedor de datos) está configurado como DPID entre dispositivos, los datos que se ingestan antes de la sincronización de ID se guardarán y se podrán utilizar poco después de la sincronización de ID.

<br> 

**¿Cuál es la marca de hora, la cual está para y puede proporcionar un ejemplo?**

Las marcas de hora se utilizan para registrar y registrar. Son requeridos por la sintaxis utilizada para un nombre de archivo de entrada con formato correcto. Consulte:

* [Requisitos de nombre de Amazon S3 para archivos de datos de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Requisitos de nombre de archivo y nombre de FTP para archivos de datos de entrada…](../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

<br> 

**¿Qué es un ID de proveedor de datos (DPID) y cómo puedo obtenerlo?**

Su consultor de Adobe asignará un DPID de tres o cuatro dígitos a su fuente de datos concreta. Este ID es único y no cambia.

<br> 

**¿Cuán grande puede ser los archivos de datos diarios?**

See [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**¿Es compatible Audience Manager con la compresión de archivos?**

Sí, consulte:

* [Compresión de archivos para archivos de transferencia de datos entrantes](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Requisitos de nombre de Amazon S3 para archivos de datos de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Requisitos de nombre de FTP para archivos de datos de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

<br> 

**La clave principal de mi base de datos de fuente de datos es una dirección de correo electrónico. Is that considered personally identifiable information?**

Sí. [!DNL Audience Manager] no almacena direcciones de correo electrónico en nuestra base de datos. Se debe asignar a los visitantes un ID aleatorio o una versión con un solo hash de la dirección de correo electrónico antes de iniciar sincronizaciones de ID.

<br> 

**¿Distingue entre mayúsculas y minúsculas los contenidos del archivo de datos? How about the ID sync?**

Existen dos componentes básicos de un archivo de datos: ID de usuario único (UUID) y datos de perfil, normalmente en forma de pares o códigos de valor clave. El UUID distingue entre mayúsculas y minúsculas. Generalmente, los datos de perfil o clave no distinguen entre mayúsculas y minúsculas.

<br> 

**¿Debería utilizar FTP o[!DNL Amazon S3]transferir archivos?**

As best practice, we recommend [!DNL Amazon S3] because the process is simpler. [!DNL Audience Manager] transfiere los archivos FTP [!DNL S3] a cualquier persona, por lo que el proceso se racionaliza si se colocan los archivos [!DNL Amazon S3] automáticamente. Además, los clientes que se cargan simultáneamente a FTP comparten el ancho de banda de FTP, por lo que deberían esperar velocidades de carga más lentas. [!DNL Amazon S3] también se replica y distribuye, por lo que generalmente es más seguro y fiable que un servidor FTP. For more information, see [About Amazon S3](../reference/amazon-s3.md).

<br> 

**¿Cómo procesa Audience Manager archivos de entrada?**

[!DNL Audience Manager] utiliza [!DNL Amazon Simple Queue Service (SQS)] para el procesamiento de datos entrantes. Esto es así como funciona:

1. [!DNL Audience Manager] los clientes cargan sus datos entrantes en un [!DNL Amazon S3] bloque.

2. The data enters the [!DNL Amazon SQS] queue, waiting to be processed by [!DNL Audience Manager].

3. [!DNL Audience Manager] lee hasta 119000 entradas de la [!DNL Amazon SQS] cola y las divide en hasta 3 lotes. Los archivos de cada lote se procesan simultáneamente.

<br> 

**Necesito cargar varios archivos al mismo tiempo. Will the files be processed simultaneously?**

Depende. [!DNL Audience Manager] lee hasta 119000 entradas de la [!DNL Amazon SQS] cola y las divide en hasta 3 lotes. Los archivos se procesarán de forma simultánea solo si terminan en el mismo lote. However, due to the high amount of data ingested by [!DNL Audience Manager] on a daily basis, we cannot guarantee any file processing order.

>[!MORE_ LIKE_ THIS]
>
>* [Proceso de transferencia de datos por lotes descrito](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process)

