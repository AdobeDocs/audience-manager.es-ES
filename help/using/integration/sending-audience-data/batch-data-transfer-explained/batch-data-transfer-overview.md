---
description: Información general para clientes técnicos y no técnicos que desean importar datos de otros sistemas (sin conexión) a Audience Manager.
keywords: datos entrantes, por lotes, carga por lotes, datos por lotes
seo-description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager. To do so, use the batch upload option in Audience Manager.
seo-title: Send Batch Data to Audience Manager Overview
solution: Audience Manager
title: Resumen de envío de datos por lotes al Audience Manager
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
source-git-commit: f02e6bcfb7ff3560d9624c3dce7ff065a3a75748
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 4%

---

# Información general sobre el envío de datos por lotes a [!DNL Audience Manager] {#send-batch-data-to-audience-manager-overview}

Información general para clientes técnicos y no técnicos que desean importar datos de otros sistemas (sin conexión) a [!DNL Audience Manager].

## Ventajas

Puede hacer que los datos de otros sistemas estén disponibles en [!DNL Audience Manager]. Nuestro sistema puede ayudarle a desbloquear el valor y aprovechar los datos de usuario que ha recopilado anteriormente. Esto incluye información sobre compras, encuestas a clientes, datos de registro, [!DNL CRM] bases de datos, etc. Si bien cada integración presenta sus propios desafíos, todas comparten estos pasos comunes. Revise este material para reducir el esfuerzo necesario para poner en línea los datos sin conexión.

## Paso 1: Sincronización de los ID de usuario

Durante la sincronización, [!DNL Audience Manager] asigna identificadores únicos a los clientes y a sus usuarios. Estos identificadores se conocen como [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) y [!UICONTROL Unique User ID] ([!UICONTROL UUID]), respectivamente. [!DNL Audience Manager] usa [!UICONTROL DPID] y [!UICONTROL UUID] para identificar usuarios y calificarlos para [!UICONTROL traits], [!UICONTROL segments], grupos de audiencias y para la creación de informes. Además, nuestro código de recopilación de datos ([!UICONTROL DIL]) busca estos ID para capturar datos de visitantes de su sitio web. Una vez completado este paso, [!DNL Audience Manager] y el repositorio sin conexión deben contener los identificadores correspondientes para cada registro de usuario.

Consideraciones importantes sobre este paso:

* **Ubicación del ID de cliente:** [!DNL Audience Manager] necesita saber dónde aparece el ID de cliente en el sitio web (por ejemplo, si se almacena en una cookie, una variable de Analytics, en el código de página, etc.).
* **Excluir [!DNL PII]:** Los identificadores de usuario no deben contener información personal ([!DNL PII]).
* **Distinción entre mayúsculas y minúsculas y el contenido:** Durante una sincronización de datos en tiempo real, los identificadores de usuario capturados del sitio por [!DNL Audience Manager] deben corresponder a los identificadores pasados desde el repositorio sin conexión. Por ejemplo, si los registros sin conexión contienen información sobre [!DNL User123], pero el sitio procesa ese identificador como [!DNL USER123], [!DNL Audience Manager] los ve como visitantes diferentes. Como resultado, la información en línea de este visitante no se puede asociar con los registros correspondientes de la base de datos sin conexión. Los ID deben coincidir exactamente.

Ver [Sincronización de ID para transferencias de datos entrantes](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Paso 2: Formato del archivo de datos

Los nombres de archivo y el contenido siguen estrictas directrices. Debe *asignar un nombre a los archivos de datos y organizarlos según estas especificaciones en esta guía.* Consulte:

* [Requisitos de nombre de Amazon S3 para archivos de datos de entrada](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Contenido del archivo de datos de entrada: sintaxis, variables y ejemplos](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Los datos en línea están disponibles para las actividades de marketing sin conexión

Cuando pone los datos sin conexión en línea, aún puede utilizar esta información para campañas sin conexión. Para ello, [!DNL Audience Manager] exporta información de características y segmentos a una ubicación [!DNL FTP] o [!DNL Amazon S3] de su elección. Póngase en contacto con su administrador de Soluciones para socios para obtener información o ayuda adicional.

## Entornos

[!DNL Audience Manager] proporciona los siguientes entornos para la entrega de archivos:

| Entorno | Servicio | Ubicación |
|---------|----------|---------|
| Producción | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-customers</li><li>ftp-in.demdex.com</li></ul> |
| Entorno de Beta | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-customers-sandbox-us-east-1</li><li>sandbox-ftp-in.demdex.com</li></ul> |

{style="table-layout:auto"}

## Lectura técnica adicional

Los ingenieros de sistemas, desarrolladores o equipos técnicos/de implementación deberían revisar [Proceso de transferencia de datos por lotes descrito](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) y los demás artículos de esta sección. En estos artículos se proporcionan detalles acerca de los protocolos de transferencia, el contenido de los archivos y los requisitos de nombre de archivo.
