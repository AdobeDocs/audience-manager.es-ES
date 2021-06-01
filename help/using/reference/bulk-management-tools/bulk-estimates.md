---
description: Una estimación masiva devuelve datos del tamaño del segmento en función de las reglas del segmento. Siga estas instrucciones para realizar una solicitud de estimación masiva.
seo-description: Una estimación masiva devuelve datos del tamaño del segmento en función de las reglas del segmento. Siga estas instrucciones para realizar una solicitud de estimación masiva.
seo-title: Estimaciones masivas
solution: Audience Manager
title: Estimaciones masivas
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 3%

---

# Estimaciones masivas{#bulk-estimates}

Una estimación masiva devuelve datos del tamaño del segmento en función de las reglas del segmento. Siga estas instrucciones para realizar una solicitud de estimación masiva.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[Los ](../../features/administration/administration-overview.md) permisos de grupo RBAC asignados en la  [!DNL Audience Manager] interfaz de usuario se respetan en  [!UICONTROL Bulk Management Tools].

Para realizar actualizaciones masivas, abra la hoja de cálculo [!UICONTROL Bulk Management Tools] y:

1. Haga clic en la pestaña **[!UICONTROL Headers]** y copie el encabezado [!UICONTROL Estimate Segment Size].
2. Haga clic en la pestaña **[!UICONTROL Estimate]**.
3. Pegue el encabezado de la estimación en la primera fila de la hoja de cálculo de la estimación.
4. Pegue o escriba los datos que desee cambiar en una columna correspondiente basada en la etiqueta del encabezado.
5. En la barra de herramientas de la hoja de cálculo, haga clic en el botón crear que coincida con el elemento que está actualizando.
Esta acción abre el cuadro de diálogo [!UICONTROL Account Information].
6. Proporcione la [información de inicio de sesión](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) necesaria y haga clic en **[!UICONTROL Submit]**.

Esta acción crea una columna [!UICONTROL Response] en la hoja de cálculo que contiene datos estimados del tamaño del segmento. Antes de introducir datos, la hoja de cálculo de estimación masiva debería tener un aspecto similar al siguiente:

![](assets/estimate.png)
Si la actualización masiva devuelve un error o falla, consulte  [Solución de problemas para herramientas de administración masiva](../../reference/bulk-management-tools/bulk-troubleshooting.md).
