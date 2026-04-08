---
description: Puede enviar segmentos cualificados a Google Ad Manager mediante una integración del lado del cliente (lado del explorador) o una integración del lado del servidor. Si elige la integración del lado del cliente, debe crear un destino basado en cookies para las etiquetas de Google Publisher en Audience Manager.
seo-description: You can send qualified segments to Google Ad Manager through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for Google Publisher Tags in Audience Manager.
seo-title: Create a GPT Destination
solution: Audience Manager
title: Crear un destino GPT
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third-party Integration
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
TQID: https://experienceleague.adobe.com/v24OVLvNGPvqASZ4CPh2xbBgVcXZNCitCBM76nUXRsE
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2:
  - id: e7029888-c8b0-46a7-849a-cf132a1559bf
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 284
ht-degree: 1%

---

# Crear un destino GPT {#create-a-gpt-destination}

Puede enviar segmentos calificados a [!DNL Google Ad Manager] mediante una integración del lado del cliente (lado del explorador) o una integración del lado del servidor. Si elige la integración del lado del cliente, debe crear un destino basado en cookies para [!DNL Google Publisher Tags] en Audience Manager.

## Destinos

En Audience Manager, *`destination`* es cualquier otro sistema (servidor de publicidad, [!DNL DSP], red de publicidad, etc.) con el que desee compartir datos. [!UICONTROL Destination Builder] proporciona las herramientas que le permiten crear y administrar estos procesos de entrega de datos. Las características de destino de Audience Manager se encuentran en *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Para comenzar, haga clic en **[!UICONTROL Add New Destination]** y siga los pasos a continuación.

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
