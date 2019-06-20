---
description: La eliminación masiva permite quitar varios segmentos, características, carpetas, señales derivadas y destinos con una sola operación. Siga estas instrucciones para crear una solicitud de eliminación masiva.
seo-description: La eliminación masiva permite quitar varios segmentos, características, carpetas, señales derivadas y destinos con una sola operación. Siga estas instrucciones para crear una solicitud de eliminación masiva.
seo-title: Eliminación masiva
solution: Audience Manager
title: Eliminación masiva
uuid: 679 cde 46-09 fb -45 c 6-b 84 d -47 e 00 e 0 e 7 c 0 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Delete{#bulk-delete}

La eliminación masiva permite quitar varios segmentos, características, carpetas, señales derivadas y destinos con una sola operación. Siga estas instrucciones para crear una solicitud de eliminación masiva.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]*No* se admite [!DNL Audience Manager]en. Esta herramienta se proporciona para su comodidad y solo como cortesía. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Los permisos de grupo RBAC](../../features/administration/administration-overview.md) asignados en [!DNL Audience Manager] la interfaz de usuario se aceptan en [!UICONTROL Bulk Management Tools]la.

>[!NOTE]
>
>Una eliminación masiva para asignaciones de destino fallará si tiene segmentos asignados al destino. Elimine los segmentos de ese destino en la interfaz de usuario antes de intentar eliminar destinos por lotes. Además, las carpetas de características y segmentos deben estar vacías para poder eliminarlas.

To delete multiple items, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the create headers for the item you want to add.
2. Click the **[!UICONTROL Delete]** tab.
3. Pegue los encabezados de eliminación en la primera fila de la hoja de cálculo de actualizaciones.
4. Pegue o escriba los ID de los objetos que desee eliminar en la columna debajo del encabezado.
5. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

   The worksheet creates a [!UICONTROL Results] column. The [!UICONTROL Results] column returns a message that indicates if the item has been deleted or an error message.
Antes de introducir datos, la hoja de cálculo de actualización masiva debería tener un aspecto similar al siguiente:

![](assets/delete.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
