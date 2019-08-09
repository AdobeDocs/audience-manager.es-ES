---
description: Las etiquetas de exportación de datos funcionan con los controles de exportación que se establecen en un origen de datos. Las etiquetas de exportación de datos impiden agregar características restringidas a un segmento y enviar datos de segmentos a un destino. Puede configurar varias etiquetas de exportación a una cookie o destino URL nuevo o existente.
seo-description: Las etiquetas de exportación de datos funcionan con los controles de exportación que se establecen en un origen de datos. Las etiquetas de exportación de datos impiden agregar características restringidas a un segmento y enviar datos de segmentos a un destino. Puede configurar varias etiquetas de exportación a una cookie o destino URL nuevo o existente.
seo-title: Agregar controles de exportación de datos a un destino
solution: Audience Manager
title: Agregar controles de exportación de datos a un destino
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---



# Agregar etiquetas de exportación de datos a un destino {#add-data-export-labels}

[!DNL Data Export Labels] trabaje con [!DNL Export Controls] el que establezca en un origen de datos. [!DNL Data Export Labels] impedir que agregue características restringidas a un segmento y envíe datos de segmentos a un destino. Puede configurar varias etiquetas de exportación a un nuevo o existente [!DNL cookie][!DNL URL] destino.

>[!NOTE]
>
>Para agregar una etiqueta de exportación, necesita permisos *de administrador o* suficientes privilegios para crear o editar un destino.

<!-- t_export_labels.xml -->

Para agregar etiquetas de exportación a un destino:

1. Haga clic en **[!UICONTROL Audience Data]**:
   * Para nuevos destinos: Haga clic **[!UICONTROL Create New Destination]** en. Complete [!UICONTROL Basic Information] la sección antes de seleccionar una etiqueta de exportación de datos. Consulte [Creación de un destino de cookie](../../features/destinations/create-cookie-destination.md) o [Creación de un destino de URL para](../../features/destinations/create-url-destination.md) obtener información.
   * Para destinos existentes: Utilice [!DNL Search] el cuadro para encontrar el destino o desplazarse por la lista y hacer clic en el nombre de destino para abrirlo.
1. Seleccione una [!DNL Data Export Label]. Deje las casillas de verificación en blanco si no desea establecer restricciones de exportación. Las etiquetas de exportación incluyen las siguientes opciones:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Las restricciones de exportación no funcionarán a menos que establezca un [control de exportación coincidente](../../features/data-export-controls.md) en un origen de datos.
1. Haga clic en **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Crear una fuente de datos](../../features/manage-datasources.md#create-data-source)