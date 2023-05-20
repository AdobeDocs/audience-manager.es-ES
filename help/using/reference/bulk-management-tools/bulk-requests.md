---
description: Una solicitud masiva devuelve datos que puede utilizar con los diferentes encabezados de las hojas de cálculo de Actualizar, Crear, Estimar y Eliminar.
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: Solicitudes masivas
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 2%

---

# Solicitudes masivas{#bulk-requests}

Una solicitud masiva devuelve datos que puede utilizar con los diferentes encabezados de las hojas de cálculo de Actualizar, Crear, Estimar y Eliminar.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[Permisos de grupo de RBAC](../../features/administration/administration-overview.md) asignado en el [!DNL Audience Manager] Las IU se respetan en la [!UICONTROL Bulk Management Tools].

El [!UICONTROL Request] La hoja de cálculo no tiene su propio conjunto de encabezados de columna y no es necesario copiar los ID en ninguna de las columnas. En su lugar, devuelve datos basados en el botón de acción en el que haga clic en la barra de herramientas. Además, una función opcional de creación de informes devuelve un recuento de frecuencia para los disparos de píxeles y un recuento de usuario único para varios intervalos de tiempo fijos.

Para realizar solicitudes masivas, abra el [!UICONTROL Bulk Management Tools] hoja de cálculo y:

1. Haga clic en **[!UICONTROL Request]** pestaña.
2. En la barra de herramientas situada en la parte superior de la hoja de cálculo, haga clic en el botón de solicitud correspondiente a los datos con los que desea trabajar. Puede solicitar:

   * Modelos algorítmicos
   * Fuentes de datos
   * Señales derivadas
   * Asignaciones de destino
   * Características algorítmicas, basadas en reglas e integradas
   * Segmentos 
   * ID de carpetas de rasgos y segmentos

   El [!DNL Audience Manager] La API escribe datos en bloque en [!UICONTROL Request] hoja de cálculo.

>[!NOTE]
>
>En sus resultados, la variable `createTime` y `updateTime` las columnas devuelven datos en notación exponencial. Las marcas de fecha y hora subyacentes se registran en la hora UNIX UTC. Actualmente, la hoja de cálculo no puede devolver marcas de fecha y hora en un formato legible.

Si la actualización masiva devuelve un error o falla, consulte [Solución de problemas para herramientas de administración masiva](../../reference/bulk-management-tools/bulk-troubleshooting.md).
