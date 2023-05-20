---
description: Preguntas frecuentes sobre la introducción de datos sin conexión en Audience Manager.
keywords: ftp o s3;s3 o ftp
seo-description: Frequently asked questions about bringing offline data into Audience Manager.
seo-title: Inbound Customer Data Ingestion FAQ
solution: Audience Manager
title: Preguntas frecuentes sobre la incorporación de datos de clientes entrantes
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
feature: Onboarding Offline Data
exl-id: 48eef5f1-0655-4dac-9ab4-74b11c705c13
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1342'
ht-degree: 89%

---

# Preguntas frecuentes sobre la incorporación de datos de clientes entrantes{#inbound-customer-data-ingestion-faq}

Preguntas frecuentes sobre la introducción de datos sin conexión en Audience Manager.

 

**Brevemente, ¿cómo es el proceso de incorporación?**

El proceso de incorporación consta de dos pasos, descritos en [Información general sobre enviar datos por lotes a Audience Manager](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md):

* Paso 1: sincronización de los ID de usuario
* Paso 2: creación y transferencia de su archivo de datos de entrada, cumpliendo los requisitos de formato de archivo

 

**Brevemente, ¿cómo es el proceso de implementación?**

Estas son nuestras recomendaciones:

* Póngase en contacto con su proveedor de datos para dar formato al archivo diario de datos entrantes, siguiendo las especificaciones de Adobe. Consulte la siguiente documentación para conocer los requisitos de nomenclatura y sintaxis de archivos:
   * [Requisitos de nomenclatura y contenido para archivos de sincronización de ID](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)
   * [Contenido del archivo de datos de entrada: sintaxis, caracteres no válidos, variables y ejemplos](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)
   * [Requisitos de tamaño de archivo y nomenclatura de Amazon S3 para archivos de datos entrantes](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* Póngase en contacto con su consultor de [!DNL Adobe] para transferir un archivo de datos de prueba a [!DNL Adobe] para verificar el formato.
* Póngase en contacto con su consultor de [!DNL Adobe] para crear una taxonomía adecuada para interpretar el contenido del archivo de datos.
* En el entorno de ensayo y desarrollo, confirme que la sincronización de ID está configurada para capturar el ID de visitante del proveedor de datos y transferirlo a los servidores de [!DNL Audience Manager] en tiempo real.
* Implemente la sincronización DIL/ID en producción. Su consultor de Adobe habrá configurado la sincronización de ID como un módulo dentro del código DIL.
* Transfiera los archivos de datos de producción a [!DNL Audience Manager]. Dadas las dependencias de las asignaciones de sincronización de ID, puede ser conveniente empezar a transferir datos hasta una semana después de la implementación del código de producción, si bien puede iniciar la transferencia de los archivos de datos en cuanto el código entre en producción.

 

**¿Qué modo FTP debo utilizar para transferir archivos comprimidos o cifrados?**

Consulte [Compresión de archivos de transferencia de datos entrantes](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

>[!WARNING]
>
>Estamos eliminando gradualmente el apoyo a las configuraciones de FTP. Aunque la incorporación de archivos de datos entrantes sigue siendo compatible con integraciones de FTP actuales, recomendamos encarecidamente utilizar Amazon S3 para incorporar datos sin conexión en el caso de nuevas integraciones. Consulte [Requisitos de nomenclatura y tamaño de archivo de Amazon S3 para archivos de datos entrantes](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) para obtener más información.

 

**¿Puedo cargar un archivo de datos de entrada (archivo [!DNL .sync] o [!DNL .overwrite]) antes de implementar el código de [!DNL Audience Manager] en la producción?**

Sí. Siempre y cuando utilice un [!UICONTROL cross-device data source] para almacenar los datos CRM que carga, Audience Manager siempre almacena los datos. De hecho, tras la [!UICONTROL Profile Merge Rules] Mejoras que Audience Manager lanzó en octubre de 2019 y que permiten casos de uso únicamente sin conexión. Puede cargar datos y actuar en ellos sin implementar el código de Audience Manager en la producción. Consulte:

* [Información general sobre las mejoras de las reglas de combinación de perfiles](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* [!UICONTROL People-based Destinations] - [Personalización basada en datos solo sin conexión](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html)

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

**¿A qué hora del día debería transferir el archivo?**

[!DNL Audience Manager] comprueba y procesa archivos varias veces a lo largo del día. Cargue los datos cuando esté listo.

 

**¿Cuánto tardan los datos de un archivo cargado en estar disponibles para la segmentación?**

Los datos están disponibles para la segmentación tras 48 horas. Además, no interprete el correo electrónico de “carga correcta” como una confirmación de que los datos están disponibles. Este mensaje solo significa que [!DNL Audience Manager] ha recogido el archivo y completado el primer paso de procesamiento.

 

**¿Con qué frecuencia debo enviar archivos? ¿Deben ser archivos completos o incrementales?**

Se recomienda el envío de un archivo incremental una vez al día en el caso de nuevos visitantes y de visitantes cuyos datos hayan cambiado. Muchos clientes de [!DNL Audience Manager] envían un archivo completo una vez al mes. Sin embargo, estos periodos e incrementos son flexibles. Los incrementos de archivos y el momento de enviarlos deberían ser los adecuados para usted.

 

**¿Cuánto tiempo mantiene Audience Manager mis archivos en el servidor?**

Los archivos FTP se eliminan una vez procesados. Los archivos de [!DNL S3] se eliminan a los 30 días. Se eliminan los archivos que no se pueden procesar debido a errores de formato, sintaxis, u otros. Consulte también las preguntas frecuentes sobre [privacidad y retención de datos](../faq/faq-privacy.md).

 

**¿Cuál es la diferencia entre archivos completos e incrementales?**

* **Completos:** un archivo completo sobrescribe todos los perfiles de visitante y los reemplaza por los datos del archivo. Los archivos completos se identifican con la etiqueta `.overwrite` anexada al nombre del archivo. Puede utilizar un archivo `.overwrite` para restablecer rasgos de visitante o eliminar rasgos antiguos y obsoletos.

   >[!NOTE]
   >
   >Los archivos [!DNL .overwrite] solo sobrescriben los datos de perfil de [!DNL Audience Manager] asociados a este proveedor de datos. Es decir, todos los datos de [!DNL Audience Manager] asociados al visitante quedan intactos después de que se procese un archivo [!DNL .overwrite].

* **Incremental:** un archivo incremental anexa nuevos datos a los perfiles de visitante. Los archivos incrementales se identifican mediante la etiqueta `.sync` adjunta al nombre del archivo. Al enviar un archivo incremental no se borran ni sobrescriben los perfiles existentes.

Los siguientes casos de uso muestran cómo se comportan estos tipos de archivos con los perfiles de visitante almacenados.

| Caso de uso | Descripción |
|---|---|
| Incremental y completo | <ul><li>Contenido del archivo `.sync` del día 1: `visitor123 = a,b,c`</li><li>Contenido del archivo `.overwrite` del día 2: `visitor123 = c,d,e`</li><li>Contenido del ID del perfil del visitante 123 del día 3: `c,d,e`</li></ul> |
| Solo incremental | <ul><li>Contenido del archivo `.sync` del día 1: `visitor123 = a,b,c`</li><li>Contenido del archivo `.sync` del día 2: `visitor123 = c,d,e`</li><li>Contenido del ID del perfil del visitante 123 del día 3: `a,b,c,d,e`</li></ul> |

Para obtener más información sobre los tipos de archivo completos e incrementales, consulte:

* [Requisitos de nomenclatura y tamaño de archivo de Amazon S3 para datos entrantes...](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**¿Qué sucede si envío un archivo con ID de visitantes que nunca han realizado la sincronización de ID en la página?**

Durante el procesamiento, [!DNL Audience Manager] omite ese registro y pasa al siguiente. Si se configura un [DPID (ID del proveedor de datos)](../reference/ids-in-aam.md) como un DPID en varios dispositivos, los datos incorporados antes de una sincronización de ID se guardan y están disponibles para su uso poco después de que se produzca la sincronización de ID.

 

**¿Qué es la marca de tiempo y para qué sirve? ¿Cuál sería un ejemplo?**

Las marcas de tiempo se utilizan para el registro y el mantenimiento de registros. Son necesarias en la sintaxis del nombre de un archivo entrante con un formato correcto. Consulte:

* [Requisitos de nombre de Amazon S3 para archivos de datos de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**¿Qué es un? [!DNL Data Provider ID (DPID)] ¿y cómo lo consigo?**

El consultor de Adobe asignará un [DPID de tres o cuatro dígitos (ID del proveedor de datos)](../reference/ids-in-aam.md) a su fuente de datos. Este ID es único y no cambia.

 

**¿Qué tamaño pueden tener los archivos diarios de datos?**

Consulte [Compresión de archivos de transferencia de datos entrantes](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

 

**¿Audience Manager admite la compresión de archivos?**

Sí. Consulte:

* [Compresión de archivos de transferencia de datos entrantes](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Requisitos de nombre de Amazon S3 para archivos de datos de entrada](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**La clave principal de mi base de fuente de datos es una dirección de correo electrónico. ¿Esta información se considera personal?**

Sí. [!DNL Audience Manager] no almacena direcciones de correo electrónico en su base de datos. A los visitantes se les debe asignar un ID generado aleatoriamente o una versión de la dirección de correo electrónico con un cifrado hash unidireccional antes de iniciar la sincronización de ID.

 

**¿El contenido del archivo de datos distingue entre mayúsculas y minúsculas? ¿Qué sucede con la sincronización de ID?**

Hay dos componentes básicos en un archivo de datos: un [!UICONTROL User ID] (consulte [!UICONTROL User ID] en [Variables de archivo definidas](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)) y datos de perfil, normalmente en forma de pares clave-valor o códigos. La [!UICONTROL User ID] distingue entre mayúsculas y minúsculas. Normalmente, los datos de perfil o de clave-valor no distinguen entre mayúsculas y minúsculas.

 

**¿Debo usar FTP o [!DNL Amazon S3] para transferir archivos?**

Recomendamos [!DNL Amazon S3] porque el proceso es más sencillo. [!DNL Audience Manager] transfiere archivos FTP a [!DNL S3] de todas formas, por lo que el proceso es más ágil si usted mismo coloca los archivos en [!DNL Amazon S3]. Además, cuando los clientes cargan simultáneamente en FTP, están compartiendo el ancho de banda del FTP, por lo que es probable que las velocidades de carga sean más lentas. [!DNL Amazon S3] también se replica y distribuye, por eso suele ser más seguro y fiable que un servidor FTP. Para obtener más información, consulte [Acerca de Amazon S3](../reference/amazon-s3.md).

>[!WARNING]
>
>Estamos eliminando gradualmente el apoyo a las configuraciones de FTP. Aunque la ingesta de archivos de datos entrantes sigue siendo compatible con integraciones de FTP existentes, recomendamos encarecidamente utilizar [!DNL Amazon S3] para incorporar datos sin conexión en las nuevas integraciones. Consulte [Requisitos de nomenclatura y tamaño de archivo de Amazon S3 para archivos de datos entrantes](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) para obtener más información.

 

**¿Cómo procesa Audience Manager los archivos de entrada?**

[!DNL Audience Manager] utiliza [!DNL Amazon Simple Queue Service (SQS)] para el procesamiento de datos entrantes. Funciona de la siguiente manera:

1. [!DNL Audience Manager] Los clientes cargan sus datos de entrada en un espacio de [!DNL Amazon S3].
1. Los datos se incorporan a la cola de [!DNL Amazon SQS] y esperan a que [!DNL Audience Manager] los procese.
1. [!DNL Audience Manager] lee hasta 119 000 entradas de la cola de [!DNL Amazon SQS] y las divide en tres lotes como máximo. Los archivos de cada lote se procesan simultáneamente.

 

**Necesito cargar varios archivos al mismo tiempo. ¿Los archivos se procesarán simultáneamente?**

Depende. [!DNL Audience Manager] lee hasta 119 000 entradas de la cola de [!DNL Amazon SQS] y las divide en tres lotes como máximo. Los archivos se procesarán simultáneamente solo si terminan formando parte del mismo lote. Sin embargo, debido a la gran cantidad de datos introducidos a diario en [!DNL Audience Manager], no podemos garantizar ningún pedido de procesamiento de archivos.

>[!MORELIKETHIS]
>
>* [Proceso de transferencia de datos por lotes descrito](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

