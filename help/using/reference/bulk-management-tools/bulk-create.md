---
description: La creación masiva le permite construir varias fuentes de datos, señales derivadas, segmentos, rasgos y otros elementos con una sola operación. Siga estas instrucciones para realizar una solicitud de creación masiva.
seo-description: Bulk create lets you construct multiple data sources, derived signals, segments, traits, and other items with a single operation. Follow these instructions to make a bulk creation request.
seo-title: Bulk Create
solution: Audience Manager
title: Creación masiva
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 1%

---

# Creación masiva{#bulk-create}

La creación masiva le permite construir varias fuentes de datos, señales derivadas, segmentos, rasgos y otros elementos con una sola operación. Siga estas instrucciones para realizar una solicitud de creación masiva.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[Permisos de grupo de RBAC](../../features/administration/administration-overview.md) asignado en el [!DNL Audience Manager] Las IU se respetan en la [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>No mezcle tipos de objetos en una solicitud de creación masiva. Los encabezados de cada objeto son únicos y no se pueden combinar. Borre la hoja de cálculo y realice una solicitud independiente para elementos diferentes.

Para crear objetos de forma masiva, abra [!UICONTROL Bulk Management Tools] hoja de cálculo y:

1. Haga clic en **[!UICONTROL Headers]** y copie los encabezados de creación del elemento que desee agregar.
2. Haga clic en **[!UICONTROL Create]** pestaña.
3. Pegue los encabezados creados en la primera fila de la hoja de cálculo de actualización.
4. Pegue o escriba los datos que desea cambiar en una columna correspondiente basada en la etiqueta del encabezado.
5. En la barra de herramientas de la hoja de cálculo, haga clic en el botón Crear que coincida con el elemento que está actualizando.
Esta acción abre el [!UICONTROL Account Information] Cuadro de diálogo.
6. Proporcione los necesarios [información de inicio de sesión](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) y haga clic en **[!UICONTROL Submit]**.

La hoja de cálculo crea un [!UICONTROL Results] columna. El [!UICONTROL Results] devuelve la respuesta JSON para una operación correcta. Consulte la [API de REST](../../api/rest-api-main/rest-api-main.md) para ver ejemplos. Antes de introducir datos, la hoja de cálculo creada de forma masiva debería tener un aspecto similar al siguiente ejemplo. Tenga en cuenta que todas las opciones de creación diferentes no se muestran aquí. Esto se incluye para ayudarle a comprender el aspecto que podría tener una hoja de cálculo completada.

![](assets/cretetraits.png)

Si la actualización masiva devuelve un error o falla, consulte [Solución de problemas para herramientas de administración masiva](../../reference/bulk-management-tools/bulk-troubleshooting.md).
