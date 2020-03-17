---
description: La eliminación masiva permite eliminar varios segmentos, características, carpetas, señales derivadas, fuentes de datos, modelos y destinos con una sola operación. Siga estas instrucciones para realizar una solicitud de eliminación masiva.
seo-description: La eliminación masiva permite eliminar varios segmentos, características, carpetas, señales derivadas, fuentes de datos, modelos y destinos con una sola operación. Siga estas instrucciones para realizar una solicitud de eliminación masiva.
seo-title: Eliminación masiva
solution: Audience Manager
title: Eliminación masiva
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
translation-type: tm+mt
source-git-commit: 8cc3d9d629536c48b7013ffede16c0b112704c89

---


# Eliminación masiva{#bulk-delete}

La eliminación masiva permite eliminar varios segmentos, características, carpetas, señales derivadas, fuentes de datos, modelos y destinos con una sola operación. Siga estas instrucciones para realizar una solicitud de eliminación masiva.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[Los permisos](../../features/administration/administration-overview.md) de grupo RBAC asignados en la [!DNL Audience Manager] interfaz de usuario se respetan en la [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>Si tiene segmentos asignados al destino, fallará la eliminación masiva de asignaciones de destino. Elimine los segmentos de ese destino en la interfaz de usuario antes de intentar eliminar destinos de forma masiva. Además, las carpetas de rasgos y segmentos deben estar vacías para poder eliminarlas.

Para eliminar varios elementos, abra la [!UICONTROL Bulk Management Tools] hoja de cálculo y:

1. Haga clic en la ficha y copie los encabezados de creación del elemento que desee agregar. **[!UICONTROL Headers]**
2. Click the **[!UICONTROL Delete]** tab.
3. Pegue los encabezados de eliminación en la primera fila de la hoja de cálculo de actualización.
4. Pegue o escriba los ID de los objetos que desea eliminar en la columna debajo del encabezado.
5. Proporcione la información [de](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) inicio de sesión necesaria y haga clic en **[!UICONTROL Submit]**.

   La hoja de cálculo crea una [!UICONTROL Results] columna. La [!UICONTROL Results] columna devuelve un mensaje que indica si el elemento se ha eliminado o un mensaje de error.
Antes de introducir datos, la hoja de cálculo de actualización masiva debe tener un aspecto similar al siguiente:

![](assets/delete.png)

Si la actualización masiva devuelve un error o un error, consulte [Resolución de problemas de las herramientas](../../reference/bulk-management-tools/bulk-troubleshooting.md)de administración masiva.
