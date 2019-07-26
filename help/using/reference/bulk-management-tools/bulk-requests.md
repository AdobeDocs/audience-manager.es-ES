---
description: Una solicitud masiva devuelve datos que puede utilizar con los distintos encabezados en las hojas de cálculo Actualizar, Crear, Estimar y Eliminar.
seo-description: Una solicitud masiva devuelve datos que puede utilizar con los distintos encabezados en las hojas de cálculo Actualizar, Crear, Estimar y Eliminar.
seo-title: Solicitudes masivas
solution: Audience Manager
title: Solicitudes masivas
uuid: 0192 d 26 a -4 cea -4 e 12-9 fea -388 b 92 b 382 f 1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Requests{#bulk-requests}

Una solicitud masiva devuelve datos que puede utilizar con los distintos encabezados en las hojas de cálculo Actualizar, Crear, Estimar y Eliminar.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]*No* se admite [!DNL Audience Manager]en. Esta herramienta se proporciona para su comodidad y solo como cortesía. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Los permisos de grupo RBAC](../../features/administration/administration-overview.md) asignados en [!DNL Audience Manager] la interfaz de usuario se aceptan en [!UICONTROL Bulk Management Tools]la.

The [!UICONTROL Request] worksheet does not have its own set of column headers and you don't need to copy IDs to any of the columns. sino que devuelve datos basados en el botón de acción que se hace clic en la barra de herramientas. Además, una función opcional de informes devuelve un recuento de frecuencia para los píxeles activados y el recuento de usuarios únicos para varios intervalos de tiempo fijo.

To make bulk requests, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Request]** tab.
2. En la barra de herramientas situada en la parte superior de la hoja de cálculo, haga clic en un botón de solicitud correspondiente a los datos con los que desee trabajar. Puede solicitar:

   * ID del proveedor de datos
   * Señales derivadas
   * Asignaciones de destino
   * Características basadas en reglas y en variables
   * Segmentos
   * ID de carpetas de segmentos y características
   [!DNL Audience Manager] La API escribe datos masivos en la [!UICONTROL Request] hoja de cálculo.

>[!NOTE]
>
>In your results, the `createTime` and `updateTime` columns return data in exponential notation. Las marcas de fecha y hora subyacentes se registran en UNIX UTC. Actualmente, la hoja de cálculo no puede devolver marcas de fecha y hora en formato legible.

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
