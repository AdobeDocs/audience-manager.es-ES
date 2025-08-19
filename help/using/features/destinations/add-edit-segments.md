---
description: Las etiquetas de exportación de datos funcionan con los controles de exportación configurados en una fuente de datos. Las etiquetas de exportación de datos impiden que se agreguen características restringidas a una segmento y que se envíen datos segmento a un destino. Puede establecer varias etiquetas de exportación para un cookie nuevo o existente o URL destino.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add or Edit Segments for Server-to-Server Destinations
solution: Audience Manager
title: añadir o Editar segmentos para destinos de servidor a servidor
feature: Destination Basics
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---

# añadir o Editar segmentos para destinos de servidor a servidor {#add-edit-segments}

Solo puede agregar o editar segmentos para un destino de servidor a servidor ([!DNL S2S]). No puede crear [!DNL S2S] destinos con [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md). Póngase en contacto con el consultor para configurar [!DNL S2S] destinos. Siga estas instrucciones para agregar o editar segmentos para un [!DNL S2S] destino.

<!-- destination-s2s-edit.xml -->

Para agregar o editar segmento asignaciones de un [!DNL S2S] destino:

1. Vaya a **[!UICONTROL Audience Data > Destinations]**. Seleccione **Plataformas integradas > basadas en** dispositivos y encuentre el destino con el [!DNL S2S] que desea trabajar.
2. En la [!UICONTROL Action] columna, haga clic en el icono de lápiz para editar el destino.
   * En el **[!UICONTROL Search and Add Segments]** cuadro, inicio escribiendo el nombre de una segmento o haga clic en **[!UICONTROL Browse All Segments]** examinar una lista de segmentos disponibles.
   * Haga clic **[!UICONTROL Add Selected Segments]** cuando encuentre la segmento que desea utilizar. Al agregar una segmento se abre la [!UICONTROL Edit Mapping] ventana.
   * En [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: establezca un valor para el [par](../../features/destinations/key-value-pairs.md) clave-valor utilizado por este destino.
      * **[!UICONTROL Start Date]** y **[!UICONTROL End Date]**: elija una fecha inicio y una fecha final para el destino. Si la fecha de finalización está en blanco, el destino no caduca nunca.
3. Haga clic y **[!UICONTROL Save]** , a continuación, haga clic en **[!UICONTROL Done]**.
