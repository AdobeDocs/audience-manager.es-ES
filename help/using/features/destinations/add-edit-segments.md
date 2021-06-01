---
description: Las etiquetas de exportación de datos funcionan con los controles de exportación establecidos en un origen de datos. Las etiquetas de exportación de datos impiden añadir características restringidas a un segmento y enviar datos de segmento a un destino. Puede establecer varias etiquetas de exportación en un destino de URL o cookie nuevo o existente.
seo-description: Las etiquetas de exportación de datos funcionan con los controles de exportación establecidos en un origen de datos. Las etiquetas de exportación de datos impiden añadir características restringidas a un segmento y enviar datos de segmento a un destino. Puede establecer varias etiquetas de exportación en un destino de URL o cookie nuevo o existente.
seo-title: Añadir o editar segmentos para destinos de servidor a servidor
solution: Audience Manager
title: Añadir o editar segmentos para destinos de servidor a servidor
feature: Conceptos básicos de destino
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 8%

---

# Añadir o editar segmentos para destinos de servidor a servidor {#add-edit-segments}

Solo puede añadir o editar segmentos para un destino de servidor a servidor ([!DNL S2S]). No puede crear destinos [!DNL S2S] con [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md). Póngase en contacto con el consultor para configurar destinos [!DNL S2S]. Siga estas instrucciones para agregar o editar segmentos para un destino [!DNL S2S].

<!-- destination-s2s-edit.xml -->

Para añadir o editar asignaciones de segmentos para un destino [!DNL S2S]:

1. Vaya a **[!UICONTROL Audience Data > Destinations]**. Seleccione **Plataformas integradas > Basadas en dispositivos** y busque el destino [!DNL S2S] con el que desea trabajar.
2. En la columna [!UICONTROL Action] , haga clic en el icono de lápiz para editar el destino.
   * En el cuadro **[!UICONTROL Search and Add Segments]**, empiece a escribir el nombre de un segmento o haga clic en **[!UICONTROL Browse All Segments]** examinar una lista de segmentos disponibles.
   * Haga clic en **[!UICONTROL Add Selected Segments]** cuando encuentre el segmento que desee utilizar. Al agregar un segmento, se abre la ventana [!UICONTROL Edit Mapping].
   * En [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Establezca un valor para el valor  [clave ](../../features/destinations/key-value-pairs.md) asociado con este destino.
      * **[!UICONTROL Start Date]** y  **[!UICONTROL End Date]**: Elija una fecha de inicio y de finalización para el destino. Si la fecha de finalización está en blanco, el destino nunca caduca.
3. Haga clic en **[!UICONTROL Save]** y, a continuación, en **[!UICONTROL Done]**.
