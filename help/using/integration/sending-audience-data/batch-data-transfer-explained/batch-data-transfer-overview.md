---
description: Información general para clientes técnicos y no técnicos que desean introducir datos de otros sistemas (sin conexión) en Audience Manager.
keywords: entrante, lote, carga por lotes, datos por lotes
seo-description: Información general para clientes técnicos y no técnicos que desean introducir datos de otros sistemas (sin conexión) en Audience Manager. Para ello, utilice la opción de carga por lotes en el Audience Manager .
seo-title: Información general sobre el envío de datos por lotes a Audience Manager
solution: Audience Manager
title: Información general sobre el envío de datos por lotes a Audience Manager
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Transferencias de datos de entrada
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 7%

---

# Enviar datos por lotes a [!DNL Audience Manager] Información general {#send-batch-data-to-audience-manager-overview}

Información general para clientes técnicos y no técnicos que desean introducir datos de otros sistemas (sin conexión) en [!DNL Audience Manager].

## Ventajas

Puede hacer que los datos de otros sistemas estén disponibles en [!DNL Audience Manager]. Nuestro sistema puede ayudarle a desbloquear valor y aprovechar los datos de usuario que ha recopilado anteriormente. Esto incluye información sobre compras, encuestas de clientes, datos de registro, [!DNL CRM] bases de datos, etc. Aunque cada integración presenta sus propios desafíos, todos comparten estos pasos comunes. Revise este material para reducir el esfuerzo necesario para poner en línea los datos sin conexión.

## Paso 1: Sincronizar ID de usuario

Durante la sincronización, [!DNL Audience Manager] asigna ID únicos a los clientes y a sus usuarios. Estos ID se conocen como [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) y [!UICONTROL Unique User ID] ([!UICONTROL UUID]), respectivamente. [!DNL Audience Manager] utiliza  [!UICONTROL DPID] y  [!UICONTROL UUID] para identificar a los usuarios y calificarlos para  [!UICONTROL traits],  [!UICONTROL segments], grupos de audiencia y para la creación de informes. Además, nuestro código de recopilación de datos ([!UICONTROL DIL]) busca estos ID para capturar los datos de visitantes de su sitio web. Cuando se complete este paso, [!DNL Audience Manager] y el repositorio sin conexión deben contener los ID correspondientes para cada registro de usuario.

Consideraciones importantes sobre este paso:

* **Ubicación del ID de cliente:** [!DNL Audience Manager] debe saber dónde aparece el ID de cliente en el sitio web (por ejemplo, si se almacena en una cookie, una variable de Analytics, en el código de página, etc.).
* **Excluir  [!DNL PII]:** Los ID de usuario no deben contener información de identificación personal ([!DNL PII]).
* **Distinción entre mayúsculas y minúsculas y contenido:** durante una sincronización de datos en tiempo real, los ID de usuario capturados desde el sitio de  [!DNL Audience Manager] deben corresponder a los ID pasados desde el repositorio sin conexión. Por ejemplo, si los registros sin conexión contienen información sobre [!DNL User123], pero el sitio procesa ese ID como [!DNL USER123], [!DNL Audience Manager] los ve como visitantes diferentes. Como resultado, la información en línea de este visitante no se puede asociar a los registros correspondientes de la base de datos sin conexión. Los ID deben coincidir exactamente.

Consulte [Sincronización de ID para transferencias de datos entrantes](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Paso 2: Formato del archivo de datos

Los nombres de archivo y el contenido siguen directrices estrictas. *debe* asignar un nombre a los archivos de datos y organizarlos de acuerdo con estas especificaciones en esta guía. Consulte:

* [Requisitos de nombre de Amazon S3 para archivos de datos de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Contenido del archivo de datos de entrada: Sintaxis, variables y ejemplos](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Los datos en línea están disponibles para los esfuerzos de marketing sin conexión

Al conectar datos sin conexión, puede seguir utilizando esta información para campañas sin conexión. Para ello, [!DNL Audience Manager] exporta la información de rasgos y segmentos a la ubicación [!DNL FTP] o [!DNL Amazon S3] que elija. Póngase en contacto con el administrador de soluciones de socios para obtener más información o ayuda.

## Entornos

[!DNL Audience Manager] proporciona los siguientes entornos para la colocación de archivos:

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

Los ingenieros de sistemas, desarrolladores o equipos técnicos/de implementación deben revisar el [Proceso de transferencia de datos por lotes descrito](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) y los demás artículos de esta sección. En estos artículos se proporcionan detalles sobre los protocolos de transferencia, el contenido del archivo y los requisitos de nombre de archivo.
