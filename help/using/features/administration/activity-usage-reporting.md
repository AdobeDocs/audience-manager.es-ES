---
description: La Creación de informes de uso de actividades le ayuda a realizar la vista y el seguimiento del uso de la actividad de su instancia de Audience Manager, lo que le permite comparar el uso real con la asignación contractual.
keywords: actividad, uso, creación de informes, asignación
seo-description: Activity Usage Reporting helps you view and track the activity usage for your Audience Manager instance, so you can compare your actual usage to your contractual commitment.
seo-title: Activity Usage Reporting
solution: Audience Manager
title: Informes de uso de actividades
feature: Usage and Billing
exl-id: 0c5f04c6-d008-4817-9c67-cd39350b3aaf
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 5%

---

# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## Información general {#overview}

[!UICONTROL Activity Usage Report] le ayuda a realizar la vista y el seguimiento del uso de la actividad de su instancia de Audience Manager, lo que le ofrece una idea clara de cómo se compara el uso de la actividad con su compromiso contractual.

Además, puede descargar [!UICONTROL Activity Usage Report] siempre que lo necesite, para mantener registros y realizar análisis personalizados.

## Consideraciones {#considerations}

[!UICONTROL Activity Usage Report] está disponible para todos los usuarios Audience Manager con [privilegios de administrador](edit-account-settings.md).

>[!IMPORTANT]
>
>[!UICONTROL Activity Usage Report] le muestra las estadísticas de uso de actividad de su instancia de Audience Manager. Para cualquier consulta de facturación relacionada con el uso de su actividad, póngase en contacto con su representante de Adobe.

## Casos de uso {#use-cases}

Hay dos casos de uso principales de [!UICONTROL Activity Usage Report]:

* **Seguimiento del uso real de la actividad de la instancia con respecto a su asignación de uso de la actividad**: la mayoría de los clientes tienen una asignación de actividad estimada mensual por Audience Manager, que luego se acumula en una asignación de actividad anual en todas las instancias. Aunque este informe no es un informe de facturación, puede proporcionar una guía útil para saber si está excediendo el uso de la actividad comprometida.
* **Validación para cambios de implementación**: Si ha actualizado recientemente su implementación, como la configuración de [!DNL Adobe Analytics] reenvío del lado del servidor o el cambio de la configuración de llamadas al servidor [!DNL Adobe Target], este informe puede ayudarle a comprobar si el nuevo volumen de actividad está en línea con el volumen de actividad esperado.

## Usando [!UICONTROL Activity Usage Report] {#using}

Para ver [!UICONTROL Activity Usage Report], inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

A continuación, utilice el filtro **[!UICONTROL Reporting Interval]** para seleccionar el intervalo de tiempo para el que generar el informe. Puede elegir entre 30, 60 o 90 días, o un intervalo de fechas personalizado.

Una vez que se cargue el informe, podrá ver un desglose de su [!UICONTROL Activities] durante el período seleccionado.

[!UICONTROL Activities] define el total agregado de todas las interacciones en el sitio y fuera del sitio con el Audience Manager, dividido en las siguientes categorías:

* **[!UICONTROL Server Calls]**: cualquier evento de recopilación o recuperación de datos enviado al Audience Manager desde sitios web, servidores, correo electrónico, aplicaciones móviles u otros sistemas.
* **[!UICONTROL Pixel Calls](anteriormente conocido como [!UICONTROL Impression Server Calls])**: datos recopilados de anuncios (como el volumen de impresiones de una plataforma de segmentación) o llamadas de impresión de correo electrónico realizadas al Audience Manager. Estos requieren la presencia del parámetro `d_event` en la cadena de consulta.
* **[!UICONTROL On-Boarded Records]**: registros únicos ingeridos desde su propio sistema de administración de la relación con los clientes (CRM) u otros archivos de datos sin conexión, como registros del centro de llamadas, ID de dispositivo y fuentes de datos personalizadas de proveedores de datos externos.
* **[!UICONTROL Log File Records]**: registros únicos de archivos de registro ingeridos en el Audience Manager desde una plataforma de segmentación.

>[!NOTE]
>
>Un registro único define cada registro individual de datos en un archivo almacenado por Adobe en nombre de un cliente Audience Manager.

Además, puede usar los tipos de gráficos [!UICONTROL Activity Usage Trends] para cambiar entre dos tipos de gráficos.

![aur-ui-graphics](assets/aur-ui-graphs.png)

También puede situar el cursor sobre una fecha específica en la cronología para ver el uso detallado de esa fecha.

![aur-hover](assets/aur-hover.png)

## Exportando [!UICONTROL Activity Usage Reports] {#export}

Para obtener una mejor descripción general del nivel de uso de la actividad del Audience Manager, puede exportar [!UICONTROL Activity Usage Report] según el tipo de registros que desee incluir.

![aur-export](assets/aur-export.png)

Los informes **[!UICONTROL Onboarded Records Breakdown]** y **[!UICONTROL Onsite Server Calls Breakdown]** proporcionan la perspectiva más granular de los datos de origen disponibles para estas actividades. El volumen atribuido a estos desgloses se basa en la implementación.

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

Este informe contiene registros incorporados desglosados por fuente de datos.

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

Este informe contiene un desglose de llamadas al servidor desde tres orígenes: [!UICONTROL Analytics], [!UICONTROL Target] y [!UICONTROL Other].

* **[!UICONTROL Analytics]**: estas son llamadas facturables al servidor pasadas desde todas las instancias de [!UICONTROL Adobe Analytics] al Audience Manager, incluido el reenvío del lado del servidor. Las llamadas secundarias al servidor o las llamadas duplicadas al servidor (como en el caso del reenvío del lado del servidor desde varios grupos de informes) no son actividades facturables, por lo que no se incluyen en este desglose.
* **[!UICONTROL Target]**: son llamadas del lado del servidor de [!UICONTROL Adobe Target] al Audience Manager para recuperar datos de segmentos del Audience Manager como parte de una integración servidor a servidor.
* **[!UICONTROL Other]**: incluye llamadas de cualquier otro sitio web o sistema (sitios de socios, llamadas directas al servidor, etc.), llamadas de navegador/aplicación móvil a través de [!DNL SDK], [!DNL DIL], llamadas de evento y llamadas de [!DNL DCS]. También incluye llamadas de [!DNL Target] si se configura como una integración de cookies (en lugar de servidor a servidor).
