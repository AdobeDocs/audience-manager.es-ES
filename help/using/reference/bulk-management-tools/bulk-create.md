---
description: La creación masiva le permite crear varias fuentes de datos, señales derivadas, segmentos, características y otros elementos con una sola operación. Siga estas instrucciones para realizar una solicitud de creación masiva.
seo-description: La creación masiva le permite crear varias fuentes de datos, señales derivadas, segmentos, características y otros elementos con una sola operación. Siga estas instrucciones para realizar una solicitud de creación masiva.
seo-title: Creación masiva
solution: Audience Manager
title: Creación masiva
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
translation-type: tm+mt
source-git-commit: 3051ca9f7c4039dafdfa01b89226c1fa8717e610

---


# Creación masiva{#bulk-create}

La creación masiva le permite crear varias fuentes de datos, señales derivadas, segmentos, características y otros elementos con una sola operación. Siga estas instrucciones para realizar una solicitud de creación masiva.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[Los permisos](../../features/administration/administration-overview.md) de grupo RBAC asignados en la [!DNL Audience Manager] interfaz de usuario se respetan en la [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>No mezcle tipos de objetos en una solicitud de creación masiva. Los encabezados de cada objeto son únicos y no se pueden combinar. Borre la hoja de cálculo y realice una solicitud independiente para distintos elementos.

Para crear objetos de forma masiva, abra la [!UICONTROL Bulk Management Tools] hoja de cálculo y:

1. Haga clic en la ficha y copie los encabezados de creación del elemento que desee agregar. **[!UICONTROL Headers]**
2. Click the **[!UICONTROL Create]** tab.
3. Pegue los encabezados de creación en la primera fila de la hoja de cálculo de actualización.
4. Pegue o escriba los datos que desee cambiar en una columna correspondiente basada en la etiqueta del encabezado.
5. En la barra de herramientas de la hoja de cálculo, haga clic en el botón crear que coincida con el elemento que está actualizando.
Esta acción abre el cuadro de diálogo [!UICONTROL Account Information] .
6. Proporcione la información [de](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) inicio de sesión necesaria y haga clic en **[!UICONTROL Submit]**.

La hoja de cálculo crea una [!UICONTROL Results] columna. La [!UICONTROL Results] columna devuelve la respuesta JSON para una operación correcta. Consulte los ejemplos en las API de [REST](../../api/rest-api-main/rest-api-main.md) . Antes de introducir datos, la hoja de cálculo de creación masiva debe tener un aspecto similar al siguiente ejemplo. Tenga en cuenta que las distintas opciones de creación no se muestran aquí. Esto se incluye para ayudarle a comprender el aspecto que podría tener una hoja de cálculo completa.

![](assets/cretetraits.png)

Si la actualización masiva devuelve un error o un error, consulte [Resolución de problemas de las herramientas](../../reference/bulk-management-tools/bulk-troubleshooting.md)de administración masiva.
