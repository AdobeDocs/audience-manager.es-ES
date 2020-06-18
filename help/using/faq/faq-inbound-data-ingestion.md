---
description: Preguntas más frecuentes sobre la introducción de datos sin conexión en Audience Manager.
keywords: ftp or s3;s3 or ftp
seo-description: Preguntas más frecuentes sobre la introducción de datos sin conexión en Audience Manager.
seo-title: Preguntas más frecuentes sobre la ingestión de datos de clientes entrantes
solution: Audience Manager
title: Preguntas más frecuentes sobre la ingestión de datos de clientes entrantes
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
translation-type: tm+mt
source-git-commit: ef098c35da49ae663d201b9b7f96034fb5c76323
workflow-type: tm+mt
source-wordcount: '1355'
ht-degree: 3%

---


# Preguntas más frecuentes sobre la ingestión de datos de clientes entrantes{#inbound-customer-data-ingestion-faq}

Preguntas más frecuentes sobre la introducción de datos sin conexión en Audience Manager.

 

**¿Puede resumir el proceso de integración?**

El proceso de integración consiste en dos pasos descritos en [Enviar datos por lotes a la información general](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)del Audience Manager:

* Paso 1: sincronizar ID de usuario;
* Paso 2: cree y transfiera su archivo de datos de entrada, cumpliendo los requisitos de formato de archivo.

 

**¿Puede resumir el proceso de implementación?**

Recomendamos lo siguiente:

* Póngase en contacto con su proveedor de datos para dar formato al archivo de datos de entrada diario según las especificaciones de Adobe. Consulte la siguiente documentación para conocer los requisitos de nomenclatura y sintaxis de archivos:
   * [Requisitos de nombre y contenido para archivos de sincronización de ID](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)
   * [Contenido del archivo de datos de entrada: Sintaxis, caracteres no válidos, variables y ejemplos](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)
   * [Requisitos de tamaño de archivo y nombre de Amazon S3 para archivos de datos de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* Póngase en contacto con su [!DNL Adobe] asesor para transferir un archivo de datos de prueba a [!DNL Adobe] para la verificación de formato.
* Póngase en contacto con su [!DNL Adobe] consultor para producir una taxonomía adecuada para interpretar el contenido del archivo de datos.
* En el entorno de ensayo/desarrollo, confirme que la sincronización de ID está configurada para recoger correctamente el ID de visitante del proveedor de datos y transferirlo a los [!DNL Audience Manager] servidores en tiempo real.
* Implementar la sincronización DIL/ID en producción. Su consultor de Adobe ya configurará la sincronización de ID como un módulo dentro del código DIL.
* Transfiera archivos de datos de producción a [!DNL Audience Manager]. Dadas las dependencias de las asignaciones de sincronización de ID, puede que sea recomendable empezar a transferir datos hasta una semana después de la implementación del código de producción, aunque puede realizar inicios en la transferencia de los archivos de datos en cuanto el código entre en producción.

 

**¿Qué modo FTP debo utilizar para transferir archivos comprimidos o cifrados?**

Consulte Compresión [de archivos para archivos](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)de transferencia de datos de entrada.

>[!WARNING]
>
>Estamos eliminando gradualmente la compatibilidad con las configuraciones de FTP. Aunque la ingestión de archivos de datos de entrada sigue siendo compatible con integraciones de FTP existentes, recomendamos encarecidamente utilizar Amazon S3 para incorporar datos sin conexión para nuevas integraciones. Consulte Requisitos de nombre y tamaño de archivo de [Amazon S3 para archivos](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) de datos de entrada para obtener más información.

 

**¿Puedo cargar un archivo de datos de entrada (archivo [!DNL .sync] o [!DNL .overwrite]) antes de implementar [!DNL Audience Manager] el código en la producción?**

Sí. Siempre que utilice un [!UICONTROL cross-device data source] para almacenar los datos de CRM que cargue, el Audience Manager siempre almacena los datos. De hecho, tras las [!UICONTROL Profile Merge Rules] mejoras que Audience Manager lanzó en octubre de 2019 que permiten casos de uso solo sin conexión, puede cargar datos y realizar acciones en ellos sin necesidad de implementar código de Audience Manager en la producción. Consulte:

* [Información general sobre las mejoras de las reglas de combinación de Perfiles](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* [!UICONTROL People-based Destinations] - [Personalización basada en datos solo sin conexión](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html)

<br> 

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

**¿A qué hora del día debo transferir mi archivo?**

[!DNL Audience Manager] comprueba y procesa archivos varias veces durante el día. Cargue los datos cuando esté listo.

 

**¿Cuánto tarda en estar disponible para la segmentación los datos de un archivo cargado?**

Los datos están disponibles para el objetivo después de 48 horas. Además, no interprete el correo electrónico de &quot;carga correcta&quot; como una afirmación de que los datos están disponibles. Esto solo significa que [!DNL Audience Manager] ha recogido el archivo y completado el primer paso de procesamiento.

 

**¿Con qué frecuencia debo enviar archivos y deben ser archivos completos o incrementales?**

Como práctica recomendada, envíe un archivo incremental una vez al día para nuevos visitantes y para visitantes cuyos datos hayan cambiado. Muchos [!DNL Audience Manager] clientes envían un archivo completo una vez al mes. Sin embargo, estos intervalos y incrementos de archivos son flexibles. Debe enviar datos en incrementos y a veces que tengan sentido para usted.

 

**¿Cuánto tiempo mantiene Audience Manager mis archivos en el servidor?**

Los archivos FTP se eliminan una vez procesados. [!DNL S3] los archivos se eliminan pasados 30 días. Se eliminan los archivos que no se pueden procesar debido a errores de formato, sintaxis u otros errores. Consulte también Preguntas más frecuentes sobre [privacidad y retención de datos](../faq/faq-privacy.md).

 

**¿Cuál es la diferencia entre archivos completos e incrementales?**

* **Completa:** Un archivo completo sobrescribe todos los perfiles de visitante existentes y los reemplaza por los datos del archivo. Los archivos completos se identifican con la `.overwrite` etiqueta anexada al nombre del archivo. Puede utilizar un `.overwrite` archivo para restablecer características de visitante o quitar características antiguas y obsoletas.

   >[!NOTE]
   >
   >Los [!DNL .overwrite] archivos solo sobrescriben los datos de [!DNL Audience Manager] perfil asociados a este proveedor de datos. En otras palabras, todos los [!DNL Audience Manager] datos asociados al visitante permanecen intactos después de procesar un [!DNL .overwrite] archivo.

* **Incremental:** Un archivo incremental anexa nuevos datos a los perfiles de visitante existentes. Los archivos incrementales se identifican mediante la `.sync` etiqueta anexada al nombre del archivo. Enviar un archivo incremental no borra ni sobrescribe los perfiles existentes.

Los siguientes casos de uso muestran cómo estos tipos de archivos afectan los perfiles de visitante almacenados.

| Caso de uso | Descripción |
|---|---|
| Incremental y completo | <ul><li>Contenido del `.sync` archivo del día 1: `visitor123 = a,b,c`</li><li>Contenido del `.overwrite` archivo del día 2: `visitor123 = c,d,e`</li><li>Contenido de la ID del perfil del visitante 123 del día 3: `c,d,e`</li></ul> |
| Sólo incremental | <ul><li>Contenido del `.sync` archivo del día 1: `visitor123 = a,b,c`</li><li>Contenido del `.sync` archivo del día 2: `visitor123 = c,d,e`</li><li>Contenido de la ID del perfil del visitante 123 del día 3: `a,b,c,d,e`</li></ul> |

Para obtener más información sobre los tipos de archivo completos e incrementales, consulte:

* [Requisitos de nombre y tamaño de archivo de Amazon S3 para datos de entrada...](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**¿Qué sucede si envío un archivo con ID para visitantes que nunca han realizado la sincronización de ID en la página?**

Durante el procesamiento, [!DNL Audience Manager] omite ese registro y pasa al siguiente. Si se configura un [DPID (ID del proveedor de datos)](../reference/ids-in-aam.md) como DPID entre dispositivos, los datos que se ingieren antes de guardar una sincronización de ID estarán disponibles para su uso poco después de que se produzca la sincronización de ID.

 

**¿Cuál es la marca de hora, para qué sirve y puede servir de ejemplo?**

Las marcas de hora se utilizan para el registro y el mantenimiento de registros. Son obligatorios según la sintaxis utilizada para un nombre de archivo entrante formateado correctamente. Consulte:

* [Requisitos de nombre de Amazon S3 para archivos de datos de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**¿Qué es un[!DNL Data Provider ID (DPID)]y cómo lo entiendo?**

El consultor de Adobe asignará un [DPID de tres o cuatro dígitos (ID del proveedor de datos)](../reference/ids-in-aam.md) a la fuente de datos concreta. Este ID es único y no cambia.

 

**¿Qué tamaño pueden tener los archivos de datos diarios?**

Consulte Compresión [de archivos para archivos](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)de transferencia de datos de entrada.

 

**¿El Audience Manager admite la compresión de archivos?**

Sí, consulte:

* [Compresión de archivos para archivos de transferencia de datos de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Requisitos de nombre de Amazon S3 para archivos de datos de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**La clave principal de mi base de datos de origen de datos es una dirección de correo electrónico. ¿Se considera que esa información es personal?**

Sí. [!DNL Audience Manager] no almacena direcciones de correo electrónico en su base de datos. A los Visitantes se les debe asignar un ID generado aleatoriamente o una versión con hash unidireccional de la dirección de correo electrónico antes de iniciar las sincronizaciones de ID.

 

**¿Distingue entre mayúsculas y minúsculas el contenido del archivo de datos? ¿Qué sucede con la sincronización de ID?**

Hay dos componentes básicos de un archivo de datos: Un [!UICONTROL User ID] (consulte [!UICONTROL User ID] en Variables [de archivo definidas](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)) y datos de perfil, normalmente en forma de pares o códigos de clave-valor. La [!UICONTROL User ID] distinción entre mayúsculas y minúsculas es importante. Generalmente, los datos de perfil o de valor clave no distinguen entre mayúsculas y minúsculas.

 

**¿Debo usar FTP o[!DNL Amazon S3]transferir archivos?**

Como práctica recomendada, recomendamos [!DNL Amazon S3] porque el proceso es más sencillo. [!DNL Audience Manager] transfiere archivos FTP a [!DNL S3] cualquier lugar, por lo que el proceso se optimiza si se colocan los archivos en [!DNL Amazon S3] sí mismo. Además, los clientes que cargan simultáneamente en FTP comparten el ancho de banda del FTP, por lo que deben esperar velocidades de carga más lentas. [!DNL Amazon S3] también se replica y distribuye, por lo que generalmente es más seguro y fiable que un servidor FTP. Para obtener más información, consulte [Acerca de Amazon S3](../reference/amazon-s3.md).

>[!WARNING]
>
>Estamos eliminando gradualmente la compatibilidad con las configuraciones de FTP. Aunque la ingestión de archivos de datos de entrada sigue siendo compatible con las integraciones de FTP existentes, recomendamos encarecidamente usar datos sin conexión integrados [!DNL Amazon S3] para nuevas integraciones. Consulte Requisitos de nombre y tamaño de archivo de [Amazon S3 para archivos](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) de datos de entrada para obtener más información.

 

**¿Cómo procesa Audiencia Manager los archivos de entrada?**

[!DNL Audience Manager] se utiliza [!DNL Amazon Simple Queue Service (SQS)] para el procesamiento de datos de entrada. Así funciona:

1. [!DNL Audience Manager] los clientes cargan sus datos de entrada en un [!DNL Amazon S3] bloque.
1. Los datos entran en la [!DNL Amazon SQS] cola, esperando ser procesados por [!DNL Audience Manager].
1. [!DNL Audience Manager] lee hasta 119000 entradas de la [!DNL Amazon SQS] cola y las divide en hasta 3 lotes. Los archivos de cada lote se procesan simultáneamente.

 

**Necesito cargar varios archivos al mismo tiempo. ¿Se procesarán los archivos simultáneamente?**

Depende. [!DNL Audience Manager] lee hasta 119000 entradas de la [!DNL Amazon SQS] cola y las divide en hasta 3 lotes. Los archivos se procesarán simultáneamente solo si terminan en el mismo lote. Sin embargo, debido a la gran cantidad de datos que ingesta [!DNL Audience Manager] diariamente, no podemos garantizar ningún pedido de procesamiento de archivos.

>[!MORELIKETHIS]
>
>* [Proceso de transferencia de datos por lotes descrito](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

