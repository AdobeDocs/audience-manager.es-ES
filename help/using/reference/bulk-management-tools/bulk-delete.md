---
description: La eliminación masiva permite eliminar varios segmentos, características, carpetas, señales derivadas, fuentes de datos, modelos y destinos con una sola operación. Siga estas instrucciones para realizar una solicitud de eliminación masiva.
seo-description: La eliminación masiva permite eliminar varios segmentos, características, carpetas, señales derivadas, fuentes de datos, modelos y destinos con una sola operación. Siga estas instrucciones para realizar una solicitud de eliminación masiva.
seo-title: Eliminación masiva
solution: Audience Manager
title: Eliminación masiva
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: BAAAM
exl-id: 3ff530dd-66d0-4dd3-a6e6-afe4a9cb5ba4
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# Eliminación masiva{#bulk-delete}

La eliminación masiva permite eliminar varios segmentos, características, carpetas, señales derivadas, fuentes de datos, modelos y destinos con una sola operación. Siga estas instrucciones para realizar una solicitud de eliminación masiva.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[Los ](../../features/administration/administration-overview.md) permisos de grupo RBAC asignados en la  [!DNL Audience Manager] interfaz de usuario se respetan en  [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>Si tiene segmentos asignados al destino, se producirá un error en la eliminación masiva de las asignaciones de destino. Elimine los segmentos de ese destino en la interfaz de usuario antes de intentar eliminar los destinos de forma masiva. Además, las carpetas de rasgos y segmentos deben estar vacías para poder eliminarlas.

Para eliminar varios elementos, abra la hoja de cálculo [!UICONTROL Bulk Management Tools] y:

1. Haga clic en la pestaña **[!UICONTROL Headers]** y copie los encabezados de creación del elemento que desee añadir.
2. Haga clic en la pestaña **[!UICONTROL Delete]**.
3. Pegue los encabezados de eliminación en la primera fila de la hoja de cálculo de actualización.
4. Pegue o escriba los ID de los objetos que desea eliminar en la columna que se encuentra debajo del encabezado.
5. Proporcione la [información de inicio de sesión](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) necesaria y haga clic en **[!UICONTROL Submit]**.

   La hoja de cálculo crea una columna [!UICONTROL Results]. La columna [!UICONTROL Results] devuelve un mensaje que indica si el elemento se ha eliminado o si hay un mensaje de error.
Antes de introducir datos, la hoja de cálculo de actualización masiva debería tener un aspecto similar al siguiente:

![](assets/delete.png)

Si la actualización masiva devuelve un error o falla, consulte [Solución de problemas para herramientas de administración masiva](../../reference/bulk-management-tools/bulk-troubleshooting.md).
