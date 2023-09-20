---
description: Una actualización masiva le permite editar varios segmentos, rasgos, modelos, fuentes de datos y elementos de carpetas de segmentos o rasgos en una sola operación. Siga estas instrucciones para realizar actualizaciones masivas.
keywords: baaam
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
ht-degree: 1%

---

# Actualizaciones masivas{#bulk-updates}

Una actualización masiva le permite editar varios segmentos, rasgos, modelos, fuentes de datos y elementos de carpetas de segmentos o rasgos en una sola operación. Siga estas instrucciones para realizar actualizaciones masivas.

>[!IMPORTANT]
>
>Las herramientas de administración masiva no son una oferta de Adobe oficialmente admitida. La resolución de problemas y la asistencia técnica a través del Servicio de atención al cliente se gestionarán caso por caso.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[Permisos de grupo de RBAC](../../features/administration/administration-overview.md) asignado en el [!DNL Audience Manager] Las IU se respetan en la [!UICONTROL Bulk Management Tools].

Para realizar actualizaciones masivas, abra el [!UICONTROL Bulk Management Tools] hoja de cálculo y:

1. Haga clic en **[!UICONTROL Headers]** y copie los encabezados de actualización del elemento que desee editar.
2. Haga clic en **[!UICONTROL Update]** pestaña.
3. Pegue los encabezados de actualización en la primera fila de la hoja de cálculo de actualización. Tenga en cuenta lo siguiente:

   * Al actualizar una carpeta, se requieren todos los encabezados.
   * Al actualizar segmentos o características, solo necesita el ID de segmento (SID) y el elemento de encabezado que debe cambiarse. Eliminar encabezados no utilizados.

4. Pegue o escriba los datos que desea cambiar en una columna correspondiente basada en la etiqueta del encabezado.
5. En la barra de herramientas de la hoja de cálculo, haga clic en un botón de actualización que coincida con el elemento que está actualizando.
Esta acción abre el [!UICONTROL Account Information] Cuadro de diálogo.

6. Proporcione los necesarios [información de inicio de sesión](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) y haga clic en **[!UICONTROL Submit]**.

   La hoja de cálculo crea un [!UICONTROL Results] columna. El [!UICONTROL Results] devuelve la respuesta JSON para una operación correcta. Consulte la [API de REST](../../api/rest-api-main/rest-api-main.md) para ver ejemplos. Antes de introducir datos, la hoja de cálculo de actualización masiva debe tener un aspecto similar al siguiente:

![](assets/update.png)

Si la actualización masiva devuelve un error o falla, consulte [Solución de problemas para herramientas de administración masiva](../../reference/bulk-management-tools/bulk-troubleshooting.md).
