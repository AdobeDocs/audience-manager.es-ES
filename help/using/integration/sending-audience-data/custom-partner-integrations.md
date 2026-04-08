---
description: Esta página muestra las integraciones personalizadas entre Audience Manager y los socios de datos.
seo-description: This page lists custom integrations between Audience Manager and data partners.
seo-title: Custom Partner Integrations
solution: Audience Manager
title: Integraciones de socios personalizadas
feature: Third-party Integration
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
TQID: https://experienceleague.adobe.com/0QvyTQOmjkES1ZO47uu7JTh07-5--uHIgCbJ9iAYfrE
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
  - id: d8f86c1e-15ad-457f-9d6f-5e756573fad4
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 271
ht-degree: 15%

---

# Integraciones de socios personalizadas {#custom-partner-integrations}

Esta página muestra las integraciones personalizadas entre Audience Manager y los socios de datos.

## Oracle Data Cloud {#oracle-data-cloud}

### Descripción

Audience Manager ingesta la cookie y los datos de ID móviles de la nube de datos de Orale para Audience Marketplace a través de archivos de datos entrantes. Las especificaciones de integración personalizadas que se describen a continuación solo hacen referencia a archivos de datos de entrada que contienen ID móviles (IDFA e ID de dispositivo Android).

### Detalles de integración

Los archivos de datos de entrada recibidos de Oracle Data Cloud difieren de la sintaxis de nombre de archivo de entrada estándar descrita en [Requisitos de tamaño de archivo y nombre de Amazon S3 para archivos de datos de entrada](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) y de la sintaxis de contenido de archivo de entrada estándar descrita en [Contenido de archivo de datos de entrada: sintaxis, caracteres no válidos, variables y ejemplos](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Los elementos que se resaltan a continuación son obligatorios, además de los campos de implementación estándar para los archivos de datos de entrada. Para obtener descripciones de todos los demás campos estándar y elementos de nombre de archivo, consulte Sintaxis del nombre de archivo y Sintaxis del contenido de archivo en las dos páginas vinculadas anteriormente.

### Nomenclatura de archivo

Los nombres de archivo ODC se estructuran de la siguiente manera:

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

El elemento de nombre de archivo `odc` identifica el archivo como importado desde Oracle Data Cloud e indica al validador de archivos entrantes de Audience Manager que lo procese como tal.

### Contenido de archivo

Los campos del archivo de datos de entrada ODC deben aparecer en el orden indicado a continuación:

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

El(la) `ID type` puede ser:

* IDFA
* ID de dispositivo Android

>[!IMPORTANT]
>
>No envíe ID de dispositivos IDFA y Android en el mismo archivo de datos de entrada.

## Archivo entrante de ODC de muestra

Descargar [archivo de muestra](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Este archivo califica varios IDFA para el 38838 de ID de rasgo. Puede abrir este archivo en un editor de texto estándar o en un editor de código.
