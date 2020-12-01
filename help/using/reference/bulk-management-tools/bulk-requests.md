---
description: Una solicitud masiva devuelve datos que puede utilizar con los diferentes encabezados de las hojas de cálculo de actualización, creación, estimación y eliminación.
seo-description: Una solicitud masiva devuelve datos que puede utilizar con los diferentes encabezados de las hojas de cálculo de actualización, creación, estimación y eliminación.
seo-title: Solicitudes masivas
solution: Audience Manager
title: Solicitudes masivas
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 2%

---


# Solicitudes masivas{#bulk-requests}

Una solicitud masiva devuelve datos que puede utilizar con los diferentes encabezados de las hojas de cálculo de actualización, creación, estimación y eliminación.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[Los ](../../features/administration/administration-overview.md) permisos de grupo RBAC asignados en la  [!DNL Audience Manager] interfaz de usuario se respetan en la  [!UICONTROL Bulk Management Tools].

La hoja de cálculo [!UICONTROL Request] no tiene su propio conjunto de encabezados de columna y no es necesario copiar los ID en ninguna de las columnas. En su lugar, devuelve datos basados en el botón de acción en el que se hace clic en la barra de herramientas. Además, una función de sistema de informes opcional devuelve un recuento de frecuencia para los incendios de píxeles y un recuento de usuarios único para varios intervalos de tiempo fijos.

Para realizar solicitudes masivas, abra la hoja de cálculo [!UICONTROL Bulk Management Tools] y:

1. Haga clic en la ficha **[!UICONTROL Request]**.
2. En la barra de herramientas situada en la parte superior de la hoja de cálculo, haga clic en un botón de solicitud correspondiente a los datos con los que desee trabajar. Puede solicitar:

   * Modelos algorítmicos
   * Fuentes de datos
   * Señales derivadas
   * Asignaciones de destino
   * Características algorítmicas, basadas en reglas y integradas
   * Segmentos 
   * ID de carpeta de segmentos y características

   La API [!DNL Audience Manager] devuelve los datos masivos a la hoja de cálculo [!UICONTROL Request].

>[!NOTE]
>
>En los resultados, las columnas `createTime` y `updateTime` devuelven datos en notación exponencial. Las marcas de fecha y hora subyacentes se registran en la hora UNIX UTC. Actualmente, la hoja de cálculo no puede devolver marcas de fecha y hora en un formato legible.

Si la actualización masiva devuelve un error o falla, consulte [Solución de problemas para las herramientas de administración masiva](../../reference/bulk-management-tools/bulk-troubleshooting.md).
