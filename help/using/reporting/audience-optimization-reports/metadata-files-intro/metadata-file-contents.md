---
description: Dé formato al contenido del archivo de metadatos de Optimización de audiencias conforme a estas especificaciones.
seo-description: Dé formato al contenido del archivo de metadatos de Optimización de audiencias conforme a estas especificaciones.
seo-title: Formato de contenido para archivos de metadatos
solution: Audience Manager
title: Formato de contenido para archivos de metadatos
uuid: 9 ba 44738-3 e 17-40 c 7-9 e 8 c -5 abd 8361 e 16 d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Content Format for Metadata Files{#content-format-for-metadata-files}

Dé formato al contenido del archivo de metadatos de Optimización de audiencias conforme a estas especificaciones.

## Sintaxis {#syntax}

La siguiente sintaxis define la estructura de contenido bien formado en un archivo de metadatos. Note, *italics* indicates a variable placeholder.

**Sintaxis:***ID de contenido* | *name* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

The third column **-1** is technically the Parent ID, which is a legacy field. The value should always be set as **-1**.

>[!NOTE]
>
>Tenga en cuenta que se necesita un archivo de metadatos por dimensión, por lo que se esperan varios archivos de metadatos en el bloque. The dimensions are listed in the article [Naming Conventions for Metadata File](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Entradas de archivo independientes con ^ a (control-A o ASCII 001)**

Use `^a` (control-A or ASCII 001) to separate content in your metadata files. Dado que estos caracteres no se imprimen, el ejemplo de sintaxis anterior muestra una barra vertical &quot;|&quot; solo para fines de visualización.

If needed, you may download the example file - [20181105_0_1](assets/20181105_0_1.zip). Descomprima y edite en el editor de opciones y ajuste según el contenido de metadatos real, ya que ya contiene el delimitador requerido.

>[!IMPORTANT]
>
>No agregue filas de encabezado a los archivos de metadatos.

## Ejemplos {#examples}

Veamos cómo estructuraría el contenido en un archivo de metadatos. Parte de esta estructura depende de la dimensión. The dimensions are listed in the article [Naming Conventions for Metadata File](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campaign**

En este ejemplo, el título del archivo es 20180921_ 0_ 1 y las tres columnas del archivo son: ID de campaña, nombre y ID principal.

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**Elemento creativo**

En este ejemplo, el título del archivo es 20180827_ 0_ 2 y las tres columnas del archivo son: ID creativos, Nombre y ID principal.

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**Sitio**

En este ejemplo, el título del archivo es 20180921_ 0_ 5 y las tres columnas del archivo son: ID del sitio, Nombre y ID principal.

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
