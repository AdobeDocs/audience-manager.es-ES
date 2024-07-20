---
description: Puede enviar segmentos cualificados a Google Ad Manager mediante una integración del lado del cliente (lado del explorador) o una integración del lado del servidor. Si elige la integración del lado del cliente, debe crear un destino basado en cookies para las etiquetas de Google Publisher en Audience Manager.
seo-description: You can send qualified segments to Google Ad Manager through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for Google Publisher Tags in Audience Manager.
seo-title: Create a GPT Destination
solution: Audience Manager
title: Crear un destino GPT
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third-party Integration
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 3%

---

# Crear un destino GPT {#create-a-gpt-destination}

Puede enviar segmentos calificados a [!DNL Google Ad Manager] mediante una integración del lado del cliente (lado del explorador) o una integración del lado del servidor. Si elige la integración del lado del cliente, debe crear un destino basado en cookies para [!DNL Google Publisher Tags] en el Audience Manager.

## Destinos

En el Audience Manager, *`destination`* es cualquier otro sistema (servidor de publicidad, [!DNL DSP], red de publicidad, etc.) con el que se desea compartir datos. [!UICONTROL Destination Builder] proporciona las herramientas que le permiten crear y administrar estos procesos de entrega de datos. Las características de destino de Audience Manager se encuentran en *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Para comenzar, haga clic en **[!UICONTROL Add New Destination]** y siga los pasos a continuación.

## Información básica

Para completar la sección [!UICONTROL Basic Information]:

1. Nombre el destino.
1. Seleccione **[!UICONTROL "Cookie"]** de la lista desplegable [!UICONTROL Type].
1. Haga clic en **[!UICONTROL Next]** y continúe con las secciones [!UICONTROL Configuration] y [!UICONTROL Segment Mappings].

## Configuración de cookies

Proporcione lo siguiente para completar la sección [!UICONTROL Configuration] (los demás campos son opcionales):

1. **Nombre de cookie:** Proporcione un nombre corto y descriptivo para su cookie.
1. **Formato de datos:** Seleccione la opción **[!UICONTROL "Single Key"]**.
1. **Clave:** Proporcione un nombre de clave.
1. **Serializar:** Seleccione la casilla **[!UICONTROL Enable]**.
1. **Delimitador de serie:** Use solo una coma.

## Asignaciones de segmentos

Para añadir un segmento a un destino de cookie:

1. Buscar segmentos: La sección [!UICONTROL Segment Mappings] proporciona dos herramientas de búsqueda para ayudar a localizar segmentos. Para buscar un segmento:

   * Opción 1: Empiece a escribir un nombre de segmento en el campo de búsqueda. El campo se actualiza automáticamente en función del texto introducido. Haga clic en **[!UICONTROL Add]** cuando encuentre el segmento que desea utilizar.
   * Opción 2: haga clic en **[!UICONTROL Browse All Segments]** para abrir una ventana que le permita buscar segmentos por nombre o ubicación de almacenamiento. Haga clic en **[!UICONTROL Add Selected Segments]** cuando termine.

1. **Agregar asignaciones:** En la ventana emergente de asignaciones, escriba el identificador del segmento en el campo de asignaciones y haga clic en **[!UICONTROL Save]**.

1. Haga clic en **[!UICONTROL Done]**.
