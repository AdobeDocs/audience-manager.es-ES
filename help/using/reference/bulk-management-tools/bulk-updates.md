---
description: Una actualización masiva le permite editar varios segmentos, características, modelos, orígenes de datos y elementos de carpeta de segmento o características con una sola operación. Siga estas instrucciones para realizar actualizaciones masivas.
keywords: Baaam
seo-description: A bulk update lets you edit multiple segments, traits, models, data sources, and segment or trait folder elements in a single operation. Follow these instructions to make bulk updates.
seo-title: Bulk Updates
solution: Audience Manager
title: Actualizaciones masivas
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: BAAAM
exl-id: ef01c7d0-5af1-4db7-9859-1087c1fef684
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Actualizaciones masivas{#bulk-updates}

Una actualización masiva le permite editar varios segmentos, características, modelos, orígenes de datos y elementos de carpeta de segmento o características con una sola operación. Siga estas instrucciones para realizar actualizaciones masivas.

>[!IMPORTANT]
>
>Los Herramientas de administración masiva no son una oferta Adobe Systems que se admita oficialmente. La solución de problemas y el soporte a través del Servicio de atención al cliente se manejarán caso por caso.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[Los permisos](../../features/administration/administration-overview.md) RBAC grupo asignados en el [!DNL Audience Manager] IU se respetan en el [!UICONTROL Bulk Management Tools].

Para realizar actualizaciones masivas, abra la hoja de [!UICONTROL Bulk Management Tools] cálculo y:

1. Haga clic en el **[!UICONTROL Headers]** pestaña y copie los encabezados de actualización para el elemento que desea editar.
2. Haga clic en el **[!UICONTROL Update]** pestaña.
3. Pegar los encabezados de actualización a la primera fila de la hoja de cálculo de actualización. Tenga en cuenta lo siguiente:

   * Al actualizar una carpeta, se requieren todos los encabezados.
   * Al actualizar segmentos o características, solo se necesita el ID de segmento (SID) y el elemento de encabezado que se debe cambiar. Eliminar encabezados no utilizados.

4. Pegar o escriba los datos que desea convertir en una columna correspondiente basada en la etiqueta de encabezado.
5. En la barra de herramientas de la hoja de cálculo, haga clic en un botón de actualización que coincida con el elemento que está actualizando.
Esta acción abre el cuadro de [!UICONTROL Account Information] diálogo.

6. Proporcione la información[ de inicio de sesión necesaria ](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)y haga clic en **[!UICONTROL Submit]**.

   La hoja de cálculo crea una [!UICONTROL Results] columna. La [!UICONTROL Results] columna devuelve la respuesta JSON de una operación correcta. Consulte los ejemplos de las API[ de ](../../api/rest-api-main/rest-api-main.md)REST. Antes de introducir datos, la hoja de cálculo de actualización masiva debe tener un aspecto similar al siguiente:

![](assets/update.png)

Si la actualización masiva devuelve un error o falla, consulte [Solución de problemas para la administración masiva Herramientas](../../reference/bulk-management-tools/bulk-troubleshooting.md).
