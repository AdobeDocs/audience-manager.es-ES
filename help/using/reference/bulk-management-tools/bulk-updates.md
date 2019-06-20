---
description: Una actualización masiva permite editar varios segmentos, características y elementos de segmentos o características en una sola operación. Siga estas instrucciones para realizar actualizaciones masivas.
keywords: baaam
seo-description: Una actualización masiva permite editar varios segmentos, características y elementos de segmentos o características en una sola operación. Siga estas instrucciones para realizar actualizaciones masivas.
seo-title: Actualizaciones masivas
solution: Audience Manager
title: Actualizaciones masivas
uuid: 22 f 1 badd-a 274-4 d 3 e -9957-a 24 bf 8 c 1 d 0 dc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Updates{#bulk-updates}

Una actualización masiva permite editar varios segmentos, características y elementos de segmentos o características en una sola operación. Siga estas instrucciones para realizar actualizaciones masivas.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]*No* se admite [!DNL Audience Manager]en. Esta herramienta se proporciona para su comodidad y solo como cortesía. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Los permisos de grupo RBAC](../../features/administration/administration-overview.md) asignados en [!DNL Audience Manager] la interfaz de usuario se aceptan en [!UICONTROL Bulk Management Tools]la.

To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the update headers for the item you want to edit.
1. Click the **[!UICONTROL Update]** tab.
1. Pegue los encabezados de actualización en la primera fila de la hoja de cálculo de actualizaciones. Tenga en cuenta lo siguiente:

   * Al actualizar una carpeta, se requieren todos los encabezados.
   * Al actualizar segmentos o características, solo se necesita el ID de segmento (SID) y el elemento de encabezado que se debe cambiar. Elimine los encabezados no utilizados.

1. Pegue o escriba los datos que desee cambiar en una columna correspondiente según la etiqueta del encabezado.
1. En la barra de herramientas de la hoja de cálculo, haga clic en un botón de actualización que coincida con el elemento que está actualizando.
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

   The worksheet creates a [!UICONTROL Results] column. The [!UICONTROL Results] column returns the JSON response for a successful operation. See the [REST APIs](../../api/rest-api-main/rest-api-main.md) for examples. Antes de introducir datos, la hoja de cálculo de actualización masiva debería tener un aspecto similar al siguiente:

![](assets/update.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
