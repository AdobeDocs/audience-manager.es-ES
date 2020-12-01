---
description: Información general para clientes técnicos y no técnicos que deseen llevar datos de otros sistemas (sin conexión) al Audience Manager.
keywords: inbound, batch, batch upload, batch data
seo-description: Información general para clientes técnicos y no técnicos que deseen llevar datos de otros sistemas (sin conexión) al Audience Manager. Para ello, utilice la opción de carga por lotes en Audience Manager.
seo-title: Información general sobre el envío de datos por lotes a Audience Manager
solution: Audience Manager
title: Información general sobre el envío de datos por lotes a Audience Manager
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 6%

---


# Enviar datos por lotes a [!DNL Audience Manager] Información general {#send-batch-data-to-audience-manager-overview}

Información general para clientes técnicos y no técnicos que desean traer datos de otros sistemas (sin conexión) a [!DNL Audience Manager].

## Ventajas

Puede hacer que los datos de otros sistemas estén disponibles en [!DNL Audience Manager]. Nuestro sistema puede ayudarle a desbloquear valor y a aprovechar los datos de usuario que ha recopilado anteriormente. Esto incluye información sobre compras, encuestas de clientes, datos de registro, [!DNL CRM] bases de datos, etc. Aunque cada integración presenta sus propios desafíos, todos comparten estos pasos comunes. Revise este material para reducir el esfuerzo necesario para poner en línea los datos sin conexión.

## Paso 1: Sincronizar ID de usuario

Durante la sincronización, [!DNL Audience Manager] asigna ID únicos a los clientes y a sus usuarios. Estos ID se conocen como [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) y [!UICONTROL Unique User ID] ([!UICONTROL UUID]), respectivamente. [!DNL Audience Manager] utiliza  [!UICONTROL DPID] y  [!UICONTROL UUID] para identificar a los usuarios y calificarlos para grupos de  [!UICONTROL traits]audiencia,  [!UICONTROL segments]grupos de sistemas de informes y para su uso. Además, nuestro código de recopilación de datos ([!UICONTROL DIL]) busca estos ID para capturar datos de visitante de su sitio web. Cuando se complete este paso, [!DNL Audience Manager] y el repositorio sin conexión deben contener los ID correspondientes para cada registro de usuario.

Consideraciones importantes sobre este paso:

* **Ubicación del ID de cliente:** [!DNL Audience Manager] necesita saber dónde aparece el ID de cliente en el sitio web (por ejemplo, si se almacena en una cookie, una variable de Analytics, en el código de página, etc.).
* **Excluir  [!DNL PII]:Los ID** de usuario no deben contener información de identificación personal ([!DNL PII]).
* **Distinción entre mayúsculas y minúsculas y contenido:** Durante una sincronización de datos en tiempo real, los ID de usuario capturados en el sitio por  [!DNL Audience Manager] deben corresponder a los ID pasados desde el repositorio sin conexión. Por ejemplo: si los registros sin conexión contienen información sobre [!DNL User123] pero el sitio procesa esa ID como [!DNL USER123], [!DNL Audience Manager] los ve como visitantes diferentes. Como resultado, la información en línea de este visitante no se puede asociar con los registros correspondientes de la base de datos sin conexión. Los ID deben coincidir exactamente.

Consulte [Sincronización de ID para transferencias de datos de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Paso 2: Formato de archivo de datos

Los nombres de archivo y el contenido siguen directrices estrictas. Usted *debe* nombrar y organizar los archivos de datos según estas especificaciones en esta guía. Consulte:

* [Requisitos de nombre de Amazon S3 para archivos de datos de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Contenido del archivo de datos de entrada: Sintaxis, variables y ejemplos](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Los datos en línea están disponibles para los esfuerzos de mercadotecnia sin conexión

Al poner los datos sin conexión en línea, puede seguir utilizando esta información para campañas sin conexión. Para ello, [!DNL Audience Manager] exporta la información de características y segmentos a una [!DNL FTP] o [!DNL Amazon S3] ubicación de su elección. Póngase en contacto con el administrador de soluciones de socio para obtener información o asistencia adicionales.

## Entornos

[!DNL Audience Manager] proporciona los siguientes entornos para la lista desplegable de archivos:

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
   <td colname="col2"> <p> <code> demdex-s2s-clients-sandbox-us-east-1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Lectura técnica adicional

Los ingenieros de sistemas, desarrolladores o equipos técnicos/de implementación deben revisar [Proceso de transferencia de datos por lotes descrito](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) y los demás artículos de esta sección. Estos artículos proporcionan detalles sobre los protocolos de transferencia, el contenido de los archivos y los requisitos de nombre de archivo.
