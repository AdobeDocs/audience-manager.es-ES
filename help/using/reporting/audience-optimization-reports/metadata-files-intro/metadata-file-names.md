---
description: Asigne un nombre al archivo de metadatos de Audience Optimization según estas especificaciones.
seo-description: Asigne un nombre al archivo de metadatos de Audience Optimization según estas especificaciones.
seo-title: Convenciones de nomenclatura para archivos de metadatos
solution: Audience Manager
title: Convenciones de nomenclatura para archivos de metadatos
uuid: cab55b2a-2e54-45f6-aeea-3735b911f821
feature: log files
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 10%

---


# Convenciones de nomenclatura para archivos de metadatos{#naming-conventions-for-metadata-files}

Asigne un nombre al archivo de metadatos de Audience Optimization según estas especificaciones.

## Sintaxis y Categorías de ID {#syntax}

La siguiente sintaxis define la estructura de un nombre de archivo de metadatos bien formado. Nota: *cursiva* indica un marcador de posición de variable. Los demás elementos son constantes y no cambian.

**Sintaxis:** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*No* utilice extensiones de archivo en los archivos de metadatos (.txt u otros).

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* El componente medio **0** es técnicamente el ID principal, que es un campo heredado. El valor siempre debe establecerse como **0**.
* El ID secundario puede tener un valor entre 1 y 10, según la dimensión. Vea lo siguiente:

## Dimensiones de ID secundarias {#child-dimension}

En el nombre del archivo de metadatos, el ID secundario es un identificador que clasifica el tipo de datos de un archivo y lo coloca en una jerarquía. Puede etiquetar el ID secundario en el nombre del archivo con los siguientes ID de categoría:

1. Campaign
1. Creative
1. Ubicación
1. Exchange
1. Sitio
1. Anunciante (si utiliza códigos de integración en una [fuente de datos](../../../features/manage-datasources.md#details))
1. Orden de inserción (E/S)
1. Vertical (es decir, una industria o categoría empresarial específica como &quot;computadoras&quot;, &quot;automóviles&quot;, &quot;bienes raíces&quot;, etc.)
1. Táctica
1. Unidad de negocio o marca

## Ejemplo {#example}

Para un archivo de metadatos de Creative, el nombre del archivo podría ser 20190115_0_2.

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
