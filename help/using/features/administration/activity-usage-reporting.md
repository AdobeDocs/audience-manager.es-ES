---
description: El Sistema de informes de uso de actividades le ayuda a realizar la vista y el seguimiento del uso de actividades para su instancia de Audience Manager, para que pueda comparar el uso real con el compromiso contractual.
keywords: activity, usage, reporting, commitment
seo-description: El Sistema de informes de uso de actividades le ayuda a realizar la vista y el seguimiento del uso de actividades para su instancia de Audience Manager, para que pueda comparar el uso real con el compromiso contractual.
seo-title: Informes de uso de actividades
solution: Audience Manager
title: Informes de uso de actividades
topic: Activity Usage Reporting
feature: Usage and Billing
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 6%

---


# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## Información general {#overview}

[!UICONTROL Activity Usage Report] le ayuda a realizar la vista y el seguimiento del uso de la actividad de su instancia de Audience Manager, lo que le ofrece una idea clara de cómo se compara el uso de la actividad con su compromiso contractual.

Además, puede descargar el [!UICONTROL Activity Usage Report] cuando lo necesite, para el mantenimiento de registros y la análisis personalizada.

## Consideraciones {#considerations}

El [!UICONTROL Activity Usage Report] está disponible para todos los usuarios Audience Manager con [privilegios de administrador](edit-account-settings.md).

>[!IMPORTANT]
>
>El [!UICONTROL Activity Usage Report] muestra las estadísticas de uso de actividades de la instancia de Audience Manager. Para cualquier consulta de facturación relacionada con el uso de su actividad, póngase en contacto con su representante de Adobes.

## Casos de uso {#use-cases}

Existen dos casos de uso principales de [!UICONTROL Activity Usage Report]:

* **Rastrear el uso real de la actividad de instancias en relación con el compromiso** de uso de la actividad: La mayoría de los clientes tiene un compromiso de actividad mensual estimado por instancia de Audience Manager, que luego se acumula en un compromiso de actividad anual en todos los casos. Aunque este informe no es un informe de facturación, puede proporcionar una guía útil para saber si está excediendo el uso de actividad comprometido.
* **Validación de los cambios** de implementación: Si ha actualizado recientemente la implementación, como la configuración del reenvío del lado del  [!DNL Adobe Analytics] servidor o el cambio de la configuración de llamadas al  [!DNL Adobe Target] servidor, este informe puede ayudarle a comprobar si el nuevo volumen de actividad está en línea con el volumen de actividad esperado.

## Cuando se usaba la identificación [!UICONTROL Activity Usage Report] {#using}

Para ver el [!UICONTROL Activity Usage Report], inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

A continuación, utilice el filtro **[!UICONTROL Reporting Interval]** para seleccionar el intervalo de tiempo para el cual generar el informe. Puede elegir entre 30, 60, 90 días o un intervalo de fechas personalizado.

Una vez cargado el informe, puede ver un desglose de su [!UICONTROL Activities] para el período seleccionado.

[!UICONTROL Activities] defina el total acumulado de todas las interacciones in situ y fuera de la web con el Audience Manager, dividido en las siguientes categorías:

* **[!UICONTROL Server Calls]**:: Cualquier evento de recopilación o recuperación de datos enviado al Audience Manager desde sitios web, servidores, correo electrónico, aplicaciones móviles u otros sistemas.
* **[!UICONTROL Pixel Calls](anteriormente conocido como  [!UICONTROL Impression Server Calls])**: Datos recopilados de anuncios (como volumen de impresión de una plataforma de objetivo) o llamadas de impresión por correo electrónico realizadas al Audience Manager. Requieren la presencia del parámetro `d_event` en la cadena de consulta.
* **[!UICONTROL On-Boarded Records]**:: Registros únicos ingeridos desde su propio sistema de administración de la relación con los clientes (CRM) u otros archivos de datos sin conexión, como registros de centros de llamadas, ID de dispositivos y fuentes de datos personalizadas de proveedores de datos externos.
* **[!UICONTROL Log File Records]**:: Registros únicos de archivos de registro ingeridos en Audience Manager desde una plataforma de segmentación.

>[!NOTE]
>
>Un registro único define cada registro individual de datos en un archivo almacenado por Adobe en nombre de un cliente Audience Manager.

Además, puede utilizar los tipos de gráficos [!UICONTROL Activity Usage Trends] para cambiar entre dos tipos de gráficos.

![aur-ui-graphics](assets/aur-ui-graphs.png)

También puede situar el cursor sobre una fecha específica en la línea de tiempo para ver el uso detallado de esa fecha.

![aur-hover](assets/aur-hover.png)

## Exportando [!UICONTROL Activity Usage Reports] {#export}

Para obtener una mejor descripción general del nivel de uso de la actividad de Audience Manager, puede exportar el [!UICONTROL Activity Usage Report] en función del tipo de registros que desee incluir.

![aur-export](assets/aur-export.png)

Los informes **[!UICONTROL Onboarded Records Breakdown]** y **[!UICONTROL Onsite Server Calls Breakdown]** proporcionan la perspectiva más granular de los datos de origen disponibles para estas actividades. El volumen atribuido a estos desgloses se basa en la implementación.

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

Este informe contiene registros incorporados desglosados por fuente de datos.

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

Este informe contiene un desglose de las llamadas al servidor de tres fuentes: [!UICONTROL Analytics], [!UICONTROL Target] y [!UICONTROL Other].

* **[!UICONTROL Analytics]**:: Son llamadas al servidor facturables que se pasan de todas  [!UICONTROL Adobe Analytics] las instancias al Audience Manager, incluido el reenvío del lado del servidor. Las llamadas secundarias al servidor o las llamadas al servidor de duplicado (como en el caso del reenvío del lado del servidor desde varios grupos de informes) no son actividades facturables, por lo que no se incluyen en este desglose.
* **[!UICONTROL Target]**:: Son llamadas del lado del servidor  [!UICONTROL Adobe Target] al Audience Manager para recuperar datos de segmentos de Audience Manager como parte de una integración servidor a servidor.
* **[!UICONTROL Other]**:: Incluye llamadas desde cualquier otro sitio web o sistema (sitios de socios, llamadas directas al servidor, etc.), llamadas de navegador/aplicación móviles a través de  [!DNL SDK],  [!DNL DIL], llamadas de evento y  [!DNL DCS] llamadas. También incluye llamadas desde [!DNL Target] si se configuran como una integración de cookies (en lugar de servidor a servidor).
