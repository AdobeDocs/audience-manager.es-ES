---
description: Preguntas más frecuentes sobre la introducción de datos sin conexión en Audience Manager.
keywords: ftp o s3;s3 o ftp
seo-description: Preguntas más frecuentes sobre la introducción de datos sin conexión en Audience Manager.
seo-title: Preguntas más frecuentes sobre la ingestión de datos de clientes entrantes
solution: Audience Manager
title: Preguntas más frecuentes sobre la ingestión de datos de clientes entrantes
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
translation-type: tm+mt
source-git-commit: e081e31380d4600883f927b5ecef3b38be2a676e

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
* Transfiera archivos de datos de producción a [!DNL Audience Manager]. Dada la dependencia de las asignaciones de sincronización de ID, puede que sea recomendable empezar a transferir datos hasta una semana después de la implementación del código de producción, aunque puede empezar a transferir los archivos de datos en cuanto el código entre en producción.

<br> 

**¿Qué modo FTP debo utilizar para transferir archivos comprimidos o cifrados?**

Consulte Compresión [de archivos para archivos](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)de transferencia de datos de entrada.

<br> 

**¿Puedo cargar un archivo de datos de entrada (archivo[!DNL .sync]o[!DNL .overwrite]) antes de implementar[!DNL Audience Manager]el código en la producción?**

* Si el proveedor de datos está configurado para utilizar el vínculo [](../features/profile-merge-rules/merge-rules-overview.md) de perfil para la segmentación entre dispositivos, los datos disponibles para segmentación poco después de que se identifique una sincronización de ID con el ID de [!DNL Audience Manager] visitante coincidente.

* Si el proveedor de datos no está configurado para utilizar la [!UICONTROL Profile Link] función, [!DNL Audience Manager] procesa únicamente los datos de los ID de visitante en el archivo de datos de entrada que se hayan sincronizado o vuelto a coincidir con un ID de visitante [!DNL Audience Manager] .

Considere los siguientes casos de uso en los que el proveedor de datos no está configurado para usar [!UICONTROL Profile Merge]:

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
   <td colname="col2"> <p>El lunes, un visitante identificado en la base de datos de CRM como visitante ABC inicia sesión, lo que inicia una sincronización de ID del lado del cliente. <span class="keyword"> Audience Manager</span> almacena la asignación del visitante ABC al visitante <span class="keyword"> de Audience Manager</span> 123. </p> <p>El martes, la base de datos CRM transfiere un archivo de datos (<span class="filepath"> .sync</span>) al <span class="keyword"> </span>servidor de Audience Manager con el siguiente registro: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender"="male","luxury_shopper"="yes"</code> </li> 
     </ul> </p> <p>En este caso, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Reconoce el ABC del visitante a partir de la asignación de sincronización de ID almacenada. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Asocia las características <code> male</code> y <code> luxury_shopper</code> el perfil del visitante 123. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Caso 2</b> </p> </td> 
   <td colname="col2"> <p>El lunes, la base de datos CRM envía un archivo de datos (<span class="filepath"> .sync</span>) al servidor de <span class="keyword"> Audience Manager</span> con el siguiente registro: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> no tiene un registro de este visitante (o un ID de visitante asociado), por lo que no se procesa este registro. </p> <p>El martes, el DEF del visitante inicia sesión. Esta acción inicia la primera sincronización de ID del lado del cliente para ese visitante. Esta acción asigna la DEF del visitante al ID 456 de <span class="keyword"> Audience Manager</span> . Sin embargo, este visitante no tiene datos CRM asociados a su perfil. Como resultado, <span class="keyword"> Audience Manager</span> no vuelve a procesar los archivos antiguos. </p> <p>El miércoles, la base de datos CRM envía otro archivo de datos al servidor de <span class="keyword"> Audience Manager</span> con el siguiente registro: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes","dma"="paris"</code> </li> 
     </ul> </p> <p>En este caso, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Reconoce el DEF del visitante a partir de la asignación de sincronización de ID almacenada. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Asocia las características <code> female</code><code> paris</code>y <code> wine_enthusiast</code> el perfil del visitante 456. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Caso 3</b> </p> </td> 
   <td colname="col2"> <p>El lunes, el servidor de Audience Manager <span class="keyword"></span> recibe dos archivos con los siguientes registros: </p> <p> <code> .sync</code> archivo que contiene: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> .overwrite</code> archivo que contiene: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender"="male" "wine_enthusiast"="no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender"="female" "wine_enthusiast"="yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> contiene un registro asignado de JKL de visitante al ID 789, desde una sincronización de ID anterior. </p> <p>En este caso, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Reconoce la JKL del visitante a partir de la asignación de sincronización de ID almacenada. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Asocia las características <code> female</code> y <code> wine_enthusiast</code> al perfil del ID de visitante 789. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Omite la asociación de características para GHI de visitantes, ya que su ID solo se sincronizó en el lote actual. Para asociar características con GHI del visitante, debe incluirlas en <code> .overwrite</code> archivos futuros. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**¿A qué hora del día debo transferir mi archivo?**

[!DNL Audience Manager] comprueba y procesa archivos varias veces durante el día. Cargue los datos cuando esté listo.

<br> 

**¿Cuánto tarda en estar disponible para la segmentación los datos de un archivo cargado?**

Los datos están disponibles para el objetivo después de 48 horas. Además, no interprete el correo electrónico de "carga correcta" como una afirmación de que los datos están disponibles. Esto solo significa que [!DNL Audience Manager] ha recogido el archivo y completado el primer paso de procesamiento.

<br> 

**¿Con qué frecuencia debo enviar archivos y deben ser archivos completos o incrementales?**

Como práctica recomendada, envíe un archivo incremental una vez al día para los visitantes nuevos y para los visitantes cuyos datos hayan cambiado. Muchos [!DNL Audience Manager] clientes envían un archivo completo una vez al mes. Sin embargo, estos intervalos y incrementos de archivos son flexibles. Debe enviar datos en incrementos y a veces que tengan sentido para usted.

<br> 

**¿Cuánto tiempo mantiene Audience Manager mis archivos en el servidor?**

Los archivos FTP se eliminan una vez procesados. [!DNL S3] los archivos se eliminan pasados 30 días. Se eliminan los archivos que no se pueden procesar debido a errores de formato, sintaxis u otros errores. Consulte también Preguntas más frecuentes sobre [privacidad y retención de datos](../faq/faq-privacy.md).

<br> 

**¿Cuál es la diferencia entre archivos completos e incrementales?**

* **** Completa: Un archivo completo sobrescribe todos los perfiles de visitantes existentes y los reemplaza por los datos del archivo. Los archivos completos se identifican con la `.overwrite` etiqueta anexada al nombre del archivo. Puede utilizar un `.overwrite` archivo para restablecer las características del visitante o eliminar las características obsoletas y antiguas.

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

Las marcas de hora se utilizan para registrar y mantener registros. Son obligatorios según la sintaxis utilizada para un nombre de archivo entrante formateado correctamente. Consulte:

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

Depende. [!DNL Audience Manager] lee hasta 119000 entradas de la [!DNL Amazon SQS] cola y las divide en hasta 3 lotes. Los archivos se procesarán simultáneamente sólo si acaban en el mismo lote. Sin embargo, debido a la gran cantidad de datos que ingesta [!DNL Audience Manager] diariamente, no podemos garantizar ningún pedido de procesamiento de archivos.

>[!MORE_LIKE_THIS]
>
>* [Proceso de transferencia de datos por lotes descrito](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

