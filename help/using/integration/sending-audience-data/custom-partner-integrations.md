---
description: Esta página muestra las integraciones personalizadas entre Audience Manager y los socios de datos.
seo-description: This page lists custom integrations between Audience Manager and data partners.
seo-title: Custom Partner Integrations
solution: Audience Manager
title: Integraciones de socios personalizadas
feature: Third-party Integration
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 18%

---

# Integraciones de socios personalizadas {#custom-partner-integrations}

Esta página muestra las integraciones personalizadas entre Audience Manager y los socios de datos.

## Oracle Data Cloud {#oracle-data-cloud}

### Descripción

Audience Manager ingesta la cookie y los datos de ID móviles de la nube de datos de Orale para Audience Marketplace a través de archivos de datos entrantes. Las especificaciones de integración personalizadas que se describen a continuación solo hacen referencia a archivos de datos de entrada que contienen ID móviles (ID de dispositivos IDFA y Android).

### Detalles de integración

Los archivos de datos de entrada recibidos de la nube de datos de Oracle difieren de la sintaxis de nombre de archivo de entrada estándar descrita en [Requisitos de tamaño de archivo y nombre de Amazon S3 para archivos de datos de entrada](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) y de la sintaxis de contenido de archivo entrante estándar descrita en [Contenido del archivo de datos de entrada: sintaxis, caracteres no válidos, variables y ejemplos](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Los elementos que se resaltan a continuación son obligatorios, además de los campos de implementación estándar para los archivos de datos de entrada. Para obtener descripciones de todos los demás campos estándar y elementos de nombre de archivo, consulte Sintaxis del nombre de archivo y Sintaxis del contenido de archivo en las dos páginas vinculadas anteriormente.

### Nomenclatura de archivo

Los nombres de archivo ODC se estructuran de la siguiente manera:

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

El `odc` El elemento de nombre de archivo identifica el archivo como importado desde la nube de datos de Oracle e indica al validador de archivos de entrada del Audience Manager que lo procese como tal.

### Contenido de archivo

Los campos del archivo de datos de entrada ODC deben aparecer en el orden indicado a continuación:

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

El `ID type` puede ser:

* IDFA
* ID de dispositivo Android

>[!IMPORTANT]
>
>No envíe ID de dispositivos IDFA y Android en el mismo archivo de datos de entrada.

## Archivo entrante de ODC de muestra

Descargue la [archivo de muestra](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Este archivo califica varios IDFA para el 38838 de ID de rasgo. Puede abrir este archivo en un editor de texto estándar o en un editor de código.
