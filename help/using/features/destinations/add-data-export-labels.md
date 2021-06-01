---
description: Las etiquetas de exportación de datos funcionan con los controles de exportación establecidos en un origen de datos. Las etiquetas de exportación de datos impiden añadir características restringidas a un segmento y enviar datos de segmento a un destino. Puede establecer varias etiquetas de exportación en un destino de URL o cookie nuevo o existente.
seo-description: Las etiquetas de exportación de datos funcionan con los controles de exportación establecidos en un origen de datos. Las etiquetas de exportación de datos impiden añadir características restringidas a un segmento y enviar datos de segmento a un destino. Puede establecer varias etiquetas de exportación en un destino de URL o cookie nuevo o existente.
seo-title: Añadir controles de exportación de datos a un destino
solution: Audience Manager
title: Añadir controles de exportación de datos a un destino
feature: Controles de exportación de datos
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 8%

---

# Agregar etiquetas de exportación de datos a un destino {#add-data-export-labels}

[!DNL Data Export Labels] trabaje con el  [!DNL Export Controls] configurado en un origen de datos. [!DNL Data Export Labels] impida la adición de características restringidas a un segmento y el envío de datos de segmentos a un destino. Puede establecer varias etiquetas de exportación en un destino [!DNL cookie] o [!DNL URL] nuevo o existente.

>[!NOTE]
>
>Para añadir una etiqueta de exportación, necesita permisos de administrador *o* suficientes privilegios para crear o editar un destino.

<!-- t_export_labels.xml -->

Para añadir etiquetas de exportación a un destino:

1. Haga clic **[!UICONTROL Audience Data]**:
   * Para nuevos destinos: Haga clic en **[!UICONTROL Create New Destination]**. Complete la sección [!UICONTROL Basic Information] antes de seleccionar una etiqueta de exportación de datos. Consulte [Crear un destino de cookie](../../features/destinations/create-cookie-destination.md) o [Crear un destino de URL](../../features/destinations/create-url-destination.md) para obtener más información.
   * Para destinos existentes: Utilice el cuadro [!DNL Search] para encontrar el destino o desplácese por la lista y haga clic en el nombre de destino para abrirlo.
1. Seleccione una [!DNL Data Export Label]. Deje las casillas en blanco si no desea establecer ninguna restricción de exportación. Las etiquetas de exportación incluyen las siguientes opciones:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >Las restricciones de exportación no funcionarán a menos que establezca un [control de exportación coincidente](../../features/data-export-controls.md) en un origen de datos.
1. Haga clic **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Crear una fuente de datos](../../features/manage-datasources.md#create-data-source)

