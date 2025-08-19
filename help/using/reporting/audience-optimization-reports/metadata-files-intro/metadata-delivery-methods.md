---
description: Envíe o actualice metadatos archivos enviándolos a un directorio Amazon S3 especial para su cuenta Audience Manager. Consulte esta sección para obtener información sobre rutas de directorio/envío, tiempos de procesamiento de archivos y actualizaciones.
seo-description: Send or update metadata files by sending them to a special Amazon S3 directory for your Audience Manager account. Refer to this section for information about delivery/directory paths, file processing times, and updates.
seo-title: Delivery Methods for Metadata Files
solution: Audience Manager
title: Métodos de entrega de metadatos Archivos
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: Log Files
exl-id: 6ef2a80c-2574-4446-b755-28027818b5eb
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---

# Métodos de entrega de metadatos Archivos{#delivery-methods-for-metadata-files}

Envíe o actualice metadatos archivos enviándolos a un directorio especial [!DNL Amazon S3] para su cuenta Audience Manager. Consulte esta sección para obtener información sobre rutas de directorio/envío, tiempos de procesamiento de archivos y actualizaciones.

>[!IMPORTANT]
>
> Póngase en contacto con su consultor Audience Manager o con el Servicio de atención al cliente para empezar y configurar un [!DNL Amazon S3] directorio para sus archivos metadatos.

## Sintaxis y ejemplo de ruta de entrega {#syntax}

Los datos se almacenan en un espacio de nombres independiente para cada cliente en un [!DNL Amazon S3] directorio. La ruta del archivo sigue la sintaxis que se muestra a continuación. Tenga en cuenta que los corchetes angulares `<>` indican un marcador de posición variable. Los otros elementos son constantes y no cambian.

**Sintaxis:**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**Ejemplo:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

La tabla siguiente define cada uno de estos elementos en una ruta de envío de archivo.


| Parámetro Archivo | Descripción |
|---------|----------|
| `.../log_ingestion/` | Este es el inicio del directorio almacenamiento ruta. Recibirá la ruta completa cuando todo esté configurado. |
| `pid=<AAM ID>` | Este par clave-valor contiene su Audience Manager ID de cliente. |
| `dpid=<d_src>` | Este par clave-valor contiene el ID de fuente de datos transferido en una llamada de evento. El ID de fuente de datos es el valor que une todo el contenido del archivo a los datos reales a los que pertenece. </br> Por ejemplo, supongamos que tiene un creativa con el ID 123 y el nombre &quot;Anunciante Creative A&quot;. Como una llamada de evento solo pasa el ID, debe incluir &quot;Anunciante Creative A&quot; en el archivo metadatos. El campaña y el creativa pertenecen a un fuente de datos. El ID fuente de datos es lo que los une y nos permite asociar con precisión el contenido del archivo a un ID enviado en una llamada evento. Consulte [cómo los ID de llamadas de eventos determinan Archivo nombres, contenidos y rutas de envío.](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names) |
| `<yyyymmdd_0_child ID>` | Este es el nombre del archivo. Consulte [Convenciones de nomenclatura para Archivos](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md) de metadatos. |

## Tiempos de procesamiento y actualizaciones de Archivo {#processing-times}

Los archivos de metadatos se procesan cuatro veces al día, a intervalos regulares.

Para actualizar sus registros de metadatos, simplemente envíe un archivo que contenga nueva información. No es necesario que envíe actualizaciones completas cada vez.
