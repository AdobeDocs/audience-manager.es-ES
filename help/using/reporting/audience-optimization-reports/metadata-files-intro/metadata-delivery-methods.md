---
description: Envíe o actualice archivos de metadatos enviándolos a un directorio especial de Amazon S3 para su cuenta de Audience Manager. Consulte esta sección para obtener información sobre rutas de envío/directorio, tiempos de procesamiento de archivos y actualizaciones.
seo-description: Envíe o actualice archivos de metadatos enviándolos a un directorio especial de Amazon S3 para su cuenta de Audience Manager. Consulte esta sección para obtener información sobre rutas de envío/directorio, tiempos de procesamiento de archivos y actualizaciones.
seo-title: Métodos de envío para archivos de metadatos
solution: Audience Manager
title: Métodos de envío para archivos de metadatos
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: log files
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 4%

---


# Métodos de envío para archivos de metadatos{#delivery-methods-for-metadata-files}

Envíe o actualice archivos de metadatos enviándolos a un directorio especial [!DNL Amazon S3] de su cuenta de Audience Manager. Consulte esta sección para obtener información sobre rutas de envío/directorio, tiempos de procesamiento de archivos y actualizaciones.

>[!IMPORTANT]
>
> Póngase en contacto con el consultor del Audience Manager o con el Servicio de atención al cliente para comenzar y configurar un directorio [!DNL Amazon S3] para sus archivos de metadatos.

## Ejemplo y sintaxis de ruta de envío {#syntax}

Los datos se almacenan en una Área de nombres separada para cada cliente en un directorio [!DNL Amazon S3]. La ruta del archivo sigue la sintaxis que se muestra a continuación. Tenga en cuenta que los corchetes angulares `<>` indican un marcador de posición de variable. Los demás elementos son constantes y no cambian.

**Sintaxis:**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**Ejemplo:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

La siguiente tabla define cada uno de estos elementos en una ruta de envío de archivos.


| Parámetro de archivo | Descripción |
---------|----------|
| `.../log_ingestion/` | Este es el inicio de la ruta de almacenamiento del directorio. Recibirás la ruta completa cuando todo esté configurado. |
| `pid=<AAM ID>` | Este par clave-valor contiene el ID de cliente del Audience Manager. |
| `dpid=<d_src>` | Este par clave-valor contiene la ID de la fuente de datos que se pasa en una llamada de evento. El ID del origen de datos es el valor que vincula todo el contenido del archivo con los datos reales a los que pertenece. </br> Por ejemplo, supongamos que tiene un elemento creativo con el ID 123 y el nombre &quot;Advertiser Creative A&quot;. Como una llamada de evento solo pasa en el ID, debe incluir &quot;Advertiser Creative A&quot; en el archivo de metadatos. La campaña y el elemento creativo pertenecen a un origen de datos. El ID de la fuente de datos es lo que los une y nos permite asociar con precisión el contenido del archivo a un ID enviado en una llamada de evento. Consulte [Cómo los ID de llamadas de Evento determinan nombres de archivo, contenido y rutas de Envío](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names). |
| `<yyyymmdd_0_child ID>` | Es el nombre del archivo. Consulte [Convenciones de nombres para archivos de metadatos](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). |

## Tiempos y actualizaciones de procesamiento de archivos {#processing-times}

Los archivos de metadatos se procesan cuatro veces al día, a intervalos regulares.

Para actualizar los registros de metadatos, solo tiene que enviar un archivo que contenga información nueva. No es necesario que envíe actualizaciones completas cada vez.
