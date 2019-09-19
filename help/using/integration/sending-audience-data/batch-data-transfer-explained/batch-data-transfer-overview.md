---
description: Información general para clientes técnicos y no técnicos que deseen traer datos de otros sistemas (sin conexión) a Audience Manager.
keywords: entrante, lote, carga por lotes, datos por lotes
seo-description: Información general para clientes técnicos y no técnicos que deseen traer datos de otros sistemas (sin conexión) a Audience Manager. Para ello, utilice la opción de carga por lotes en Audience Manager.
seo-title: Información general sobre el envío de datos por lotes a Audience Manager
solution: Audience Manager
title: Información general sobre el envío de datos por lotes a Audience Manager
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
translation-type: tm+mt
source-git-commit: 2e3adc8f0b2fe6efd9ca57f1d763ee4476d2edee

---


# Información general sobre el envío de datos por lotes a Audience Manager{#send-batch-data-to-audience-manager-overview}

Información general para clientes técnicos y no técnicos que deseen traer datos de otros sistemas (sin conexión) a Audience Manager.

## Ventajas

<!-- c_offline_to_online.xml -->

Puede hacer que los datos de otros sistemas estén disponibles en Audience Manager. Nuestro sistema puede ayudarle a desbloquear valor y a aprovechar los datos de usuario que ha recopilado anteriormente. Esto incluye información sobre compras, encuestas de clientes, datos de registro, bases de datos, [!DNL CRM] etc. Aunque cada integración presenta sus propios desafíos, todos comparten estos pasos comunes. Revise este material para reducir el esfuerzo necesario para poner en línea los datos sin conexión.

## Paso 1: Sincronizar ID de usuario

Durante la sincronización, Audience Manager asigna ID únicos a los clientes y a sus usuarios. Estos ID se conocen como [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) y [!UICONTROL Unique User ID] ([!UICONTROL UUID]), respectivamente. Audience Manager utiliza [!UICONTROL DPID] y [!UICONTROL UUID] para identificar a los usuarios y calificarlos para características, segmentos, grupos de audiencias y para la generación de informes. Además, nuestro código de recopilación de datos ([!UICONTROL DIL]) busca estos ID para capturar los datos de los visitantes del sitio web. Cuando se complete este paso, Audience Manager y el repositorio sin conexión deben contener los ID correspondientes para cada registro de usuario.

Consideraciones importantes sobre este paso:

* **** Ubicación del ID de cliente: Audience Manager necesita saber dónde aparece su ID de cliente en su sitio web (por ejemplo, si se almacena en una cookie, una variable de Analytics, en el código de página, etc.).
* **[!DNL PII]Excluir**: Los ID de usuario no deben contener información de identificación personal ([!DNL PII]).
* **** Distinción entre mayúsculas y minúsculas y contenido: Durante una sincronización de datos en tiempo real, los ID de usuario capturados en el sitio por Audience Manager deben corresponderse con los ID pasados desde el repositorio sin conexión. Por ejemplo, si los registros sin conexión contienen información sobre [!DNL User123]pero el sitio procesa esa ID como [!DNL USER123], Audience Manager los ve como visitantes diferentes. Como resultado, la información en línea de este visitante no se puede asociar con los registros correspondientes de la base de datos sin conexión. Los ID deben coincidir exactamente.

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

## Paso 2:Formato de archivo de datos

Los nombres de archivo y el contenido siguen directrices estrictas. En esta guía *debe* nombrar y organizar los archivos de datos según estas especificaciones. Consulte:

* [Requisitos de nombre de Amazon S3 para archivos de datos de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Contenido del archivo de datos de entrada: Sintaxis, variables y ejemplos](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Los datos en línea están disponibles para los esfuerzos de mercadotecnia sin conexión

Al poner los datos sin conexión en línea, puede seguir utilizando esta información para campañas sin conexión. Para ello, Audience Manager exporta la información de características y segmentos a una [!DNL FTP] o [!DNL Amazon S3] ubicación de su elección. Póngase en contacto con el administrador de soluciones de socio para obtener información o asistencia adicionales.

## Entornos

Audience Manager proporciona los siguientes entornos para la eliminación de archivos:

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
   <td colname="col2"> <p> <code> demdex-s2s-customers-sandbox-us-east-1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Lectura técnica adicional

Los ingenieros de sistemas, desarrolladores o equipos técnicos/de implementación deben revisar el proceso [de transferencia de datos por lotes descrito](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) y los demás artículos de esta sección. Estos artículos proporcionan detalles sobre los protocolos de transferencia, el contenido de los archivos y los requisitos de nombre de archivo.