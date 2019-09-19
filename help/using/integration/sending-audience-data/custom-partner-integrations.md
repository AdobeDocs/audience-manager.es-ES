---
description: Esta página muestra las integraciones personalizadas entre Audience Manager y los socios de datos.
seo-description: Esta página muestra las integraciones personalizadas entre Audience Manager y los socios de datos.
seo-title: Integraciones de socios personalizadas
solution: Audience Manager
title: Integraciones de socios personalizadas
translation-type: tm+mt
source-git-commit: 3e7c993b1ddd2829e382de56ea246a667ff3ce0c

---


# Integraciones de socios personalizadas {#custom-partner-integrations}

Esta página muestra las integraciones personalizadas entre Audience Manager y los socios de datos.

## Oracle Data Cloud {#oracle-data-cloud}

**Descripción**

Audience Manager ingesta la cookie y los datos de ID móviles de la nube de datos de Orale para Audience Marketplace a través de archivos de datos entrantes. Las especificaciones de integración personalizada que se describen a continuación se refieren únicamente a los archivos de datos de entrada que contienen ID de dispositivos móviles (IDFA y Android Device ID).

<br> 

**Especificaciones de integración**

Los archivos de datos de entrada recibidos de Oracle Data Cloud difieren de la sintaxis de nombre de archivo de entrada estándar descrita en los requisitos de nombre y tamaño de archivo de [Amazon S3 para archivos](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) de datos de entrada y de la sintaxis de contenido de archivo de entrada estándar descrita en Contenido del archivo de datos de [entrada: Sintaxis, Caracteres no válidos, Variables y Ejemplos](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Los elementos resaltados a continuación son obligatorios, además de los campos de implementación estándar para archivos de datos de entrada. Para obtener descripciones de todos los demás campos estándar y elementos de nombre de archivo, consulte Sintaxis del nombre de archivo y Sintaxis del contenido de archivo en las dos páginas vinculadas anteriormente.

<br> 

**Nominación de archivo**

Los nombres de archivo ODC están estructurados como:

<pre>ftp_dpm_<b>odc</b>_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]</pre>

El elemento `odc` file name identifica el archivo como importado de Oracle Data Cloud e indica al validador de archivos de entrada de Audience Manager que lo procese como tal.

<br> 

**Contenido del archivo**

Los campos del archivo de datos de entrada ODC deben aparecer en el orden que se muestra a continuación:

<pre>&lt;<b>ID de tipo</b>&gt;&lt;TAB&gt;&lt;ID de usuario&gt;&lt;TAB&gt;&lt;ID de rasgo&gt;,&lt;ID de rasgo&gt;,&lt;ID de rasgo&gt;,...</pre>

Puede `ID type` ser:

* IDFA
* ID de dispositivo de Android

>[!IMPORTANT]
>
>No envíe ID de dispositivos de IDFA y Android en el mismo archivo de datos de entrada.

<br> 

**Archivo de entrada ODC de muestra**

Descargue el archivo [de](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync)muestra. Este archivo califica varios IDFA para el ID de característica 38838. Puede abrir este archivo en un editor de texto estándar o en un editor de código.