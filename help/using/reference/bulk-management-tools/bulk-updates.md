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
TQID: https://experienceleague.adobe.com/fDSvlPqWTgaw-SszCIa5M2qxJcyfrewPaW03eVShhDw
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: c2c33729-f309-4bc2-92ba-87c475259df3
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 268
ht-degree: 0%

---

# Actualizaciones masivas{#bulk-updates}

Una actualización masiva le permite editar varios segmentos, rasgos, modelos, fuentes de datos y elementos de carpetas de segmentos o rasgos en una sola operación. Siga estas instrucciones para realizar actualizaciones masivas.

>[!IMPORTANT]
>
>Las herramientas de administración masiva no son una oferta de Adobe oficialmente compatible. La resolución de problemas y la asistencia técnica a través del Servicio de atención al cliente se gestionarán caso por caso.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[Los permisos de grupo RBAC](../../features/administration/administration-overview.md) asignados en la interfaz de usuario de [!DNL Audience Manager] se respetan en [!UICONTROL Bulk Management Tools].

Para realizar actualizaciones masivas, abra la hoja de cálculo [!UICONTROL Bulk Management Tools] y:

1. Haga clic en la ficha **[!UICONTROL Headers]** y copie los encabezados de actualización del elemento que desee editar.
2. Haga clic en la ficha **[!UICONTROL Update]**.
3. Pegue los encabezados de actualización en la primera fila de la hoja de cálculo de actualización. Tenga en cuenta lo siguiente:

   * Al actualizar una carpeta, se requieren todos los encabezados.
   * Al actualizar segmentos o características, solo necesita el ID de segmento (SID) y el elemento de encabezado que debe cambiarse. Eliminar encabezados no utilizados.

4. Pegue o escriba los datos que desea cambiar en una columna correspondiente basada en la etiqueta del encabezado.
5. En la barra de herramientas de la hoja de cálculo, haga clic en un botón de actualización que coincida con el        elemento que está actualizando.
Esta acción abre el cuadro de diálogo [!UICONTROL Account Information].

6. Proporcione la [información de inicio de sesión](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) necesaria y haga clic en **[!UICONTROL Submit]**.

   La hoja de cálculo crea una columna [!UICONTROL Results]. La columna [!UICONTROL Results] devuelve la respuesta JSON para una operación correcta. Consulte las [API de REST](../../api/rest-api-main/rest-api-main.md) para ver ejemplos. Antes de introducir datos, la hoja de cálculo de actualización masiva debe tener un aspecto similar al siguiente:

![](assets/update.png)

Si su actualización masiva devuelve un error o falla, consulte [Solución de problemas para herramientas de administración masiva](../../reference/bulk-management-tools/bulk-troubleshooting.md).
