---
description: Puede enviar segmentos calificados a Google Ad Manager mediante una integración de lado del cliente o de explorador del lado del servidor. Si elige la integración lado del cliente, debe crear un destino basado en cookie para las etiquetas de editor de Google en Audience Manager.
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
ht-degree: 1%

---

# Crear un destino GPT {#create-a-gpt-destination}

Puede enviar segmentos calificados a [!DNL Google Ad Manager] través de una integración de lado del cliente (lado explorador) o una integración de del lado del servidor. Si elige la lado del cliente integración, deberá crear un destino basado en cookie para [!DNL Google Publisher Tags] Audience Manager.

## Destinos

En Audience Manager, a es cualquier *`destination`* otro sistema (servidor de anuncios, [!DNL DSP], red de anuncios, etc.) con el que se quiera compartir datos. [!UICONTROL Destination Builder] proporciona las herramientas que le permiten crear y administrar estos procesos de envío datos. Audience Manager características de destino se encuentran en *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Para comenzar, haga clic **[!UICONTROL Add New Destination]** y seguir los pasos a continuación.

## Información básica

Para completar la [!UICONTROL Basic Information] sección:

1. Asigne un nombre al destino.
1. Seleccione **[!UICONTROL "Cookie"]** en la [!UICONTROL Type] lista desplegable.
1. Haga clic **[!UICONTROL Next]** y vaya a las [!UICONTROL Configuration] secciones y [!UICONTROL Segment Mappings] .

## Configuración de cookie

Proporcione lo siguiente para completar la [!UICONTROL Configuration] sección (otros campos son opcionales):

1. **Nombre de la cookie:** proporcione un breve nombre descriptivo para su cookie.
1. **Formato de datos:** seleccione la **[!UICONTROL "Single Key"]** opción.
1. **Clave:** proporcione un nombre de clave.
1. **Serializar:** seleccione la casilla de **[!UICONTROL Enable]** verificación.
1. **Delimitador de serie:** Utilice solo una coma.

## Asignaciones de segmentos

Para agregar un segmento a un destino cookie:

1. Buscar segmentos: La [!UICONTROL Segment Mappings] sección proporciona dos herramientas búsqueda para ayudarle a localizar segmentos. Para encontrar una segmento:

   * Opción 1: Inicio escribir un nombre de segmento en el campo búsqueda. El campo se actualiza automáticamente en función del texto introducido. Haga clic **[!UICONTROL Add]** una vez que encuentre el segmento desea utilizar.
   * Opción 2: Haga clic **[!UICONTROL Browse All Segments]** para abrir una ventana que le permita buscar segmentos por nombre o ubicación almacenamiento. Haga clic **[!UICONTROL Add Selected Segments]** cuando termine.

1. **añadir asignaciones:** En la ventana emergente Asignaciones, introduzca el ID de segmento en el campo Asignaciones y haga clic en **[!UICONTROL Save]**.

1. Haga clic en **[!UICONTROL Done]**.
