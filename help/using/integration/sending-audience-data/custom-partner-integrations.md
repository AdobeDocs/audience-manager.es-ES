---
description: Esta página muestra las integraciones personalizadas entre Audience Manager y los socios de datos.
seo-description: Esta página muestra las integraciones personalizadas entre Audience Manager y los socios de datos.
seo-title: Integraciones de socios personalizados
solution: Audience Manager
title: Integraciones de socios personalizados
translation-type: tm+mt
source-git-commit: 3e7c993b1ddd2829e382de56ea246a667ff3ce0c

---


# Custom Partner Integrations {#custom-partner-integrations}

Esta página muestra las integraciones personalizadas entre Audience Manager y los socios de datos.

## Oracle Data Cloud {#oracle-data-cloud}

**Descripción**

Audience Manager ingesta la cookie y los datos de ID móviles de la nube de datos de Orale para Audience Marketplace a través de archivos de datos entrantes. Las especificaciones de integración personalizadas descritas a continuación solo se refieren a archivos de datos de entrada que contienen ID móviles (ID de dispositivo Android y IDFA).

<br> 

**Detalles específicos de integración**

Inbound Data Files received from the Oracle Data Cloud differ from the standard inbound file name syntax described in [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) and from the standard inbound file content syntax described in [Inbound Data File Contents: Syntax, Invalid Characters, Variables, and Examples](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Los elementos resaltados a continuación son obligatorios, además de los campos de implementación estándar para archivos de datos de entrada. Para obtener descripciones de todos los demás campos estándar y de los elementos de nombre de archivo, consulte Sintaxis del nombre de archivo y Sintaxis del contenido de archivo en las dos páginas vinculadas arriba.

<br> 

**Nomenclatura de archivos**

Los nombres de archivos ODC están estructurados como:

<pre>ftp_dpm_<b>odc</b>_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]</pre>

The `odc` file name element identifies the file as being imported from the Oracle Data Cloud and instructs the Audience Manager inbound file validator to process it as such.

<br> 

**Contenido del archivo**

Los campos del archivo de datos de entrada ODC deben aparecer en el orden que se muestra a continuación:

<pre>&lt;<b>ID type</b>&gt;&lt;TAB&gt;&lt;user ID&gt;&lt;TAB&gt;&lt;trait ID&gt;,&lt;trait ID&gt;,&lt;trait ID&gt;,...</pre>

`ID type` Puede ser:

* IDFA
* ID de dispositivo Android

>[!IMPORTANT]
>
>No envíe ID de dispositivo Android y IDFA en el mismo archivo de datos de entrada.

<br> 

**Archivo de entrada ODC de muestra**

Download the [sample file](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Este archivo califica varios IDFA para el ID de característica 38838. Puede abrir este archivo en un editor de texto estándar o en un editor de código.