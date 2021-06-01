---
description: Una solicitud masiva devuelve datos que puede utilizar con los diferentes encabezados de las hojas de cálculo de actualización, creación, estimación y eliminación.
seo-description: Una solicitud masiva devuelve datos que puede utilizar con los diferentes encabezados de las hojas de cálculo de actualización, creación, estimación y eliminación.
seo-title: Solicitudes masivas
solution: Audience Manager
title: Solicitudes masivas
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 3%

---

# Solicitudes masivas{#bulk-requests}

Una solicitud masiva devuelve datos que puede utilizar con los diferentes encabezados de las hojas de cálculo de actualización, creación, estimación y eliminación.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[Los ](../../features/administration/administration-overview.md) permisos de grupo RBAC asignados en la  [!DNL Audience Manager] interfaz de usuario se respetan en  [!UICONTROL Bulk Management Tools].

La hoja de cálculo [!UICONTROL Request] no tiene su propio conjunto de encabezados de columna y no es necesario copiar los ID en ninguna de las columnas. En su lugar, devuelve datos en función del botón de acción en el que haga clic en la barra de herramientas. Además, una función opcional de sistema de informes devuelve un recuento de frecuencia para los incendios de píxeles y un recuento de usuarios único durante varios intervalos de tiempo fijos.

Para realizar solicitudes masivas, abra la hoja de cálculo [!UICONTROL Bulk Management Tools] y:

1. Haga clic en la pestaña **[!UICONTROL Request]**.
2. En la barra de herramientas de la parte superior de la hoja de cálculo, haga clic en un botón de solicitud correspondiente a los datos con los que desee trabajar. Puede solicitar:

   * Modelos algorítmicos
   * Fuentes de datos
   * Señales derivadas
   * Asignaciones de destino
   * Características algorítmicas, basadas en reglas y integradas
   * Segmentos 
   * ID de carpetas de segmentos y características

   La API [!DNL Audience Manager] escribe datos masivos en la hoja de cálculo [!UICONTROL Request].

>[!NOTE]
>
>En los resultados, las columnas `createTime` y `updateTime` devuelven datos en notación exponencial. Las marcas de fecha y hora subyacentes se registran en la hora UNIX UTC. Actualmente, la hoja de cálculo no puede devolver marcas de fecha y hora en un formato legible.

Si la actualización masiva devuelve un error o falla, consulte [Solución de problemas para herramientas de administración masiva](../../reference/bulk-management-tools/bulk-troubleshooting.md).
