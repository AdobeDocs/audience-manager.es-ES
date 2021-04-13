---
description: Dé formato al contenido del archivo de metadatos del Audience Optimization según estas especificaciones.
seo-description: Dé formato al contenido del archivo de metadatos del Audience Optimization según estas especificaciones.
seo-title: Formato de contenido para archivos de metadatos
solution: Audience Manager
title: Formato de contenido para archivos de metadatos
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
feature: Archivos de registro
exl-id: 1aed39f4-f893-4f25-b041-e198895e338a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 5%

---

# Formato de contenido para archivos de metadatos{#content-format-for-metadata-files}

Dé formato al contenido del archivo de metadatos del Audience Optimization según estas especificaciones.

## Sintaxis {#syntax}

La siguiente sintaxis define la estructura del contenido bien formado de un archivo de metadatos. Tenga en cuenta que la *cursiva* indica un marcador de posición de variable.

**Sintaxis:**  *ID de contenido*  |  *nombre* |  *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

La tercera columna **-1** es técnicamente el ID principal, que es un campo heredado. El valor siempre debe establecerse como **-1**.

>[!NOTE]
>
>Tenga en cuenta que se necesita un archivo de metadatos por dimensión, por lo que se esperan varios archivos de metadatos en el bloque. Las dimensiones se enumeran en el artículo [Convenciones de nomenclatura para el archivo de metadatos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Separar entradas de archivo con ^a (control-A o ASCII 001)**

Utilice `^a` (control-A o ASCII 001) para separar el contenido de los archivos de metadatos. Como estos son caracteres no imprimibles, el ejemplo de sintaxis anterior muestra una barra vertical &quot;|&quot; únicamente con fines de visualización.

Si es necesario, puede descargar el archivo de ejemplo: [20181105_0_1](assets/20181105_0_1.zip). Descomprima y edite en el editor que elija y ajuste según el contenido real de los metadatos, ya que ya contiene el delimitador requerido.

>[!IMPORTANT]
>
>No agregue filas de encabezado a archivos de metadatos.

## Ejemplos {#examples}

Veamos cómo estructuraría el contenido en un archivo de metadatos. Parte de esta estructura depende de la dimensión. Las dimensiones se enumeran en el artículo [Convenciones de nomenclatura para el archivo de metadatos](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campaign**

En este ejemplo, el título del archivo es 20180921_0_1 y las tres columnas del archivo son: ID de campaña, nombre e ID principal.

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**Creative**

En este ejemplo, el título del archivo es 20180827_0_2 y las tres columnas del archivo son: ID creativo, nombre e ID principal.

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**Sitio**

En este ejemplo, el título del archivo es 20180921_0_5 y las tres columnas del archivo son: ID del sitio, nombre e ID principal.

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
