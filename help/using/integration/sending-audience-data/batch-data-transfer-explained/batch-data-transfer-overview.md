---
description: Información general para clientes técnicos y no técnicos que desean importar datos de otros sistemas (sin conexión) a Audience Manager.
keywords: datos entrantes, por lotes, carga por lotes, datos por lotes
seo-description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager. To do so, use the batch upload option in Audience Manager.
seo-title: Send Batch Data to Audience Manager Overview
solution: Audience Manager
title: Información general sobre el envío de datos por lotes a Audience Manager
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
source-git-commit: f02e6bcfb7ff3560d9624c3dce7ff065a3a75748
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 6%

---

# Enviar datos por lotes a [!DNL Audience Manager] Información general {#send-batch-data-to-audience-manager-overview}

Información general para clientes técnicos y no técnicos que desean importar datos de otros sistemas (sin conexión) a [!DNL Audience Manager].

## Ventajas

Los datos de otros sistemas se pueden distribuir en [!DNL Audience Manager]. Nuestro sistema puede ayudarle a desbloquear el valor y aprovechar los datos de usuario que ha recopilado anteriormente. Esto incluye información sobre compras, encuestas a clientes, datos de registro, [!DNL CRM] bases de datos, etc. Si bien cada integración presenta sus propios desafíos, todas comparten estos pasos comunes. Revise este material para reducir el esfuerzo necesario para poner en línea los datos sin conexión.

## Paso 1: Sincronización de los ID de usuario

Durante la sincronización, [!DNL Audience Manager] asigna ID únicos a los clientes y a sus usuarios. Estos ID se conocen como [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) y [!UICONTROL Unique User ID] ([!UICONTROL UUID]), respectivamente. [!DNL Audience Manager] utiliza el [!UICONTROL DPID] y [!UICONTROL UUID] para identificar a los usuarios y calificarlos para [!UICONTROL traits], [!UICONTROL segments], grupos de audiencias y para informes. Además, nuestro código de recopilación de datos ([!UICONTROL DIL]) busca estos ID para capturar los datos de visitante de su sitio web. Una vez completado este paso, [!DNL Audience Manager] y el repositorio sin conexión deben contener los ID correspondientes para cada registro de usuario.

Consideraciones importantes sobre este paso:

* **Ubicación del ID del cliente:** [!DNL Audience Manager] necesita saber dónde aparece el ID de cliente en el sitio web (por ejemplo, si se almacena en una cookie, una variable de Analytics, en el código de la página, etc.).
* **Excluir [!DNL PII]:** Los ID de usuario no deben contener información personal identificable ([!DNL PII]).
* **Distinción entre mayúsculas y minúsculas y contenido:** Durante una sincronización de datos en tiempo real, los ID de usuario capturados del sitio por [!DNL Audience Manager] debe corresponder a los ID transferidos desde el repositorio sin conexión. Por ejemplo, si los registros sin conexión contienen información sobre [!DNL User123], pero el sitio procesa ese ID como [!DNL USER123], [!DNL Audience Manager] ve estos como visitantes diferentes. Como resultado, la información en línea de este visitante no se puede asociar con los registros correspondientes de la base de datos sin conexión. Los ID deben coincidir exactamente.

Consulte [Sincronización de ID para transferencias de datos entrantes](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Paso 2: Formato del archivo de datos

Los nombres de archivo y el contenido siguen estrictas directrices. Usted *debe* asigne un nombre a los archivos de datos y organícelos según las especificaciones de esta guía. Consulte:

* [Requisitos de nombre de Amazon S3 para archivos de datos de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Contenido del archivo de datos de entrada: sintaxis, variables y ejemplos](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Los datos en línea están disponibles para las actividades de marketing sin conexión

Cuando pone los datos sin conexión en línea, aún puede utilizar esta información para campañas sin conexión. Para ello, [!DNL Audience Manager] exporta información de rasgos y segmentos a un [!DNL FTP] o [!DNL Amazon S3] la ubicación que elija. Póngase en contacto con su administrador de Soluciones para socios para obtener información o ayuda adicional.

## Entornos

[!DNL Audience Manager] proporciona los siguientes entornos para la entrega de archivos:

| Entorno | Servicio | Ubicación |
|---------|----------|---------|
| Producción | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients</li><li>ftp-in.demdex.com</li></ul> |
| Entorno beta | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-customers-sandbox-us-east-1</li><li>sandbox-ftp-in.demdex.com</li></ul> |

{style="table-layout:auto"}

## Lectura técnica adicional

Los ingenieros de sistemas, los desarrolladores o los equipos técnicos/de implementación deben revisar [Proceso de transferencia de datos por lotes descrito](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) y los demás artículos de esta sección. En estos artículos se proporcionan detalles acerca de los protocolos de transferencia, el contenido de los archivos y los requisitos de nombre de archivo.
