---
description: Las etiquetas de exportación de datos funcionan con los controles de exportación establecidos en un origen de datos. Las etiquetas de exportación de datos impiden agregar características restringidas a un segmento y enviar datos de segmentos a un destino. Puede establecer varias etiquetas de exportación en un destino de cookie o URL nuevo o existente.
seo-description: Las etiquetas de exportación de datos funcionan con los controles de exportación establecidos en un origen de datos. Las etiquetas de exportación de datos impiden agregar características restringidas a un segmento y enviar datos de segmentos a un destino. Puede establecer varias etiquetas de exportación en un destino de cookie o URL nuevo o existente.
seo-title: Añadir o editar segmentos para destinos de servidor a servidor
solution: Audience Manager
title: Añadir o editar segmentos para destinos de servidor a servidor
feature: Destination Basics
translation-type: tm+mt
source-git-commit: 55925e803e16580e0d9357d973405cf39370a8fd
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 8%

---


# Añadir o editar segmentos para destinos de servidor a servidor {#add-edit-segments}

Solo puede agregar o editar segmentos para un destino de servidor a servidor ([!DNL S2S]). No puede crear destinos [!DNL S2S] con [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md). Póngase en contacto con su asesor para configurar [!DNL S2S] destinos. Siga estas instrucciones para agregar o editar segmentos para un destino [!DNL S2S].

<!-- destination-s2s-edit.xml -->

Para agregar o editar asignaciones de segmentos para un destino [!DNL S2S]:

1. Vaya a **[!UICONTROL Audience Data > Destinations]**. Seleccione **Plataformas integradas > Basadas en dispositivos** y busque el [!DNL S2S] destino con el que desea trabajar.
2. En la columna [!UICONTROL Action], haga clic en el icono del lápiz para editar el destino.
   * En el cuadro **[!UICONTROL Search and Add Segments]**, inicio escribiendo el nombre de un segmento o haga clic en **[!UICONTROL Browse All Segments]** examinar una lista de segmentos disponibles.
   * Haga clic **[!UICONTROL Add Selected Segments]** cuando encuentre el segmento que desee utilizar. Al añadir un segmento se abre la ventana [!UICONTROL Edit Mapping].
   * En [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**:: Establezca un valor para el valor de  [clave ](../../features/destinations/key-value-pairs.md) pairused por este destino.
      * **[!UICONTROL Start Date]** y  **[!UICONTROL End Date]**: Elija un inicio y una fecha de finalización para el destino. Si la fecha de finalización está en blanco, el destino nunca caduca.
3. Haga clic en **[!UICONTROL Save]** y, a continuación, haga clic en **[!UICONTROL Done]**.
