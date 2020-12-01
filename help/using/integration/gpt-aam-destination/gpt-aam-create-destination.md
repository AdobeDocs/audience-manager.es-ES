---
description: Puede enviar segmentos cualificados a Google Ad Manager mediante una integración de cliente (de lado del explorador) o de servidor. Si elige la integración del lado del cliente, debe crear un destino basado en cookies para Google Publisher Tags en Audience Manager.
seo-description: Puede enviar segmentos cualificados a Google Ad Manager mediante una integración de cliente (de lado del explorador) o de servidor. Si elige la integración del lado del cliente, debe crear un destino basado en cookies para Google Publisher Tags en Audience Manager.
seo-title: Crear un destino GPT
solution: Audience Manager
title: Crear un destino GPT
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 7%

---


# Crear un destino GPT {#create-a-gpt-destination}

Puede enviar segmentos calificados a [!DNL Google Ad Manager] mediante una integración del lado del cliente (del navegador) o de servidor. Si elige la integración del lado del cliente, debe crear un destino basado en cookies para [!DNL Google Publisher Tags] en Audience Manager.

## Destinos 

En Audience Manager, un *`destination`* es cualquier otro sistema (servidor de publicidad, [!DNL DSP], red de publicidad, etc.) con el que se desea compartir datos. [!UICONTROL Destination Builder] proporciona las herramientas que permiten crear y administrar estos procesos de envío de datos. Las características de destino de Audience Manager se encuentran en *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Para comenzar, haga clic en **[!UICONTROL Add New Destination]** y siga los pasos a continuación.

## Información básica

Para completar la sección [!UICONTROL Basic Information]:

1. Asigne un nombre al destino.
1. Seleccione **[!UICONTROL "Cookie"]** en la lista desplegable [!UICONTROL Type].
1. Haga clic en **[!UICONTROL Next]** y pase a las secciones [!UICONTROL Configuration] y [!UICONTROL Segment Mappings].

## Configuración de cookies

Proporcione lo siguiente para completar la sección [!UICONTROL Configuration] (otros campos son opcionales):

1. **Nombre de la cookie:** proporcione un nombre corto y descriptivo para la cookie.
1. **Formato de datos:** seleccione la  **[!UICONTROL "Single Key"]** opción.
1. **Clave:** proporcione un nombre de clave.
1. **Serializar:** seleccione la  **[!UICONTROL Enable]** casilla de verificación.
1. **Delimitador serie:** utilice una coma únicamente.

## Asignaciones de segmentos

Para agregar un segmento a un destino de cookie:

1. Buscar segmentos: La sección [!UICONTROL Segment Mappings] proporciona dos herramientas de búsqueda para ayudar a localizar segmentos. Para encontrar un segmento:

   * Opción 1: Inicio que escribe el nombre de un segmento en el campo de búsqueda. El campo se actualiza automáticamente en función del texto introducido. Haga clic **[!UICONTROL Add]** una vez que encuentre el segmento que desee utilizar.
   * Opción 2: Haga clic **[!UICONTROL Browse All Segments]** para abrir una ventana que le permite buscar segmentos por nombre o ubicación de almacenamiento. Haga clic en **[!UICONTROL Add Selected Segments]** cuando termine.

1. **Añadir asignaciones:** en la ventana emergente de asignaciones, introduzca el ID de segmento en el campo de asignaciones y haga clic en  **[!UICONTROL Save]**.

1. Haga clic **[!UICONTROL Done]**.