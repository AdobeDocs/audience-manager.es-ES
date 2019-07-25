---
description: Puede enviar segmentos cualificados a DFP mediante una integración del lado del cliente (lado del explorador) o una integración del lado del servidor. Si elige la integración del lado del cliente, debe crear un destino basado en cookies para etiquetas de Google Publisher en Audience Manager.
seo-description: Puede enviar segmentos cualificados a DFP mediante una integración del lado del cliente (lado del explorador) o una integración del lado del servidor. Si elige la integración del lado del cliente, debe crear un destino basado en cookies para etiquetas de Google Publisher en Audience Manager.
seo-title: Crear un destino GPT
solution: Audience Manager
title: Crear un destino GPT
uuid: e 3 bbf 327-a 7 e 0-48 da-bc 84-8 f 531 b 7 f 6750
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Create a GPT Destination {#create-a-gpt-destination}

You can send qualified segments to [!DNL DFP] through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for [!DNL Google Publisher Tags] in Audience Manager.

## Destinos

In Audience Manager, a *`destination`* is any other system (ad server, [!DNL DSP], ad network, etc.) a los que desee compartir datos. [!UICONTROL Destination Builder] proporciona las herramientas que permiten crear y administrar estos procesos de entrega de datos. Audience Manager destination features are located in *[!UICONTROL Audience Data]&gt;[!UICONTROL Destinations]*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

## Información básica

To complete the [!UICONTROL Basic Information] section:

1. Asigne un nombre al destino.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Click **[!UICONTROL Next]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

## Configuración de cookie

Provide the following to complete the [!UICONTROL Configuration] section (other fields are optional):

1. **Nombre de la cookie:** Proporcione un nombre corto y descriptivo para la cookie.
1. **Formato de datos:** Seleccione la **[!UICONTROL "Single Key"]** opción.
1. **Clave:** Proporcione un nombre de clave.
1. **Serializar:** Seleccione la casilla de **[!UICONTROL Enable]** verificación.
1. **Delimitador de serie:** Utilice sólo una coma.

## Asignaciones de segmentos

Para agregar un segmento a un destino de cookie:

1. Find segments: The [!UICONTROL Segment Mappings] section provides two search tools to help locate segments. Para encontrar un segmento:

   * Opción 1: Empiece a escribir un nombre de segmento en el campo de búsqueda. El campo se actualiza automáticamente en función del texto introducido. Click **[!UICONTROL Add]** once you find the segment you want to use.
   * Option 2: Click **[!UICONTROL Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL Add Selected Segments]** when done.

1. **Agregar asignaciones:** En las asignaciones pop, introduzca el ID de segmento en el campo Asignaciones y haga clic **[!UICONTROL Save]** en.

1. Haga clic en **[!UICONTROL Done]**.