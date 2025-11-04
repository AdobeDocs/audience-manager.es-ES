---
description: Las etiquetas de exportación de datos funcionan con los controles de exportación definidos en una fuente de datos. Las etiquetas de exportación de datos impiden añadir rasgos restringidos a un segmento y enviar datos de segmento a un destino. Puede establecer varias etiquetas de exportación a una cookie o un destino URL nuevo o existente.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add Data Export Controls to a Destination
solution: Audience Manager
title: Añadir controles de exportación de datos a un destino
feature: Data Export Controls
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 2%

---

# Añadir etiquetas de exportación de datos a un destino {#add-data-export-labels}

[!DNL Data Export Labels] trabaja con [!DNL Export Controls] que ha establecido en un origen de datos. [!DNL Data Export Labels] le impide agregar características restringidas a un segmento y enviar datos de segmento a un destino. Puede establecer varias etiquetas de exportación en un destino nuevo o existente [!DNL cookie] o [!DNL URL].

>[!NOTE]
>
>Para agregar una etiqueta de exportación, necesita permisos de administrador *o* suficientes privilegios para crear o editar un destino.

<!-- t_export_labels.xml -->

Para añadir etiquetas de exportación a un destino:

1. Haga clic **[!UICONTROL Audience Data]**:

   * Para nuevos destinos: Haga clic en **[!UICONTROL Create New Destination]**. Complete la sección [!UICONTROL Basic Information] antes de seleccionar una etiqueta de exportación de datos. Consulte [Crear un destino de cookie](../../features/destinations/create-cookie-destination.md) o [Crear un destino de URL](../../features/destinations/create-url-destination.md) para obtener información.
   * Para destinos existentes: utilice el cuadro [!DNL Search] para buscar el destino o desplácese por la lista y haga clic en el nombre del destino para abrirlo.

1. Seleccione un(a) [!DNL Data Export Label]. Deje las casillas de verificación en blanco si no desea establecer restricciones de exportación. Las etiquetas de exportación incluyen las siguientes opciones:

   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >Las restricciones de exportación no funcionarán a menos que establezca un [control de exportación coincidente](../../features/data-export-controls.md) en un origen de datos.

1. Haga clic en **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Crear una fuente de datos](../../features/manage-datasources.md#create-data-source)
