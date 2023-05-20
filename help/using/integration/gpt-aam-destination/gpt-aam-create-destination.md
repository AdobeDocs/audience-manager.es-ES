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
source-wordcount: '282'
ht-degree: 6%

---

# Crear un destino GPT {#create-a-gpt-destination}

Puede enviar segmentos cualificados a [!DNL Google Ad Manager] mediante una integración del lado del cliente (lado del explorador) o una integración del lado del servidor. Si elige la integración de cliente, debe crear un destino basado en cookies para [!DNL Google Publisher Tags] en Audience Manager.

## Destinos 

En Audience Manager, una *`destination`* es cualquier otro sistema (servidor de publicidad, [!DNL DSP], red de anuncios, etc.) con el que se desea compartir datos. [!UICONTROL Destination Builder] proporciona las herramientas que le permiten crear y administrar estos procesos de entrega de datos. Las funciones de destino de Audience Manager se encuentran en *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Para empezar, haga clic en **[!UICONTROL Add New Destination]** y siga los pasos a continuación.

## Información básica

Para completar la [!UICONTROL Basic Information] sección:

1. Nombre el destino.
1. Seleccionar **[!UICONTROL "Cookie"]** desde el [!UICONTROL Type] lista desplegable.
1. Clic **[!UICONTROL Next]** y continúe con la [!UICONTROL Configuration] y [!UICONTROL Segment Mappings] secciones.

## Configuración de cookies

Proporcione lo siguiente para completar la [!UICONTROL Configuration] (los demás campos son opcionales):

1. **Nombre de la cookie:** Proporcione un nombre corto y descriptivo para la cookie.
1. **Formato de datos:** Seleccione el **[!UICONTROL "Single Key"]** opción.
1. **Clave:** Proporcione un nombre de clave.
1. **Serializar:** Seleccione el **[!UICONTROL Enable]** casilla de verificación
1. **Delimitador de serie:** Utilice solo una coma.

## Asignaciones de segmentos

Para añadir un segmento a un destino de cookie:

1. Buscar segmentos: La [!UICONTROL Segment Mappings] Esta sección proporciona dos herramientas de búsqueda para localizar segmentos. Para buscar un segmento:

   * Opción 1: Empiece a escribir un nombre de segmento en el campo de búsqueda. El campo se actualiza automáticamente en función del texto introducido. Clic **[!UICONTROL Add]** una vez que encuentre el segmento que desea utilizar.
   * Opción 2: clic **[!UICONTROL Browse All Segments]** para abrir una ventana que le permita buscar segmentos por nombre o ubicación de almacenamiento. Clic **[!UICONTROL Add Selected Segments]** cuando termine.

1. **Agregar asignaciones:** En la ventana emergente de asignaciones, introduzca el ID de segmento en el campo de asignaciones y haga clic en **[!UICONTROL Save]**.

1. Haga clic **[!UICONTROL Done]**.
