---
description: El Sistema de informes de uso de Actividades le ayuda a realizar la vista y el seguimiento del uso de actividades de su instancia de Administrador de Audiencias, para que pueda comparar el uso real con el compromiso contractual.
keywords: activity, usage, reporting, commitment
seo-description: El Sistema de informes de uso de Actividades le ayuda a realizar la vista y el seguimiento del uso de actividades de su instancia de Administrador de Audiencias, para que pueda comparar el uso real con el compromiso contractual.
seo-title: Sistema de informes de uso de Actividades
solution: Audience Manager
title: Sistema de informes de uso de Actividades
topic: Activity Usage Reporting
translation-type: tm+mt
source-git-commit: 75fe1e0f7321107930a28e354ca2f4a256a477ac

---


# Sistema de informes de uso de Actividades

## Información general {#overview}

Esto [!UICONTROL Activity Usage Report] le ayuda a realizar la vista y el seguimiento del uso de la actividad de su instancia de Administrador de Audiencias, lo que le ofrece una idea clara de cómo se compara el uso de la actividad con su compromiso contractual.

Además, puede descargar el archivo [!UICONTROL Activity Usage Report] cuando lo necesite, para el mantenimiento de registros y la análisis personalizada.

## Consideraciones {#considerations}

El [!UICONTROL Activity Usage Report] está disponible para todos los usuarios del Administrador de Audiencias con privilegios [de administrador](edit-account-settings.md).

>[!IMPORTANT]
>
>La [!UICONTROL Activity Usage Report] muestra las estadísticas de uso de actividades de la instancia del Administrador de Audiencias. Para cualquier consulta de facturación relacionada con el uso de su actividad, póngase en contacto con su representante de Adobe.

## Casos de uso {#use-cases}

Existen dos casos de uso principales de [!UICONTROL Activity Usage Report]:

* **Rastrear el uso real de la actividad de instancias en relación con el compromiso** de uso de la actividad: La mayoría de los clientes tiene un compromiso de actividad mensual estimado por instancia del Administrador de Audiencias, que luego se acumula en un compromiso de actividad anual en todos los casos. Aunque este informe no es un informe de facturación, puede proporcionar una guía útil para saber si está excediendo el uso de actividad comprometido.
* **Validación de los cambios** de implementación: Si ha actualizado recientemente la implementación, como la configuración del reenvío de servidor de Analytics o el cambio de la configuración de llamadas al servidor de Destinatario, este informe puede ayudarle a comprobar si el nuevo volumen de actividad está en consonancia con el volumen de actividad esperado.

## Uso del informe Uso de Actividades {#using}

Para ver el [!UICONTROL Activity Usage Report], inicie sesión en su cuenta del Administrador de Audiencias y vaya a **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

A continuación, utilice el **[!UICONTROL Reporting Interval]** filtro para seleccionar el intervalo de tiempo para el cual generar el informe. Puede elegir entre 30, 60, 90 días o un intervalo de fechas personalizado.

Una vez que se cargue el informe, podrá ver un desglose del informe [!UICONTROL Activities] para el período seleccionado.

[!UICONTROL Activities] defina el total acumulado de todas las interacciones en el sitio y fuera del sitio con el Administrador de Audiencias, dividido en las siguientes categorías:

* **[!UICONTROL Server Calls]**:: Cualquier evento de recopilación o recuperación de datos enviado al Administrador de Audiencias desde sitios web, servidores, correo electrónico, aplicaciones móviles u otros sistemas.
* **[!UICONTROL Pixel Calls](anteriormente conocido como[!UICONTROL Impression Server Calls])**: Datos recopilados de anuncios (como volumen de impresión de una plataforma de objetivo) o llamadas de impresión por correo electrónico realizadas al Administrador de Audiencias. Requieren la presencia del`d_event`parámetro en la cadena de consulta.
* **[!UICONTROL On-Boarded Records]**:: Registros únicos ingeridos desde su propio sistema de administración de la relación con los clientes (CRM) u otros archivos de datos sin conexión, como registros de centros de llamadas, ID de dispositivos y fuentes de datos personalizadas de proveedores de datos externos.
* **[!UICONTROL Log File Records]**:: Registros únicos de archivos de registro ingeridos en el Administrador de Audiencias desde una plataforma de objetivo.

>[!NOTE]
>
>Un registro único define cada registro individual de datos de un archivo almacenado por Adobe en nombre de un cliente de Audiencia Manager.

Además, puede utilizar los tipos de gráficos para cambiar entre dos tipos de gráficos. [!UICONTROL Activity Usage Trends]

![aur-ui-graphics](assets/aur-ui-graphs.png)

También puede situar el cursor sobre una fecha específica en la línea de tiempo para ver el uso detallado de esa fecha.

![aur-hover](assets/aur-hover.png)

## Exportación de informes de uso de Actividades {#export}

Para obtener una mejor descripción general del nivel de uso de la actividad del Administrador de Audiencias, puede exportar la variable en función del tipo de registros que desee incluir [!UICONTROL Activity Usage Report] .

![aur-export](assets/aur-export.png)

Los informes **[!UICONTROL Onboarded Records Breakdown]** y **[!UICONTROL Onsite Server Calls Breakdown]** proporcionan la perspectiva más granular de los datos de origen disponibles para estas actividades. El volumen atribuido a estos desgloses se basa en la implementación.

### Desglose de registros integrados {#onboarded-breakdown}

Este informe contiene registros incorporados desglosados por fuente de datos.

### Desglose de llamadas al servidor en el sitio {#onsite-breakdown}

Este informe contiene un desglose de las llamadas al servidor de tres fuentes: [!UICONTROL Analytics], [!UICONTROL Target], y [!UICONTROL Other].

* **[!UICONTROL Analytics]**:: Son llamadas al servidor facturables que se pasan de todas las instancias de Adobe Analytics al Administrador de Audiencias, incluido el reenvío del lado del servidor. Las llamadas secundarias al servidor o las llamadas al servidor de duplicado (como en el caso del reenvío del lado del servidor desde varios grupos de informes) no son actividades facturables, por lo que no se incluyen en este desglose.
* **[!UICONTROL Target]**:: Son llamadas del lado del servidor desde Adobe Destinatario al Administrador de Audiencias para recuperar datos de segmentos del Administrador de Audiencias como parte de una integración servidor a servidor.
* **[!UICONTROL Other]**:: Incluye llamadas desde cualquier otro sitio web o sistema (sitios de socios, llamadas directas al servidor, etc.), llamadas de navegador/aplicación móviles a través de [!DNL SDK], [!DNL DIL], llamadas de evento y [!DNL DCS] llamadas. También incluye llamadas desde [!DNL Target] si se configuran como una integración de cookies (en lugar de servidor a servidor).
