---
description: Esta página muestra las integraciones personalizadas entre Audience Manager y los socios de datos.
seo-description: Esta página muestra las integraciones personalizadas entre Audience Manager y los socios de datos.
seo-title: Integraciones de socios personalizadas
solution: Audience Manager
title: Integraciones de socios personalizadas
feature: Third-party Integration
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 22%

---

# Integraciones de socios personalizadas {#custom-partner-integrations}

Esta página muestra las integraciones personalizadas entre Audience Manager y los socios de datos.

## Nube de datos de oracle {#oracle-data-cloud}

### Descripción

Audience Manager ingesta la cookie y los datos de ID móviles de la nube de datos de Orale para Audience Marketplace a través de archivos de datos entrantes. Las especificaciones de integración personalizada que se describen a continuación se refieren únicamente a archivos de datos entrantes que contienen ID móviles (IDFA e ID de dispositivos Android).

### Detalles de integración

Los archivos de datos de entrada recibidos de la nube de datos de Oracle difieren de la sintaxis de nombre de archivo de entrada estándar que se describe en [Requisitos de tamaño de archivo y nombre de Amazon S3 para archivos de datos de entrada](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) y de la sintaxis de contenido de archivo de entrada estándar que se describe en [Contenido del archivo de datos de entrada: Sintaxis, caracteres no válidos, variables y ejemplos](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Los elementos resaltados a continuación son obligatorios, además de los campos de implementación estándar para archivos de datos entrantes. Para obtener descripciones de todos los demás campos estándar y elementos de nombre de archivo, consulte Sintaxis de nombres de archivo y Sintaxis de contenido de archivo en las dos páginas vinculadas anteriormente.

### Asignación de nombres de archivo

Los nombres de archivos ODC están estructurados de la siguiente manera:

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

El elemento de nombre de archivo `odc` identifica el archivo como importado de la nube de datos de Oracle e indica al validador de archivos entrantes del Audience Manager que lo procese como tal.

### Contenido del archivo

Los campos del archivo de datos de entrada de ODC deben aparecer en el orden que se muestra a continuación:

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

El `ID type` puede ser:

* IDFA
* ID del dispositivo Android

>[!IMPORTANT]
>
>No envíe ID de dispositivo de IDFA y Android en el mismo archivo de datos de entrada.

## Archivo de entrada ODC de muestra

Descargue el [archivo de muestra](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Este archivo clasifica varios IDFA para el ID de rasgo 38838. Puede abrir este archivo en un editor de texto estándar o en un editor de código.
