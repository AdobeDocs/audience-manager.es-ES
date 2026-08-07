---
description: La creación masiva le permite construir varias fuentes de datos, señales derivadas, segmentos, rasgos y otros elementos con una sola operación. Siga estas instrucciones para realizar una solicitud de creación masiva.
seo-description: Bulk create lets you construct multiple data sources, derived signals, segments, traits, and other items with a single operation. Follow these instructions to make a bulk creation request.
seo-title: Bulk Create
solution: Audience Manager
title: Creación masiva
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
TQID: https://experienceleague.adobe.com/EbavgrTOfC5Wjx4IwGxt4Gi3-d-EkOSQjG3WaRAionU
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: c2c33729-f309-4bc2-92ba-87c475259df3id: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 291
ht-degree: 0%

---

# Creación masiva{#bulk-create}

La creación masiva le permite construir varias fuentes de datos, señales derivadas, segmentos, rasgos y otros elementos con una sola operación. Siga estas instrucciones para realizar una solicitud de creación masiva.

>[!IMPORTANT]
>
>Las herramientas de administración masiva no son una oferta de Adobe oficialmente compatible. La resolución de problemas y la asistencia técnica a través del Servicio de atención al cliente se gestionarán caso por caso.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[Los permisos de grupo RBAC](../../features/administration/administration-overview.md) asignados en la interfaz de usuario de [!DNL Audience Manager] se respetan en [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>No mezcle tipos de objetos en una solicitud de creación masiva. Los encabezados de cada objeto son únicos y no se pueden combinar. Borre la hoja de cálculo y realice una solicitud independiente para elementos diferentes.

Para crear objetos de forma masiva, abra la hoja de cálculo [!UICONTROL Bulk Management Tools] y:

1. Haga clic en la ficha **[!UICONTROL Headers]** y copie los encabezados de creación del elemento que desee agregar.
2. Haga clic en la ficha **[!UICONTROL Create]**.
3. Pegue los encabezados creados en la primera fila de la hoja de cálculo de actualización.
4. Pegue o escriba los datos que desea cambiar en una columna correspondiente basada en la etiqueta del encabezado.
5. En la barra de herramientas de la hoja de cálculo, haga clic en el botón Crear que coincida con el elemento que está actualizando.
Esta acción abre el cuadro de diálogo [!UICONTROL Account Information].
6. Proporcione la [información de inicio de sesión](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) necesaria y haga clic en **[!UICONTROL Submit]**.

La hoja de cálculo crea una columna [!UICONTROL Results]. La columna [!UICONTROL Results] devuelve la respuesta JSON para una operación correcta. Consulte las [API de REST](../../api/rest-api-main/rest-api-main.md) para ver ejemplos. Antes de introducir datos, la hoja de cálculo creada de forma masiva debería tener un aspecto similar al siguiente ejemplo. Tenga en cuenta que todas las opciones de creación diferentes no se muestran aquí. Esto se incluye para ayudarle a comprender el aspecto que podría tener una hoja de cálculo completada.

![](assets/cretetraits.png)

Si su actualización masiva devuelve un error o falla, consulte [Solución de problemas para herramientas de administración masiva](../../reference/bulk-management-tools/bulk-troubleshooting.md).
