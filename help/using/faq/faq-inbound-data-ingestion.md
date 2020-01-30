---
description: Preguntas más frecuentes sobre la introducción de datos sin conexión en Audience Manager.
keywords: ftp or s3;s3 or ftp
seo-description: Preguntas más frecuentes sobre la introducción de datos sin conexión en Audience Manager.
seo-title: Preguntas más frecuentes sobre la ingestión de datos de clientes entrantes
solution: Audience Manager
title: Preguntas más frecuentes sobre la ingestión de datos de clientes entrantes
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
translation-type: tm+mt
source-git-commit: 22336b052af1c438136e4a6cfd6ad88393503f16

---


# Preguntas más frecuentes sobre la ingestión de datos de clientes entrantes{#inbound-customer-data-ingestion-faq}

Preguntas más frecuentes sobre la introducción de datos sin conexión en Audience Manager.

<br> 

<!-- 

c_inbound_crm_data_ingestion.xml

 -->

**¿Puede resumir el proceso de integración?**

El proceso de incorporación consiste en dos componentes principales descritos en el proceso de transferencia de datos por [lotes descrito](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md). Éstos incluyen:

* Sincronización de ID
* Archivo de datos de entrada ( [!DNL .sync] archivo o [!DNL .overwrite] archivo)

<!-- 

Removed the Data Translation File bullet from the list above.

 -->

A continuación encontrará una lista de preguntas y respuestas que puede resultar de utilidad tras revisar la documentación.

>[!NOTE]
>
>Los ejemplos de esta sección se simplifican o abrevian con fines de abreviación y demostración. Consulte la documentación de introducción de datos para obtener especificaciones detalladas sobre los formatos de archivo y la sintaxis.

<br> 

**¿Puede resumir el proceso de implementación?**

Recomendamos lo siguiente:

* Trabaje con su proveedor de datos para dar formato al archivo de datos de entrada diario según [!DNL Adobe] las especificaciones.
* Transfiera un archivo de datos de prueba a para [!DNL Adobe] la verificación de formato.
* Póngase en contacto con su [!DNL Adobe] consultor para producir una taxonomía adecuada para interpretar el contenido del archivo de datos.
* En el entorno de ensayo/desarrollo, confirme que la sincronización de ID está configurada para recoger correctamente la ID de visitante del proveedor de datos y transferirla a los [!DNL Audience Manager] servidores en tiempo real.
* Implementar la sincronización DIL/ID en producción. Su consultor de Adobe ya configurará la sincronización de ID como un módulo dentro del código DIL.
* Transfiera archivos de datos de producción a [!DNL Audience Manager]. Dadas las dependencias de las asignaciones de sincronización de ID, puede que sea recomendable empezar a transferir datos hasta una semana después de la implementación del código de producción, aunque puede empezar a transferir los archivos de datos en cuanto el código entre en producción.

<br> 

**¿Qué modo FTP debo utilizar para transferir archivos comprimidos o cifrados?**

Consulte Compresión [de archivos para archivos](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)de transferencia de datos de entrada.

<br> 

**¿Puedo cargar un archivo de datos de entrada (archivo [!DNL .sync] o [!DNL .overwrite]) antes de implementar [!DNL Audience Manager] el código en la producción?**

Sí. Siempre que utilice un origen de datos entre dispositivos para almacenar los datos CRM que cargue, Audience Manager siempre almacena los datos. De hecho, tras las mejoras de las reglas de combinación de perfiles que Audience Manager inició en octubre de 2019 y que permiten casos de uso solo sin conexión, puede cargar datos y realizar acciones en ellos sin implementar el código de Audience Manager en la producción. Consulte:

* [Introducción a las mejoras de las reglas de combinación de perfiles](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* Destinos basados en personas: [personalización basada en datos solo sin conexión](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html)

<!---
* If the data provider is configured to use [Profile Link](../features/profile-merge-rules/merge-rules-overview.md) for cross-device targeting, the data available for targeting shortly after an ID sync identifies to the matching [!DNL Audience Manager] visitor ID.

* If the data provider is not configured to use the [!UICONTROL Profile Link] feature, [!DNL Audience Manager] processes only the data for visitor IDs in the inbound data file that have been previously synced/matched back to an [!DNL Audience Manager] visitor ID.

Consider the following use cases in which the data provider is not configured to use [!UICONTROL Profile Merge]:

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Case 1</b> </p> </td> 
   <td colname="col2"> <p>On Monday, a visitor identified in the CRM database as visitor ABC logs in, which initiates a client-side ID sync. <span class="keyword"> Audience Manager</span> stores the mapping of visitor ABC to <span class="keyword"> Audience Manager</span> visitor 123. </p> <p>On Tuesday, the CRM database transfers a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager </span>server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender"="male","luxury_shopper"="yes"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Recognizes visitor ABC from the stored ID sync mapping. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associates the traits <code> male</code> and <code> luxury_shopper</code> with the visitor 123 profile. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 2</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the CRM database pushes a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> does not have a record of this visitor (or an associated visitor ID) so this record is not processed. </p> <p>On Tuesday, visitor DEF logs in. This action initiates the first client-side ID sync for that visitor. This action maps visitor DEF to <span class="keyword"> Audience Manager</span> ID 456. However, this visitor does not have CRM data associated with their profile. As a result, <span class="keyword"> Audience Manager</span> does not go back and reprocess old files. </p> <p>On Wednesday, the CRM database pushes another data file to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes","dma"="paris"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Recognizes visitor DEF from the stored ID sync mapping. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associates the traits <code> female</code>, <code> paris</code>, and <code> wine_enthusiast</code> with the visitor 456 profile. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 3</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the <span class="keyword"> Audience Manager</span> server receives two files with the following records: </p> <p> <code> .sync</code> file containing: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> .overwrite</code> file containing: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender"="male" "wine_enthusiast"="no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender"="female" "wine_enthusiast"="yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> holds a mapped record of visitor JKL to ID 789, from a previous ID sync. </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Recognizes visitor JKL from the stored ID sync mapping. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associates the traits <code> female</code> and <code> wine_enthusiast</code> with visitor ID 789's profile. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Ignores the trait association for visitor GHI, since its ID was only synced in the current batch. To associate traits with visitor GHI, you need to include them in future <code> .overwrite</code> files. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

-->

<br> 

**¿A qué hora del día debo transferir mi archivo?**

[!DNL Audience Manager] comprueba y procesa archivos varias veces durante el día. Cargue los datos cuando esté listo.

<br> 

**¿Cuánto tarda en estar disponible para la segmentación los datos de un archivo cargado?**

Los datos están disponibles para el objetivo después de 48 horas. Además, no interprete el correo electrónico de &quot;carga correcta&quot; como una afirmación de que los datos están disponibles. Esto solo significa que [!DNL Audience Manager] ha recogido el archivo y completado el primer paso de procesamiento.

<br> 

**¿Con qué frecuencia debo enviar archivos y deben ser archivos completos o incrementales?**

Como práctica recomendada, envíe un archivo incremental una vez al día para los visitantes nuevos y para los visitantes cuyos datos hayan cambiado. Muchos [!DNL Audience Manager] clientes envían un archivo completo una vez al mes. Sin embargo, estos intervalos y incrementos de archivos son flexibles. Debe enviar datos en incrementos y a veces que tengan sentido para usted.

<br> 

**¿Cuánto tiempo mantiene Audience Manager mis archivos en el servidor?**

Los archivos FTP se eliminan una vez procesados. [!DNL S3] los archivos se eliminan pasados 30 días. Se eliminan los archivos que no se pueden procesar debido a errores de formato, sintaxis u otros errores. Consulte también Preguntas más frecuentes sobre [privacidad y retención de datos](../faq/faq-privacy.md).

<br> 

**¿Cuál es la diferencia entre archivos completos e incrementales?**

* **** Completa: Un archivo completo sobrescribe todos los perfiles de visitante existentes y los reemplaza por los datos del archivo. Los archivos completos se identifican con la `.overwrite` etiqueta anexada al nombre del archivo. Puede utilizar un `.overwrite` archivo para restablecer las características del visitante o eliminar las características obsoletas y antiguas.

   >[!NOTE]
   >
   >Los [!DNL .overwrite] archivos solo sobrescriben los datos [!DNL Audience Manager] de perfil asociados a este proveedor de datos. En otras palabras, todos los datos [!DNL Adobe Analytics] asociados al visitante permanecen intactos después de procesar un [!DNL .overwrite] archivo.

* **** Incremental: Un archivo incremental anexa nuevos datos a los perfiles de visitante existentes. Los archivos incrementales se identifican mediante la `.sync` etiqueta anexada al nombre del archivo. Enviar un archivo incremental no borra ni sobrescribe los perfiles existentes.

Los siguientes casos de uso muestran cómo estos tipos de archivos afectan los perfiles de visitantes almacenados.

<table id="table_CE43B49508384ABF8B25FA8A8FFE5362"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Incremental y completo</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_E89301D815174D45B9B238F2CDE6CCC6"> 
      <li id="li_FA841FEEC0534AD59D1AB61DD5B9DEC4">Contenido del <code> .sync</code> archivo del día 1: <code> visitor123 = a,b,c</code> </li> 
      <li id="li_0E1A57B04D26481C8C41EBA63ACBEFE0">Contenido del <code> .overwrite</code> archivo del día 2: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_497A5604AD9A49A2ADE548C7CE158F0E"> El ID de perfil del visitante del día 3 123 contiene <code> c,d,e </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Sólo incremental</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8271C9796BD040E4B8DC64DCE4FE2AD3"> 
      <li id="li_347959BDE83549F794E6661C95097891">Contenido del <code> .sync</code> archivo del día 1: <code> visitor123 = a,b,c </code> </li> 
      <li id="li_B25D96526DE94171A3A5DC8DB7A19415">Contenido del <code> .sync</code> archivo del día 2: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_6E17809D49C74F4991B0B445469055E6">El ID de perfil del visitante del día 3 123 contiene <code> a,b,c,d,e</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Para obtener más información sobre los tipos de archivo completos e incrementales, consulte:

* [Requisitos de nombre y tamaño de archivo de Amazon S3 para datos de entrada...](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

<br> 

**¿Qué sucede si envío un archivo con ID para visitantes que nunca han realizado la sincronización de ID en la página?**

Durante el procesamiento, [!DNL Audience Manager] simplemente omite ese registro y pasa al siguiente. Si un DPID (ID del proveedor de datos) está configurado como DPID entre dispositivos, los datos que se ingieren antes de guardar una sincronización de ID estarán disponibles para su uso poco después de que se produzca la sincronización de ID.

<br> 

**¿Cuál es la marca de hora, para qué sirve y puede servir de ejemplo?**

Las marcas de hora se utilizan para el registro y el mantenimiento de registros. Son obligatorios según la sintaxis utilizada para un nombre de archivo entrante formateado correctamente. Consulte:

* [Requisitos de nombre de Amazon S3 para archivos de datos de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**¿Qué es una ID de proveedor de datos (DPID) y cómo puedo obtenerla?**

El consultor de Adobe asignará un DPID de tres o cuatro dígitos a la fuente de datos concreta. Este ID es único y no cambia.

<br> 

**¿Qué tamaño pueden tener los archivos de datos diarios?**

Consulte Compresión [de archivos para archivos](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)de transferencia de datos de entrada.

<br> 

**¿Audience Manager admite la compresión de archivos?**

Sí, consulte:

* [Compresión de archivos para archivos de transferencia de datos de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Requisitos de nombre de Amazon S3 para archivos de datos de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**La clave principal de mi base de datos de origen de datos es una dirección de correo electrónico. ¿Se considera que esa información es personal?**

Sí. [!DNL Audience Manager] no almacena direcciones de correo electrónico en nuestra base de datos. Se debe asignar a los visitantes un ID aleatorio o una versión con hash unidireccional de la dirección de correo electrónico antes de iniciar la sincronización de ID.

<br> 

**¿Distingue entre mayúsculas y minúsculas el contenido del archivo de datos? ¿Qué sucede con la sincronización de ID?**

Hay dos componentes básicos de un archivo de datos: Un ID de usuario (consulte ID de usuario en Variables de [archivo definidas](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)) y datos de perfil, normalmente en forma de pares o códigos de valor clave. El ID de usuario distingue entre mayúsculas y minúsculas. Generalmente, los datos de perfil o de valor clave no distinguen entre mayúsculas y minúsculas.

<br> 

**¿Debo usar FTP o[!DNL Amazon S3]transferir archivos?**

Como práctica recomendada, recomendamos [!DNL Amazon S3] porque el proceso es más sencillo. [!DNL Audience Manager] transfiere archivos FTP a [!DNL S3] cualquier lugar, por lo que el proceso se optimiza si se colocan los archivos en [!DNL Amazon S3] sí mismo. Además, los clientes que cargan simultáneamente en FTP comparten el ancho de banda del FTP, por lo que deben esperar velocidades de carga más lentas. [!DNL Amazon S3] también se replica y distribuye, por lo que generalmente es más seguro y fiable que un servidor FTP. Para obtener más información, consulte [Acerca de Amazon S3](../reference/amazon-s3.md).

<br> 

**¿Cómo procesa Audience Manager los archivos de entrada?**

[!DNL Audience Manager] se utiliza [!DNL Amazon Simple Queue Service (SQS)] para el procesamiento de datos de entrada. Así funciona:

1. [!DNL Audience Manager] los clientes cargan sus datos de entrada en un [!DNL Amazon S3] bloque.

2. Los datos entran en la [!DNL Amazon SQS] cola, esperando ser procesados por [!DNL Audience Manager].

3. [!DNL Audience Manager] lee hasta 119000 entradas de la [!DNL Amazon SQS] cola y las divide en hasta 3 lotes. Los archivos de cada lote se procesan simultáneamente.

<br> 

**Necesito cargar varios archivos al mismo tiempo. ¿Se procesarán los archivos simultáneamente?**

Depende. [!DNL Audience Manager] lee hasta 119000 entradas de la [!DNL Amazon SQS] cola y las divide en hasta 3 lotes. Los archivos se procesarán simultáneamente solo si terminan en el mismo lote. Sin embargo, debido a la gran cantidad de datos que ingesta [!DNL Audience Manager] diariamente, no podemos garantizar ningún pedido de procesamiento de archivos.

>[!MORELIKETHIS]
>
>* [Proceso de transferencia de datos por lotes descrito](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

