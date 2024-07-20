---
description: Las etiquetas de exportación de datos funcionan con los controles de exportación definidos en una fuente de datos. Las etiquetas de exportación de datos impiden añadir rasgos restringidos a un segmento y enviar datos de segmento a un destino. Puede establecer varias etiquetas de exportación a una cookie o un destino URL nuevo o existente.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add or Edit Segments for Server-to-Server Destinations
solution: Audience Manager
title: Añadir o editar segmentos para destinos de servidor a servidor
feature: Destination Basics
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---

# Añadir o editar segmentos para destinos de servidor a servidor {#add-edit-segments}

Solo puede agregar o editar segmentos para un destino de servidor a servidor ([!DNL S2S]). No puede crear [!DNL S2S] destinos con [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md). Póngase en contacto con el consultor para configurar [!DNL S2S] destinos. Siga estas instrucciones para agregar o editar segmentos para un destino de [!DNL S2S].

<!-- destination-s2s-edit.xml -->

Para agregar o editar asignaciones de segmentos para un destino [!DNL S2S]:

1. Ir a **[!UICONTROL Audience Data > Destinations]**. Seleccione **Plataformas integradas > Basadas en dispositivos** y busque el destino [!DNL S2S] con el que desea trabajar.
2. En la columna [!UICONTROL Action], haga clic en el icono de lápiz para editar el destino.
   * En el cuadro **[!UICONTROL Search and Add Segments]**, empiece a escribir el nombre de un segmento o haga clic en **[!UICONTROL Browse All Segments]** para examinar una lista de segmentos disponibles.
   * Haga clic en **[!UICONTROL Add Selected Segments]** cuando encuentre el segmento que desee utilizar. Añadir un segmento abre la ventana [!UICONTROL Edit Mapping].
   * En [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: establezca un valor para el [par clave-valor](../../features/destinations/key-value-pairs.md) que usa este destino.
      * **[!UICONTROL Start Date]** y **[!UICONTROL End Date]**: elija una fecha de inicio y de finalización para el destino. Si la fecha de finalización está en blanco, el destino nunca caduca.
3. Haga clic en **[!UICONTROL Save]** y luego en **[!UICONTROL Done]**.
