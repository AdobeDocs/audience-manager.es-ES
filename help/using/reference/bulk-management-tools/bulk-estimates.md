---
description: Una estimación masiva devuelve datos de tamaño de segmento basados en reglas de segmentos. Siga estas instrucciones para realizar una solicitud de cálculo masiva.
seo-description: Una estimación masiva devuelve datos de tamaño de segmento basados en reglas de segmentos. Siga estas instrucciones para realizar una solicitud de cálculo masiva.
seo-title: Estimaciones masivas
solution: Audience Manager
title: Estimaciones masivas
uuid: 63 b 2 f 06 a -8 ba 0-47 a 2-bd 0 b -8039 b 2 d 4 c 95 d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Estimates{#bulk-estimates}

Una estimación masiva devuelve datos de tamaño de segmento basados en reglas de segmentos. Siga estas instrucciones para realizar una solicitud de cálculo masiva.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]*No* se admite [!DNL Audience Manager]en. Esta herramienta se proporciona para su comodidad y solo como cortesía. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Los permisos de grupo RBAC](../../features/administration/administration-overview.md) asignados en [!DNL Audience Manager] la interfaz de usuario se aceptan en [!UICONTROL Bulk Management Tools]la.

To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the [!UICONTROL Estimate Segment Size] header.
1. Click the **[!UICONTROL Estimate]** tab.
1. Pegue el encabezado de estimación en la primera fila de la hoja de cálculo estimada.
1. Pegue o escriba los datos que desee cambiar en una columna correspondiente según la etiqueta del encabezado.
1. En la barra de herramientas de la hoja de cálculo, haga clic en el botón Crear que coincida con el elemento que está actualizando.
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

This action creates a [!UICONTROL Response] column in the worksheet that contains estimated segment size data. Antes de ingresar datos, la hoja de cálculo de cálculo masiva debería tener un aspecto similar al siguiente:

![](assets/estimate.png)Si la actualización masiva devuelve un error o falla, consulte [Solución de problemas de herramientas de administración masiva](../../reference/bulk-management-tools/bulk-troubleshooting.md).

