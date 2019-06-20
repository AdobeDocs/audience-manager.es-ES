---
description: Información general para clientes técnicos y no técnicos que desean introducir datos de otros sistemas (sin conexión) en Audience Manager.
keywords: entrada
seo-description: Información general para clientes técnicos y no técnicos que desean introducir datos de otros sistemas (sin conexión) en Audience Manager.
seo-title: Enviar datos de lote a información general del Administrador de audiencia
solution: Audience Manager
title: Enviar datos de lote a información general del Administrador de audiencia
uuid: 472583 b 1-5057-4 add -8 e 3 c -5 e 50762 c 88 e 0
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Send Batch Data to Audience Manager Overview{#send-batch-data-to-audience-manager-overview}

Información general para clientes técnicos y no técnicos que desean introducir datos de otros sistemas (sin conexión) en Audience Manager.

## Ventajas

<!-- c_offline_to_online.xml -->

Puede hacer que los datos de otros sistemas estén disponibles en Audience Manager. Nuestro sistema puede ayudarle a desbloquear el valor y aprovechar los datos de usuario que ha recopilado anteriormente. This includes information about purchases, customer surveys, registration data, [!DNL CRM] databases, etc. Aunque cada integración presenta sus propios desafíos, todos comparten estos pasos comunes. Revise este material para ayudar a reducir el esfuerzo necesario para traer los datos sin conexión en línea.

## Paso 1: Sincronizar ID de usuario

Durante la sincronización, Audience Manager asigna ID únicos a los clientes y a sus usuarios. These IDs are known as the [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) and [!UICONTROL Unique User ID] ([!UICONTROL UUID]), respectively. Audience Manager uses the [!UICONTROL DPID] and [!UICONTROL UUID] to identify users and qualify them for traits, segments, audience groups, and for reporting. Additionally, our data collection code ([!UICONTROL DIL]) looks for these IDs to capture visitor data from your website. Cuando se complete este paso, Audience Manager y el repositorio sin conexión deben contener los ID correspondientes para cada registro de usuario.

Consideraciones importantes sobre este paso:

* **Ubicación de ID de cliente:** Audience Manager debe saber dónde aparece su ID de cliente en el sitio web (p. ej., está almacenado en una cookie, una variable de Analytics, en el código de página, etc.).
* **Excluir[!DNL PII]:** Los ID de usuario no deben contener información personal ([!DNL PII]).
* **Distinción entre mayúsculas y minúsculas y contenido:** Durante la sincronización de datos en tiempo real, Audience Manager captura los ID de usuario capturados desde su sitio a los ID transferidos desde el repositorio sin conexión. For example, if offline records hold information about [!DNL User123], but your site renders that ID as [!DNL USER123], Audience Manager sees these as different visitors. Como resultado, la información en línea para este visitante no se puede asociar con los registros correspondientes de la base de datos sin conexión. Los ID deben coincidir exactamente.

See [ID Synchronization for Inbound Data Transfers](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

<!-- 

<p> <b>Step 2: Create a Translation File</b> </p> 
<p>A translation file classifies data according to uniform and logical hierarchy. It is a taxonomy that helps you organize information from general categories (e.g., geography) to more precise classifications (e.g., <i>geography > United States > New York</i>). Also, it labels data with to easy to understand names such as "gender=male" or "color=green" instead of with your internal SKUs, abbreviations, or other names. The file lets Audience Manager display this information in a readable, logical manner. You and your data partners must create and share the translation file with Audience Manager before any real-time or server-to-server data transfers can begin. You can update this file on a schedule relevant to your business needs. </p> 
<p>Important considerations about this step: </p> 
<ul id="ul_6A05AECB0BD649B1BF1B34058E9008E2"> 
 <li id="li_39817ED898F14156A77FCAC066FE0968"> <b>Create a comprehensive list:</b> The translation file must include all the possible values that can be passed in on a particular key. For example, if you have category key called "color" and it accepts the values "red," "green," and "blue," the translation file must contain <i>all</i> those elements. </li> 
 <li id="li_19CAD7683BCF45278E2991C1EDBC9903"> <b>Case and content sensitivity:</b> The key-values in the file must match the values actually passed in to Audience Manager from your website. </li> 
</ul> 
<p>See DATA TRANSLATION FILE. </p>

 -->

## Paso 2: Formato de archivo de datos

Los nombres de archivo y el contenido siguen directrices estrictas. You *must* name and organize data files according to these specifications in this guide. Consulte:

* [Requisitos de nombre de Amazon S3 para archivos de datos de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Requisitos de nombre de FTP para archivos de datos de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)
* [Contenido del archivo de datos de entrada: Sintaxis, variables y ejemplos](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Los datos en línea están disponibles para los esfuerzos de mercadotecnia sin conexión

Cuando ponga datos sin conexión en línea, puede seguir utilizando esta información para campañas sin conexión. To do this, Audience Manager exports trait and segment information to an [!DNL FTP] or [!DNL Amazon S3] location of your choice. Póngase en contacto con el administrador de soluciones de socio para obtener más información o asistencia.

## Entornos

Audience Manager proporciona los entornos siguientes para la devolución de archivos:

<table id="table_A61AA64578944B23B5A7355F2A76E882"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Entorno </th> 
   <th colname="col02" class="entry"> Servicio </th> 
   <th colname="col2" class="entry"> Ubicación </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <b>Producción</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p> <code> ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-clients</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <b>Entorno beta</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p><code> sandbox-ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s 2 s-customers-sandbox-us-east -1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Lectura técnica adicional

Systems engineers, developers, or technical/implementation teams should review [Batch Data Transfer Process Described](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process) and the other articles in this section. Estos artículos proporcionan detalles sobre los protocolos de transferencia, el contenido de archivos y los requisitos de nombre de archivo.