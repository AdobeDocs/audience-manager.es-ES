---
description: Una estimación masiva devuelve datos de tamaño segmento basados en reglas de segmento. Siga estas instrucciones para hacer una estimación global solicitud.
seo-description: A bulk estimate returns segment size data based on segment rules. Follow these instructions to make a bulk estimate request.
seo-title: Bulk Estimates
solution: Audience Manager
title: Estimaciones globales
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# Estimaciones globales{#bulk-estimates}

Una estimación masiva devuelve datos de tamaño segmento basados en reglas de segmento. Siga estas instrucciones para hacer una estimación global solicitud.

>[!IMPORTANT]
>
>Los Herramientas de administración masiva no son una oferta Adobe Systems que se admita oficialmente. La solución de problemas y el soporte a través del Servicio de atención al cliente se manejarán caso por caso.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[Los permisos](../../features/administration/administration-overview.md) RBAC grupo asignados en el [!DNL Audience Manager] IU se respetan en el [!UICONTROL Bulk Management Tools].

Para realizar actualizaciones masivas, abra la hoja de [!UICONTROL Bulk Management Tools] cálculo y:

1. Haga clic en el **[!UICONTROL Headers]** pestaña y copie el [!UICONTROL Estimate Segment Size] encabezado.
2. Haga clic en el **[!UICONTROL Estimate]** pestaña.
3. Pegar el encabezado Estimación en la primera fila de la hoja de cálculo de estimación.
4. Pegar o escriba los datos que desea convertir en una columna correspondiente basada en la etiqueta de encabezado.
5. En la barra de herramientas de la hoja de cálculo, haga clic en el botón de creación que coincida con el elemento que está actualizando.
Esta acción abre el cuadro de [!UICONTROL Account Information] diálogo.
6. Proporcione la información[ de inicio de sesión necesaria ](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)y haga clic en **[!UICONTROL Submit]**.

Esta acción crea una [!UICONTROL Response] columna en la hoja de cálculo que contiene datos de tamaño de segmento estimado. Antes de ingresar datos, la hoja de cálculo de estimación masiva debe tener un aspecto similar al siguiente:

![](assets/estimate.png)Si la actualización masiva devuelve un error o falla, consulte [Solución de problemas para la administración masiva Herramientas](../../reference/bulk-management-tools/bulk-troubleshooting.md).
