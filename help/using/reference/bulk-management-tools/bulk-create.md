---
description: La creación masiva permite construir varias fuentes de datos, señales derivadas, segmentos, rasgos y otros elementos con una sola operación. Siga estas instrucciones para realizar una solicitud de creación masiva.
seo-description: La creación masiva permite construir varias fuentes de datos, señales derivadas, segmentos, rasgos y otros elementos con una sola operación. Siga estas instrucciones para realizar una solicitud de creación masiva.
seo-title: Creación masiva
solution: Audience Manager
title: Creación masiva
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# Creación masiva{#bulk-create}

La creación masiva permite construir varias fuentes de datos, señales derivadas, segmentos, rasgos y otros elementos con una sola operación. Siga estas instrucciones para realizar una solicitud de creación masiva.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[Los ](../../features/administration/administration-overview.md) permisos de grupo RBAC asignados en la  [!DNL Audience Manager] interfaz de usuario se respetan en  [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>No mezcle tipos de objetos en una solicitud de creación masiva. Los encabezados de cada objeto son únicos y no se pueden combinar. Borre la hoja de cálculo y realice una solicitud independiente para distintos elementos.

Para crear objetos de forma masiva, abra la hoja de cálculo [!UICONTROL Bulk Management Tools] y:

1. Haga clic en la pestaña **[!UICONTROL Headers]** y copie los encabezados de creación del elemento que desee añadir.
2. Haga clic en la pestaña **[!UICONTROL Create]**.
3. Pegue los encabezados de creación en la primera fila de la hoja de cálculo de actualización.
4. Pegue o escriba los datos que desee cambiar en una columna correspondiente basada en la etiqueta del encabezado.
5. En la barra de herramientas de la hoja de cálculo, haga clic en el botón crear que coincida con el elemento que está actualizando.
Esta acción abre el cuadro de diálogo [!UICONTROL Account Information].
6. Proporcione la [información de inicio de sesión](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) necesaria y haga clic en **[!UICONTROL Submit]**.

La hoja de cálculo crea una columna [!UICONTROL Results]. La columna [!UICONTROL Results] devuelve la respuesta JSON para una operación correcta. Consulte las [API de REST](../../api/rest-api-main/rest-api-main.md) para ver ejemplos. Antes de introducir datos, la hoja de cálculo de creación masiva debería tener un aspecto similar al del siguiente ejemplo. Tenga en cuenta que aquí no se muestran todas las opciones de creación diferentes. Esto se incluye para ayudarle a comprender el aspecto que podría tener una hoja de cálculo completada.

![](assets/cretetraits.png)

Si la actualización masiva devuelve un error o falla, consulte [Solución de problemas para herramientas de administración masiva](../../reference/bulk-management-tools/bulk-troubleshooting.md).
