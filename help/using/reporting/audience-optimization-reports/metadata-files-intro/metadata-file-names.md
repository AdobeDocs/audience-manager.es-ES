---
description: Asigne un nombre al archivo de metadatos de Optimización de audiencia según estas especificaciones.
seo-description: Asigne un nombre al archivo de metadatos de Optimización de audiencia según estas especificaciones.
seo-title: Convenciones de nombres para archivos de metadatos
solution: Audience Manager
title: Convenciones de nombres para archivos de metadatos
uuid: cab 55 b 2 a -2 e 54-45 f 6-aeea -3735 b 911 f 821
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Naming Conventions for Metadata Files{#naming-conventions-for-metadata-files}

Asigne un nombre al archivo de metadatos de Optimización de audiencia según estas especificaciones.

## Syntax and ID Categories {#syntax}

La siguiente sintaxis define la estructura de un nombre de archivo de metadatos bien formado. Note, *italics* indicates a variable placeholder. Los demás elementos son constantes y no cambian.

**Sintaxis:** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*No* utilice extensiones de archivo en los archivos de metadatos (.txt u otro).

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* The middle component **0** is technically the Parent ID, which is a legacy field. The value should always be set as **0**.
* El ID secundario puede tener un valor entre 1 y 10, según la dimensión. Vea lo siguiente:

## Child ID dimensions {#child-dimension}

En el nombre del archivo de metadatos, el ID secundario es un identificador que clasifica el tipo de datos de un archivo y lo coloca en una jerarquía. Puede etiquetar el ID secundario en el nombre de archivo con los siguientes ID de categoría:

1. Campaign
1. Elemento creativo
1. Ubicación
1. Exchange
1. Sitio
1. Advertiser (if using integration codes in a [data source](../../../features/manage-datasources.md#details))
1. Orden de inserción (IO)
1. Vertical (es decir, una industria específica o una categoría comercial como «computadoras», «automóviles», «bienes inmuebles», etc.)
1. Táctica
1. Unidad o marca comercial

## Ejemplo {#example}

Para un archivo de metadatos Creative, el nombre del archivo podría ser 20190115_ 0_ 2.

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
