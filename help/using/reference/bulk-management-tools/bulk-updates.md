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
>[Los ](../../features/administration/administration-overview.md) permisos de grupo RBAC asignados en la  [!DNL Audience Manager] interfaz de usuario se respetan en la  [!UICONTROL Bulk Management Tools].

Para realizar actualizaciones masivas, abra la hoja de cálculo [!UICONTROL Bulk Management Tools] y:

1. Haga clic en la ficha **[!UICONTROL Headers]** y copie los encabezados de actualización del elemento que desee editar.
2. Haga clic en la ficha **[!UICONTROL Update]**.
3. Pegue los encabezados de actualización en la primera fila de la hoja de cálculo de actualización. Tenga en cuenta lo siguiente:

   * Al actualizar una carpeta, se requieren todos los encabezados.
   * Al actualizar segmentos o características, solo necesita el ID de segmento (SID) y el elemento de encabezado que debe cambiarse. Eliminar encabezados no utilizados.

4. Pegue o escriba los datos que desee cambiar en una columna correspondiente basada en la etiqueta del encabezado.
5. En la barra de herramientas de la hoja de cálculo, haga clic en un botón de actualización que coincida con el        elemento que está actualizando.
Esta acción abre el cuadro de diálogo [!UICONTROL Account Information].

6. Proporcione la [información de inicio de sesión requerida](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) y haga clic en **[!UICONTROL Submit]**.

   La hoja de cálculo crea una columna [!UICONTROL Results]. La columna [!UICONTROL Results] devuelve la respuesta JSON para una operación correcta. Consulte las [API de REST](../../api/rest-api-main/rest-api-main.md) para ver ejemplos. Antes de introducir datos, la hoja de cálculo de actualización masiva debe tener un aspecto similar al siguiente:

![](assets/update.png)

Si la actualización masiva devuelve un error o falla, consulte [Solución de problemas para las herramientas de administración masiva](../../reference/bulk-management-tools/bulk-troubleshooting.md).
