---
description: Una actualización masiva permite editar varios segmentos, características, modelos, fuentes de datos y elementos de carpeta de segmentos o características en una sola operación. Siga estas instrucciones para realizar actualizaciones masivas.
keywords: baaam
seo-description: Una actualización masiva permite editar varios segmentos, características, modelos, fuentes de datos y elementos de carpeta de segmentos o características en una sola operación. Siga estas instrucciones para realizar actualizaciones masivas.
seo-title: Actualizaciones masivas
solution: Audience Manager
title: Actualizaciones masivas
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 2%

---


# Actualizaciones masivas{#bulk-updates}

Una actualización masiva permite editar varios segmentos, características, modelos, fuentes de datos y elementos de carpeta de segmentos o características en una sola operación. Siga estas instrucciones para realizar actualizaciones masivas.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[Los permisos](../../features/administration/administration-overview.md) de grupo RBAC asignados en la [!DNL Audience Manager] interfaz de usuario se respetan en la [!UICONTROL Bulk Management Tools].

Para realizar actualizaciones masivas, abra la [!UICONTROL Bulk Management Tools] hoja de cálculo y:

1. Haga clic en la **[!UICONTROL Headers]** ficha y copie los encabezados de actualización del elemento que desee editar.
2. Click the **[!UICONTROL Update]** tab.
3. Pegue los encabezados de actualización en la primera fila de la hoja de cálculo de actualización. Tenga en cuenta lo siguiente:

   * Al actualizar una carpeta, se requieren todos los encabezados.
   * Al actualizar segmentos o características, solo necesita el ID de segmento (SID) y el elemento de encabezado que debe cambiarse. Eliminar encabezados no utilizados.

4. Pegue o escriba los datos que desee cambiar en una columna correspondiente basada en la etiqueta del encabezado.
5. En la barra de herramientas de la hoja de cálculo, haga clic en un botón de actualización que coincida con el elemento que está actualizando.
Esta acción abre el cuadro de diálogo [!UICONTROL Account Information] .

6. Proporcione la información [de](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) inicio de sesión necesaria y haga clic en **[!UICONTROL Submit]**.

   La hoja de cálculo crea una [!UICONTROL Results] columna. La [!UICONTROL Results] columna devuelve la respuesta JSON para una operación correcta. Consulte los ejemplos en las API de [REST](../../api/rest-api-main/rest-api-main.md) . Antes de introducir datos, la hoja de cálculo de actualización masiva debe tener un aspecto similar al siguiente:

![](assets/update.png)

Si la actualización masiva devuelve un error o un error, consulte [Resolución de problemas de las herramientas](../../reference/bulk-management-tools/bulk-troubleshooting.md)de administración masiva.
