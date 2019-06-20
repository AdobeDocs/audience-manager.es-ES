---
description: La creación masiva permite crear varias fuentes de datos, señales derivadas, segmentos, características y otros elementos con una sola operación. Siga estas instrucciones para crear una solicitud de creación masiva.
seo-description: La creación masiva permite crear varias fuentes de datos, señales derivadas, segmentos, características y otros elementos con una sola operación. Siga estas instrucciones para crear una solicitud de creación masiva.
seo-title: Creación masiva
solution: Audience Manager
title: Creación masiva
uuid: 1 e 09 bcfa -783 e -4 e 9 b -9 ead -147 f 8 d 1381 c 8
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Create{#bulk-create}

La creación masiva permite crear varias fuentes de datos, señales derivadas, segmentos, características y otros elementos con una sola operación. Siga estas instrucciones para crear una solicitud de creación masiva.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]*No* se admite [!DNL Audience Manager]en. Esta herramienta se proporciona para su comodidad y solo como cortesía. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Los permisos de grupo RBAC](../../features/administration/administration-overview.md) asignados en [!DNL Audience Manager] la interfaz de usuario se aceptan en [!UICONTROL Bulk Management Tools]la.

>[!CAUTION]
>
>No mezcle tipos de objetos en una solicitud de creación masiva. Los encabezados para cada objeto son únicos y no pueden combinarse. Borre la hoja de cálculo y realice una solicitud separada para los distintos elementos.

To create objects in bulk, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the create headers for the item you want to add.
1. Click the **[!UICONTROL Create]** tab.
1. Pegue los encabezados de creación en la primera fila de la hoja de cálculo de actualización.
1. Pegue o escriba los datos que desee cambiar en una columna correspondiente según la etiqueta del encabezado.
1. En la barra de herramientas de la hoja de cálculo, haga clic en el botón Crear que coincida con el elemento que está actualizando.
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

The worksheet creates a [!UICONTROL Results] column. The [!UICONTROL Results] column returns the JSON response for a successful operation. See the [REST APIs](../../api/rest-api-main/rest-api-main.md) for examples. Antes de ingresar datos, la hoja de cálculo masiva debe tener un aspecto similar al siguiente. Tenga en cuenta que las diferentes opciones de creación no se muestran aquí. Esto se incluye para ayudarle a comprender qué aspecto podría tener una hoja de cálculo completa.

![](assets/cretetraits.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
