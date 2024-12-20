---
description: La eliminación en lote permite eliminar varios segmentos, rasgos, carpetas, señales derivadas, fuentes de datos, modelos y destinos con una sola operación. Siga estas instrucciones para realizar una solicitud de eliminación masiva.
seo-description: Bulk delete lets you remove multiple segments, traits, folders, derived signals, data sources, models, and destinations with a single operation. Follow these instructions to make a bulk delete request.
seo-title: Bulk Delete
solution: Audience Manager
title: Eliminación masiva
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: BAAAM
exl-id: 3ff530dd-66d0-4dd3-a6e6-afe4a9cb5ba4
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 0%

---

# Eliminación masiva{#bulk-delete}

La eliminación en lote permite eliminar varios segmentos, rasgos, carpetas, señales derivadas, fuentes de datos, modelos y destinos con una sola operación. Siga estas instrucciones para realizar una solicitud de eliminación masiva.

>[!IMPORTANT]
>
>Las herramientas de administración masiva no son una oferta de Adobe oficialmente admitida. La resolución de problemas y la asistencia técnica a través del Servicio de atención al cliente se gestionarán caso por caso.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[Los permisos de grupo RBAC](../../features/administration/administration-overview.md) asignados en la interfaz de usuario de [!DNL Audience Manager] se respetan en [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>Si tiene segmentos asignados al destino, se producirá un error en la eliminación masiva de asignaciones de destino. Elimine los segmentos de ese destino en la interfaz de usuario antes de intentar eliminar destinos por lotes. Además, las carpetas de rasgos y segmentos deben estar vacías para poder eliminarlas.

Para eliminar varios elementos, abra la hoja de cálculo [!UICONTROL Bulk Management Tools] y:

1. Haga clic en la ficha **[!UICONTROL Headers]** y copie los encabezados de creación del elemento que desee agregar.
2. Haga clic en la ficha **[!UICONTROL Delete]**.
3. Pegue los encabezados de eliminación en la primera fila de la hoja de cálculo de actualización.
4. Pegue o escriba los identificadores de los objetos que desea eliminar en la columna situada debajo del encabezado.
5. Proporcione la [información de inicio de sesión](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) necesaria y haga clic en **[!UICONTROL Submit]**.

   La hoja de cálculo crea una columna [!UICONTROL Results]. La columna [!UICONTROL Results] devuelve un mensaje que indica si el elemento se ha eliminado o un mensaje de error.
Antes de introducir datos, la hoja de cálculo de actualización masiva debe tener un aspecto similar al siguiente:

![](assets/delete.png)

Si su actualización masiva devuelve un error o falla, consulte [Solución de problemas para herramientas de administración masiva](../../reference/bulk-management-tools/bulk-troubleshooting.md).
