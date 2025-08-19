---
description: Una solicitud masiva devuelve datos que puede utilizar con los diferentes encabezados de las hojas de cálculo de Actualizar, Crear, Estimar y Eliminar.
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: Solicitudes masivas
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# Solicitudes masivas{#bulk-requests}

Una solicitud masiva devuelve datos que puede utilizar con los diferentes encabezados de las hojas de cálculo de Actualizar, Crear, Estimar y Eliminar.

>[!IMPORTANT]
>
>Las herramientas de administración masiva no son una oferta de Adobe oficialmente compatible. La resolución de problemas y la asistencia técnica a través del Servicio de atención al cliente se gestionarán caso por caso.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[Los permisos de grupo RBAC](../../features/administration/administration-overview.md) asignados en la interfaz de usuario de [!DNL Audience Manager] se respetan en [!UICONTROL Bulk Management Tools].

La hoja de cálculo [!UICONTROL Request] no tiene su propio conjunto de encabezados de columna y no es necesario copiar los identificadores en ninguna de las columnas. En su lugar, devuelve datos basados en el botón de acción en el que haga clic en la barra de herramientas. Además, una función opcional de creación de informes devuelve un recuento de frecuencia para los disparos de píxeles y un recuento de usuario único para varios intervalos de tiempo fijos.

Para realizar solicitudes masivas, abra la hoja de cálculo [!UICONTROL Bulk Management Tools] y:

1. Haga clic en la ficha **[!UICONTROL Request]**.
2. En la barra de herramientas situada en la parte superior de la hoja de cálculo, haga clic en el botón de solicitud correspondiente a los datos con los que desea trabajar. Puede solicitar:

   * Modelos algorítmicos
   * Fuentes de datos
   * Señales derivadas
   * Asignaciones de destino
   * Características algorítmicas, basadas en reglas e integradas
   * Segmentos
   * ID de carpetas de rasgos y segmentos

   La API [!DNL Audience Manager] escribe datos en bloque en la hoja de cálculo [!UICONTROL Request].

>[!NOTE]
>
>En sus resultados, las columnas `createTime` y `updateTime` devuelven datos en notación exponencial. Las marcas de fecha y hora subyacentes se registran en la hora UNIX UTC. Actualmente, la hoja de cálculo no puede devolver marcas de fecha y hora en un formato legible.

Si su actualización masiva devuelve un error o falla, consulte [Solución de problemas para herramientas de administración masiva](../../reference/bulk-management-tools/bulk-troubleshooting.md).
