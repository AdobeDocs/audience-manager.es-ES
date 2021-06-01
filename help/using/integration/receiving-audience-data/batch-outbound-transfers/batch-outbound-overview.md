---
description: El Audience Manager envía datos por lotes a proveedores de contenido de terceros según estas especificaciones.
seo-description: Adobe Audience Manager (AAM) envía datos por lotes a proveedores de contenido de terceros según estas especificaciones.
seo-title: Transferencias de datos de salida por lotes en Adobe Audience Manager (AAM)
title: 'Transferencias de datos de salida por lotes '
feature: Transferencias de datos de salida
exl-id: 1fdcc971-3a71-4033-8501-ef3d1f1f0f47
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 17%

---

# Transferencias de datos de salida por lotes 

El Audience Manager envía datos por lotes a proveedores de contenido de terceros según estas especificaciones.

* [Nombre del archivo de datos de salida: sintaxis y ejemplos](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)

   Describe los campos, la sintaxis y las convenciones requeridos que se usan para asignar un nombre a un archivo de datos de salida.

* [Configuración de la integración de transferencia de datos por lotes](batch-server-configuration.md)

   Describe los métodos a través de los cuales puede configurar la integración de transferencia de datos por lotes.

* [Archivos de transferencia y control para transferencias de archivos de registro](/help/using/integration/receiving-audience-data/batch-outbound-transfers/transfer-control-files.md)

   Los archivos de control de transferencia (.info) proporcionan información de metadatos sobre las transferencias de archivos para que los socios puedan comprobar que el Audience Manager ha gestionado correctamente las transferencias de archivos.

* [Macros de plantillas de salida](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)

   Enumera las macros que puede utilizar para crear plantillas salientes. Estas incluyen macros de nombre de archivo, macros de encabezado y macros de contenido.

* [Ejemplos de macros de salida](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

   Ejemplos de cómo se utilizan algunas de las macros comunes para crear plantillas de archivo salientes.

* [Usar los permisos de bloque entre cuentas de Amazon S3 para los archivos salientes](/help/using/integration/receiving-audience-data/batch-outbound-transfers/authorize-s3-cross-bucket.md)

   El proceso de transferencia de datos de salida para los clientes que utilizan Amazon Simple Storage Service (Amazon S3) requiere que solicitemos su clave de acceso y clave secreta de Amazon S3 para entregar los archivos de datos de salida a su bucket.
