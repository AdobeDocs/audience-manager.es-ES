---
description: Envíe o actualice archivos de metadatos enviándolos a un directorio especial de Amazon S3 para su cuenta de Audience Manager. Consulte esta sección para obtener información sobre las rutas de entrega/directorio, los tiempos de procesamiento de archivos y las actualizaciones.
seo-description: Send or update metadata files by sending them to a special Amazon S3 directory for your Audience Manager account. Refer to this section for information about delivery/directory paths, file processing times, and updates.
seo-title: Delivery Methods for Metadata Files
solution: Audience Manager
title: Métodos de envío para archivos de metadatos
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: Log Files
exl-id: 6ef2a80c-2574-4446-b755-28027818b5eb
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 3%

---

# Métodos de envío para archivos de metadatos{#delivery-methods-for-metadata-files}

Envíe o actualice archivos de metadatos enviándolos a un especial [!DNL Amazon S3] para su cuenta de Audience Manager. Consulte esta sección para obtener información sobre las rutas de entrega/directorio, los tiempos de procesamiento de archivos y las actualizaciones.

>[!IMPORTANT]
>
> Póngase en contacto con su asesor Audience Manager o con el Servicio de atención al cliente para comenzar y configurar una [!DNL Amazon S3] para los archivos de metadatos.

## Ejemplo y sintaxis de la ruta de envío {#syntax}

Los datos se almacenan en un área de nombres independiente para cada cliente en una [!DNL Amazon S3] directorio. La ruta del archivo sigue la sintaxis que se muestra a continuación. Nota, corchetes angulares `<>` indica un marcador de posición variable. Los demás elementos son constantes y no cambian.

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
|---------|----------|
| `.../log_ingestion/` | Este es el inicio de la ruta de almacenamiento del directorio. Recibirá la ruta de acceso completa cuando todo esté configurado. |
| `pid=<AAM ID>` | Este par clave-valor contiene su ID de cliente de Audience Manager. |
| `dpid=<d_src>` | Este par clave-valor contiene el ID de fuente de datos pasado en una llamada de evento. El ID de la fuente de datos es el valor que vincula todo el contenido del archivo con los datos reales a los que pertenece. </br> Por ejemplo, supongamos que tiene un creativo con el ID 123 y el nombre &quot;Anunciante creativo A&quot;. Como una llamada de evento solo pasa el ID, debe incluir &quot;Creativo del anunciante A&quot; en el archivo de metadatos. La campaña y el elemento creativo pertenecen a una fuente de datos. El ID de la fuente de datos es el que vincula estos datos y nos permite asociar con precisión el contenido del archivo a un ID enviado en una llamada de evento. Consulte [Cómo determinan los ID de llamada de evento los nombres de archivo, el contenido y las rutas de envío](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names). |
| `<yyyymmdd_0_child ID>` | Este es el nombre de archivo. Consulte [Convenciones de nomenclatura para archivos de metadatos](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). |

## Tiempos y actualizaciones de procesamiento de archivos {#processing-times}

Los archivos de metadatos se procesan cuatro veces al día, a intervalos regulares.

Para actualizar los registros de metadatos, envíe un archivo que contenga información nueva. No es necesario que envíe actualizaciones completas cada vez.
