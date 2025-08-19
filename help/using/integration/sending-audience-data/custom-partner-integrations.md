---
description: Esta página muestra las integraciones personalizadas entre Audience Manager y los socios de datos.
seo-description: This page lists custom integrations between Audience Manager and data partners.
seo-title: Custom Partner Integrations
solution: Audience Manager
title: Integraciones personalizadas de socios
feature: Third-party Integration
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 15%

---

# Integraciones personalizadas de socios {#custom-partner-integrations}

Esta página muestra las integraciones personalizadas entre Audience Manager y los socios de datos.

## Nube de datos de Oracle {#oracle-data-cloud}

### Descripción

Audience Manager ingesta la cookie y los datos de ID móviles de la nube de datos de Orale para Audience Marketplace a través de archivos de datos entrantes. Las especificaciones de integración personalizada que se describen a continuación se refieren únicamente a los archivos de datos de entrada que contienen ID móviles (IDFA e ID de dispositivo Android).

### Detalles de la integración

Los Archivos de datos de entrada recibidos de Oracle Data Cloud difieren de la sintaxis estándar de nombre de archivo de entrada descrita en [Amazon Requisitos de nombre y tamaño de Archivo de S3 para la Archivos](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) de datos de entrada y de la sintaxis de contenido de archivo de entrada estándar descrita en [Contenido de Archivo de datos de entrada: Sintaxis, caracteres no válidos, variables y ejemplos](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Los elementos resaltados a continuación son obligatorios, además de los campos de implementación estándar para los archivos de datos de entrada. Para obtener descripciones de todos los demás campos estándar y elementos de nombre de archivo, consulte Sintaxis de nombre de Archivo y Sintaxis de contenido de Archivo en las dos páginas vinculadas anteriormente.

### Archivo nomenclatura

Los nombres de archivo ODC se estructuran como:

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

El `odc` elemento nombre de archivo identifica el archivo como importado de Oracle Data Cloud e indica al validador de archivos de entrada Audience Manager que lo procese como tal.

### Contenido Archivo

Los campos del archivo de datos de entrada de ODC deben aparecer en el orden que se muestra a continuación:

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

El `ID type` puede ser:

* IDFA
* ID de dispositivo Android

>[!IMPORTANT]
>
>No envíe IDFA e ID de dispositivo Android en el mismo archivo de datos de entrada.

## Archivo de entrada ODC de muestra

Descargue el archivo[ de ](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync)muestra. Este archivo califica varios IDFA para el ID de rasgo 38838. Puede abrir este archivo en una editor de texto estándar o en una editor de código.
