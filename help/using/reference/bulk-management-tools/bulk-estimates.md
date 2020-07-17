---
description: Una estimación masiva devuelve datos del tamaño del segmento en función de las reglas del segmento. Siga estas instrucciones para realizar una solicitud de estimación masiva.
seo-description: Una estimación masiva devuelve datos del tamaño del segmento en función de las reglas del segmento. Siga estas instrucciones para realizar una solicitud de estimación masiva.
seo-title: Estimaciones masivas
solution: Audience Manager
title: Estimaciones masivas
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 3%

---


# Estimaciones masivas{#bulk-estimates}

Una estimación masiva devuelve datos del tamaño del segmento en función de las reglas del segmento. Siga estas instrucciones para realizar una solicitud de estimación masiva.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[Los permisos](../../features/administration/administration-overview.md) de grupo RBAC asignados en la [!DNL Audience Manager] interfaz de usuario se respetan en la [!UICONTROL Bulk Management Tools].

Para realizar actualizaciones masivas, abra la [!UICONTROL Bulk Management Tools] hoja de cálculo y:

1. Haga clic en la **[!UICONTROL Headers]** ficha y copie el [!UICONTROL Estimate Segment Size] encabezado.
2. Click the **[!UICONTROL Estimate]** tab.
3. Pegue el encabezado de estimación en la primera fila de la hoja de cálculo de estimación.
4. Pegue o escriba los datos que desee cambiar en una columna correspondiente basada en la etiqueta del encabezado.
5. En la barra de herramientas de la hoja de cálculo, haga clic en el botón crear que coincida con el elemento que está actualizando.
Esta acción abre el cuadro de diálogo [!UICONTROL Account Information] .
6. Proporcione la información [de](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) inicio de sesión necesaria y haga clic en **[!UICONTROL Submit]**.

Esta acción crea una [!UICONTROL Response] columna en la hoja de cálculo que contiene datos de tamaño de segmento estimados. Antes de introducir datos, la hoja de cálculo de estimación masiva debe tener un aspecto similar al siguiente:

![](assets/estimate.png)
Si la actualización masiva devuelve un error o un error, consulte [Resolución de problemas de las herramientas](../../reference/bulk-management-tools/bulk-troubleshooting.md)de administración masiva.

