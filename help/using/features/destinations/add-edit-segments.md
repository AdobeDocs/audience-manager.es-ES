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

Solo puede agregar o editar segmentos para un destino de servidor a servidor ([!DNL S2S]). No se pueden crear [!DNL S2S] destinos con [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md). Póngase en contacto con el consultor para configurar [!DNL S2S] destinos. Siga estas instrucciones para agregar o editar segmentos para un [!DNL S2S] destino.

<!-- destination-s2s-edit.xml -->

Para agregar o editar asignaciones de segmentos para un [!DNL S2S] destino:

1. Vaya a **[!UICONTROL Audience Data > Destinations]**. Seleccione Plataformas **integradas > Basado** en dispositivos y busque el [!DNL S2S] destino con el que desea trabajar.
2. En la [!UICONTROL Action] columna, haga clic en el icono del lápiz para editar el destino.
   * En el **[!UICONTROL Search and Add Segments]** cuadro, inicio escribiendo el nombre de un segmento o haga clic en **[!UICONTROL Browse All Segments]** examinar una lista de segmentos disponibles.
   * Haga clic **[!UICONTROL Add Selected Segments]** cuando encuentre el segmento que desee utilizar. Al añadir un segmento se abre la [!UICONTROL Edit Mapping] ventana.
   * En [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**:: Establezca un valor para el par [](../../features/destinations/key-value-pairs.md) clave-valor utilizado por este destino.
      * **[!UICONTROL Start Date]** y **[!UICONTROL End Date]**: Elija un inicio y una fecha de finalización para el destino. Si la fecha de finalización está en blanco, el destino nunca caduca.
3. Haga clic en **[!UICONTROL Save]** y, a continuación, en **[!UICONTROL Done]**.
