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
ht-degree: 7%

---

# Añadir o editar segmentos para destinos de servidor a servidor {#add-edit-segments}

Solo puede añadir o editar segmentos de un servidor a servidor ([!DNL S2S]) destino. No puede crear [!DNL S2S] destinos con [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md). Póngase en contacto con su consultor de para configurar [!DNL S2S] destinos. Siga estas instrucciones para agregar o editar segmentos para una [!DNL S2S] destino.

<!-- destination-s2s-edit.xml -->

Para agregar o editar asignaciones de segmentos para un [!DNL S2S] destino:

1. Ir a **[!UICONTROL Audience Data > Destinations]**. Seleccionar **Plataformas integradas > Basado en dispositivos** y busque el [!DNL S2S] destino con el que desea trabajar.
2. En el [!UICONTROL Action] Haga clic en el icono de lápiz para editar el destino.
   * En el **[!UICONTROL Search and Add Segments]** , empiece a escribir el nombre de un segmento o haga clic en **[!UICONTROL Browse All Segments]** examine una lista de segmentos disponibles.
   * Clic **[!UICONTROL Add Selected Segments]** cuando encuentre el segmento que desea utilizar. Añadir un segmento abre el [!UICONTROL Edit Mapping] ventana.
   * En [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: establezca un valor para [par clave-valor](../../features/destinations/key-value-pairs.md) utilizado por este destino.
      * **[!UICONTROL Start Date]** y **[!UICONTROL End Date]**: elija una fecha de inicio y de finalización para el destino. Si la fecha de finalización está en blanco, el destino nunca caduca.
3. Clic **[!UICONTROL Save]** y luego haga clic en **[!UICONTROL Done]**.
