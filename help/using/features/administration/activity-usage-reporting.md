---
description: Los informes de uso de actividades le ayudan a ver y rastrear el uso de la actividad de su instancia de Audience Manager, para que pueda comparar el uso real con su compromiso contractual.
keywords: activity, usage, reporting, commitment
seo-description: Los informes de uso de actividades le ayudan a ver y rastrear el uso de la actividad de su instancia de Audience Manager, para que pueda comparar el uso real con su compromiso contractual.
seo-title: Informes de uso de actividades
solution: Audience Manager
title: Informes de uso de actividades
topic: Activity Usage Reporting
translation-type: tm+mt
source-git-commit: 7a3914af8fb225508f57724a75fe2547aac3f241

---


# Informes de uso de actividades

## Información general {#overview}

Esto [!UICONTROL Activity Usage Report] le ayuda a ver y rastrear el uso de la actividad de su instancia de Audience Manager, lo que le ofrece una idea clara de cómo se compara el uso de la actividad con el compromiso contractual.

Además, puede descargar el [!UICONTROL Activity Usage Report] archivo cuando lo necesite para el mantenimiento de registros y el análisis personalizado.

## Consideraciones {#considerations}

El [!UICONTROL Activity Usage Report] está disponible para todos los usuarios de Audience Manager con privilegios [de](edit-account-settings.md)administrador.

> [!IMPORTANT]
>
> La muestra [!UICONTROL Activity Usage Report] las estadísticas de uso de la actividad de la instancia de Audience Manager. Para cualquier consulta de facturación relacionada con el uso de su actividad, póngase en contacto con su representante de Adobe.

## Casos de uso {#use-cases}

Existen dos casos de uso principales de [!UICONTROL Activity Usage Report]:

* **Rastrear el uso de la actividad de instancia real en relación con el compromiso** de uso de la actividad: La mayoría de los clientes tiene un compromiso de actividad mensual estimado por instancia de Audience Manager, que luego se acumula en un compromiso de actividad anual en todos los casos. Aunque este informe no es un informe de facturación, puede proporcionar una guía útil sobre si está superando el uso de la actividad comprometida.
* **Validación de los cambios** de implementación: Si ha actualizado recientemente la implementación, como la configuración del reenvío de servidor de Analytics o el cambio de la configuración de la llamada al servidor de Target, este informe le ayudará a comprobar si el nuevo volumen de actividad está en línea con el volumen de actividad esperado.

## Uso del informe Uso de la actividad {#using}

Para ver el [!UICONTROL Activity Usage Report], inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]**>**[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

A continuación, utilice el **[!UICONTROL Reporting Interval]**filtro para seleccionar el intervalo de tiempo para el cual generar el informe. Puede elegir entre 30, 60, 90 días o un intervalo de fechas personalizado.

Una vez que se cargue el informe, podrá ver un desglose del informe [!UICONTROL Activities] para el período seleccionado.

[!UICONTROL Activities] defina el total agregado de todas las interacciones en el sitio y fuera de él con Audience Manager, divididas en las siguientes categorías:

* **[!UICONTROL Server Calls]**:: Cualquier evento de recuperación o recopilación de datos enviado a Audience Manager desde sitios web, servidores, correo electrónico, aplicaciones móviles u otros sistemas.
* **[!UICONTROL Pixel Calls](anteriormente conocido como[!UICONTROL Impression Server Calls])**: Datos recopilados de anuncios (como volumen de impresión de una plataforma de segmentación) o llamadas de impresión por correo electrónico realizadas a Audience Manager. Requieren la presencia del `d_event` parámetro en la cadena de consulta.
* **[!UICONTROL On-Boarded Records]**:: Registros únicos ingeridos desde su propio sistema de administración de la relación con los clientes (CRM) u otros archivos de datos sin conexión, como registros de centros de llamadas, ID de dispositivos y fuentes de datos personalizadas de proveedores de datos externos.
* **[!UICONTROL Log File Records]**:: Registros únicos de archivos de registro ingeridos en Audience Manager desde una plataforma de segmentación.

> [!NOTE]
> Un registro único define cada registro individual de datos de un archivo almacenado por Adobe en nombre de un cliente de Audience Manager.

Además, puede utilizar los tipos de gráficos [!UICONTROL Activity Usage Trends] para cambiar entre dos tipos de gráficos.

![aur-ui-graphics](assets/aur-ui-graphs.png)

También puede situar el cursor sobre una fecha específica en la línea de tiempo para ver el uso detallado de esa fecha.

![aur-hover](assets/aur-hover.png)

## Exportación de informes de uso de actividades {#export}

Para obtener una mejor descripción general del nivel de uso de la actividad de Audience Manager, puede exportar los registros [!UICONTROL Activity Usage Report] en función del tipo de registros que desee incluir.

![aur-export](assets/aur-export.png)

Los informes **[!UICONTROL Onboarded Records Breakdown]**y**[!UICONTROL Onsite Server Calls Breakdown]** proporcionan la perspectiva más granular de los datos de origen disponibles para estas actividades. El volumen atribuido a estos desgloses se basa en la implementación.

### Desglose de registros integrados {#onboarded-breakdown}

Este informe contiene registros incorporados desglosados por fuente de datos.

### Desglose de llamadas al servidor en el sitio {#onsite-breakdown}

Este informe contiene un desglose de las llamadas al servidor de tres fuentes: [!UICONTROL Analytics], [!UICONTROL Target], y [!UICONTROL Other].

* **[!UICONTROL Analytics]**:: Son llamadas al servidor facturables que se pasan de todas las instancias de Adobe Analytics a Audience Manager, incluido el reenvío del lado del servidor. Las llamadas secundarias al servidor o las llamadas duplicadas al servidor (como en el caso del reenvío del lado del servidor desde varios grupos de informes) no son actividades facturables, por lo que no se incluyen en este desglose.
* **[!UICONTROL Target]**:: Son llamadas del lado del servidor de Adobe Target a Audience Manager para recuperar datos de segmentos de Audience Manager como parte de una integración servidor a servidor.
* **[!UICONTROL Other]**:: Incluye llamadas desde cualquier otro sitio web o sistema (sitios de socios, llamadas directas al servidor, etc.), llamadas de navegador o aplicación móvil a través de la[!DNL SDK],[!DNL DIL], llamadas de evento y[!DNL DCS]llamadas. También incluye llamadas desde[!DNL Target]si se configuran como una integración de cookies (en lugar de servidor a servidor).
