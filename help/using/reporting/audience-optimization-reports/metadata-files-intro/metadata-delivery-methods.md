---
description: Envíe o actualice archivos de metadatos enviándolos a un directorio especial de Amazon S3 para su cuenta de Audience Manager. Consulte esta sección para obtener información sobre las rutas de entrega/directorio, los tiempos de procesamiento de los archivos y las actualizaciones.
seo-description: Envíe o actualice archivos de metadatos enviándolos a un directorio especial de Amazon S3 para su cuenta de Audience Manager. Consulte esta sección para obtener información sobre las rutas de entrega/directorio, los tiempos de procesamiento de los archivos y las actualizaciones.
seo-title: Métodos de envío para archivos de metadatos
solution: Audience Manager
title: Métodos de envío para archivos de metadatos
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: Log Files
exl-id: 6ef2a80c-2574-4446-b755-28027818b5eb
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 4%

---

# Métodos de envío para archivos de metadatos{#delivery-methods-for-metadata-files}

Envíe o actualice archivos de metadatos enviándolos a un directorio especial [!DNL Amazon S3] de su cuenta de Audience Manager. Consulte esta sección para obtener información sobre las rutas de entrega/directorio, los tiempos de procesamiento de los archivos y las actualizaciones.

>[!IMPORTANT]
>
> Póngase en contacto con su asesor de Audience Manager o con el Servicio de atención al cliente para empezar y configurar un directorio [!DNL Amazon S3] para sus archivos de metadatos.

## Ejemplo y sintaxis de ruta de entrega {#syntax}

Los datos se almacenan en un espacio de nombres independiente para cada cliente en un directorio [!DNL Amazon S3]. La ruta del archivo sigue la sintaxis que se muestra a continuación. Tenga en cuenta que los corchetes de ángulo `<>` indican un marcador de posición de variable. Los demás elementos son constantes y no cambian.

**Sintaxis:**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**Ejemplo:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

La siguiente tabla define cada uno de estos elementos en una ruta de entrega de archivos.


| Parámetro de archivo | Descripción |
---------|----------|
| `.../log_ingestion/` | Este es el inicio de la ruta de almacenamiento del directorio. Recibirá la ruta completa cuando todo esté configurado. |
| `pid=<AAM ID>` | Este par clave-valor contiene su ID de cliente de Audience Manager. |
| `dpid=<d_src>` | Este par clave-valor contiene el ID de fuente de datos transferido en una llamada de evento. El ID de la fuente de datos es el valor que vincula todo el contenido del archivo con los datos reales a los que pertenece. </br> Por ejemplo, supongamos que tiene un creativo con el ID 123 y el nombre &quot;Creativo del anunciante A&quot;. Como una llamada de evento solo pasa el ID, debe incluir &quot;Creativo del anunciante A&quot; en el archivo de metadatos. La campaña y el elemento creativo pertenecen a una fuente de datos. El ID de fuente de datos es lo que los une y nos permite asociar de forma precisa el contenido del archivo a un ID enviado en una llamada de evento. Consulte [Cómo determinan los ID de llamadas de evento los nombres de archivo, los contenidos y las rutas de envío](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names). |
| `<yyyymmdd_0_child ID>` | Este es el nombre del archivo. Consulte [Convenciones de nomenclatura para archivos de metadatos](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). |

## Tiempos y actualizaciones de procesamiento de archivos {#processing-times}

Los archivos de metadatos se procesan cuatro veces al día, a intervalos regulares.

Para actualizar los registros de metadatos, envíe un archivo que contenga información nueva. No es necesario que envíe actualizaciones completas cada vez.
