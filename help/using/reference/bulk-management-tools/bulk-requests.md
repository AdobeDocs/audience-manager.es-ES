---
description: Una solicitud masiva devuelve datos que puede utilizar con los diferentes encabezados de las hojas de cálculo de actualización, creación, estimación y eliminación.
seo-description: Una solicitud masiva devuelve datos que puede utilizar con los diferentes encabezados de las hojas de cálculo de actualización, creación, estimación y eliminación.
seo-title: Solicitudes masivas
solution: Audience Manager
title: Solicitudes masivas
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
translation-type: tm+mt
source-git-commit: 8cc3d9d629536c48b7013ffede16c0b112704c89

---


# Solicitudes masivas{#bulk-requests}

Una solicitud masiva devuelve datos que puede utilizar con los diferentes encabezados de las hojas de cálculo de actualización, creación, estimación y eliminación.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[Los permisos](../../features/administration/administration-overview.md) de grupo RBAC asignados en la [!DNL Audience Manager] interfaz de usuario se respetan en la [!UICONTROL Bulk Management Tools].

La hoja de cálculo no tiene su propio conjunto de encabezados de columna y no es necesario copiar los ID en ninguna de las columnas. [!UICONTROL Request] En su lugar, devuelve datos basados en el botón de acción en el que se hace clic en la barra de herramientas. Además, una función de informes opcional devuelve un recuento de frecuencia para los incendios de píxeles y un recuento de usuarios únicos durante varios intervalos de tiempo fijos.

Para realizar solicitudes masivas, abra la [!UICONTROL Bulk Management Tools] hoja de cálculo y:

1. Click the **[!UICONTROL Request]** tab.
2. En la barra de herramientas situada en la parte superior de la hoja de cálculo, haga clic en un botón de solicitud correspondiente a los datos con los que desee trabajar. Puede solicitar:

   * Modelos algorítmicos
   * Fuentes de datos
   * Señales derivadas
   * Asignaciones de destino
   * Características algorítmicas, basadas en reglas y integradas
   * Segmentos
   * ID de carpeta de segmentos y características
   La [!DNL Audience Manager] API vuelve a escribir datos masivos en la [!UICONTROL Request] hoja de cálculo.

>[!NOTE]
>
>En los resultados, las `createTime` columnas y `updateTime` devuelven datos en notación exponencial. Las marcas de fecha y hora subyacentes se registran en la hora UNIX UTC. Actualmente, la hoja de cálculo no puede devolver marcas de fecha y hora en un formato legible.

Si la actualización masiva devuelve un error o un error, consulte [Resolución de problemas de las herramientas](../../reference/bulk-management-tools/bulk-troubleshooting.md)de administración masiva.
