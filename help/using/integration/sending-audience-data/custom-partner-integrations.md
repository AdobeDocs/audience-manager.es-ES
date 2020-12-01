---
description: Esta página muestra las integraciones personalizadas entre Audience Manager y los socios de datos.
seo-description: Esta página muestra las integraciones personalizadas entre Audience Manager y los socios de datos.
seo-title: Integraciones de socios personalizadas
solution: Audience Manager
title: Integraciones de socios personalizadas
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 22%

---


# Integraciones de socios personalizadas {#custom-partner-integrations}

Esta página muestra las integraciones personalizadas entre Audience Manager y los socios de datos.

## Oracle Data Cloud {#oracle-data-cloud}

### Descripción

Audience Manager ingesta la cookie y los datos de ID móviles de la nube de datos de Orale para Audience Marketplace a través de archivos de datos entrantes. Las especificaciones de integración personalizada que se describen a continuación se refieren únicamente a los archivos de datos de entrada que contienen ID de dispositivos móviles (IDFA y Android Device ID).

### Especificaciones de integración

Los archivos de datos de entrada recibidos de Oracle Data Cloud difieren de la sintaxis de nombre de archivo de entrada estándar descrita en [Requisitos de nombre y tamaño de archivo de Amazon S3 para archivos de datos de entrada](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) y de la sintaxis de contenido de archivo de entrada estándar descrita en [Contenido del archivo de datos de entrada: Sintaxis, Caracteres no válidos, Variables y Ejemplos](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Los elementos resaltados a continuación son obligatorios, además de los campos de implementación estándar para archivos de datos de entrada. Para obtener descripciones de todos los demás campos estándar y elementos de nombre de archivo, consulte Sintaxis del nombre de archivo y Sintaxis del contenido de archivo en las dos páginas vinculadas anteriormente.

### Nominación de archivo

Los nombres de archivo ODC están estructurados como:

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

El elemento `odc` nombre de archivo identifica el archivo como importado desde Oracle Data Cloud e indica al validador de archivos de entrada del Audience Manager que lo procese como tal.

### Contenido del archivo

Los campos del archivo de datos de entrada ODC deben aparecer en el orden que se muestra a continuación:

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

El `ID type` puede ser:

* IDFA
* ID de dispositivo de Android

>[!IMPORTANT]
>
>No envíe ID de dispositivos de IDFA y Android en el mismo archivo de datos de entrada.

## Archivo de entrada ODC de muestra

Descargue el [archivo de muestra](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Este archivo califica varios IDFA para el ID de característica 38838. Puede abrir este archivo en un editor de texto estándar o en un editor de código.