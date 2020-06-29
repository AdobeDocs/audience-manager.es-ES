---
description: Las etiquetas de exportación de datos funcionan con los controles de exportación establecidos en un origen de datos. Las etiquetas de exportación de datos impiden agregar características restringidas a un segmento y enviar datos de segmentos a un destino. Puede establecer varias etiquetas de exportación en un destino de cookie o URL nuevo o existente.
seo-description: Las etiquetas de exportación de datos funcionan con los controles de exportación establecidos en un origen de datos. Las etiquetas de exportación de datos impiden agregar características restringidas a un segmento y enviar datos de segmentos a un destino. Puede establecer varias etiquetas de exportación en un destino de cookie o URL nuevo o existente.
seo-title: Añadir controles de exportación de datos a un destino
solution: Audience Manager
title: Añadir controles de exportación de datos a un destino
feature: Data Export Controls
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 1%

---



# Añadir etiquetas de exportación de datos en un destino {#add-data-export-labels}

[!DNL Data Export Labels] trabaje con el [!DNL Export Controls] conjunto en un origen de datos. [!DNL Data Export Labels] evite agregar características restringidas a un segmento y enviar datos de segmentos a un destino. Puede definir varias etiquetas de exportación en un destino nuevo o existente [!DNL cookie] o [!DNL URL] .

>[!NOTE]
>
>Para agregar una etiqueta de exportación, necesita permisos de administrador *o* suficientes privilegios para crear o editar un destino.

<!-- t_export_labels.xml -->

Para agregar etiquetas de exportación a un destino:

1. Haga clic **[!UICONTROL Audience Data]**:
   * Para nuevos destinos: Haga clic en **[!UICONTROL Create New Destination]**. Complete la [!UICONTROL Basic Information] sección antes de seleccionar una etiqueta de exportación de datos. Consulte [Creación de un destino](../../features/destinations/create-cookie-destination.md) de cookie o [Creación de un destino](../../features/destinations/create-url-destination.md) de URL para obtener más información.
   * Para destinos existentes: Utilice el [!DNL Search] cuadro para buscar el destino o desplácese por la lista y haga clic en el nombre del destino para abrirlo.
1. Seleccione una [!DNL Data Export Label]. Deje las casillas en blanco si no desea establecer ninguna restricción de exportación. Las etiquetas de exportación incluyen las siguientes opciones:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Las restricciones de exportación no funcionarán a menos que establezca un control [de exportación](../../features/data-export-controls.md) coincidente en un origen de datos.
1. Haga clic **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Crear una fuente de datos](../../features/manage-datasources.md#create-data-source)