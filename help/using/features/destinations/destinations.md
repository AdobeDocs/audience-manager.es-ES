---
description: En Audience Manager, un destino es cualquier sistema de terceros (servidor de publicidad, DSP, red de publicidad, etc.) con el que se desea compartir datos. Utilice la herramienta Generador de destinos para crear y administrar destinos de cookie, URL o servidor a servidor.
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: En Audience Manager, un destino es cualquier sistema de terceros (servidor de publicidad, DSP, red de publicidad, etc.) con el que se desea compartir datos. El Generador de destinos es la herramienta que se utiliza para crear y administrar destinos de cookie, URL o servidor a servidor.
seo-title: 'Destinos '
solution: Audience Manager
title: 'Destinos '
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
translation-type: tm+mt
source-git-commit: 8027f278aa2b879b6cb277f44caf4b62dc75e2c3
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 6%

---


# [!UICONTROL Destinations] Información general {#destinations}

En Audience Manager, [!UICONTROL destination] es un sistema de terceros (servidor de publicidad, [!DNL DSP]red de publicidad, etc.) con el que se desea compartir datos. [!UICONTROL Destination Builder] es la herramienta que se utiliza para crear y administrar [!UICONTROL cookie], [!DNL URL]o [!UICONTROL server-to-server destinations].

## Propósito y ventajas {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] y [!UICONTROL Destination Builder] permite crear [!UICONTROL destinations] y enviar información sobre usuarios segmentados a su socio de datos. Esto le ayuda a:

* **Valor de datos de Protect:** En lugar de enviar todos los datos de usuario a un [!UICONTROL destination], [!UICONTROL Destination Builder] permite compartir información específica sobre usuarios cualificados únicamente.
* **Tome medidas sobre sus datos:** El envío de datos a un [!UICONTROL destination] socio les ayuda a desarrollar y destinatario rápidamente segmentos de audiencia cualificados.
* **Reduzca el overhead técnico:** Los usuarios empresariales pueden realizar la configuración [!UICONTROL destinations] de forma segura en la [!UICONTROL Destination Builder] interfaz. Esto ayuda a reducir el tiempo necesario para las pruebas previas a la implementación. Con [!UICONTROL Destination Builder], usted crea, administra y elimina [!UICONTROL destinations] a medida que cambian sus necesidades comerciales, todo sin tener que trabajar a través de un largo ciclo de desarrollo.

## Consideraciones técnicas {#technical-considerations}

<!-- destination-delivery-methods.xml -->

El envío de datos depende de cómo el socio de datos desee o pueda recibir [!UICONTROL destination] información. Las restricciones técnicas o de ingeniería pueden impedir que un [!UICONTROL destination] usuario reciba datos a través [!DNL URL], [!UICONTROL cookie]o [!UICONTROL server-to-server] procesos. Póngase en contacto con su socio de terceros para determinar qué método pueden utilizar.

## Consideraciones empresariales {#business-considerations}

Las decisiones comerciales para seleccionar un método de envío sobre otro dependen de las capacidades técnicas de su [!UICONTROL destination] socio y de lo que desee hacer con la información de usuario cualificada. Por ejemplo, las restricciones técnicas pueden limitar las opciones si un [!UICONTROL destination] usuario no puede recibir datos mediante un método de envío determinado. Sin embargo, si no hay problemas técnicos, puede enviar información en función de cómo desee tomar medidas en relación con esos datos. Por ejemplo:

* [!DNL URL]y [!UICONTROL cookie-based destinations] trabajar de forma casi sincrónica con las acciones del usuario en una página.
* [!UICONTROL Server-to-server] los métodos son adecuados para generar segmentos de audiencia profunda con el paso del tiempo.

## [!UICONTROL Destination] Tipos y usos típicos {#destination-types}

Los ejemplos de la tabla siguiente pueden ayudarle a comprender cuándo usar un determinado [!UICONTROL destination] y las diferencias entre cada tipo.

| [!UICONTROL Destination] Escriba | Normalmente se utiliza cuando | Ejemplo | Consideraciones |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Debe enviar datos a otras soluciones de Adobe Experience Cloud. | Envío de datos a Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Debe enviar segmentos de audiencia a entornos basados en personas, como Facebook. | Entregar ofertas personalizadas a los clientes existentes, según su historial de compras | La segmentación de audiencias se realiza mediante identificadores con hash. Consulte Destinos basados en [personas](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Servidor a servidor**) | <ul><li>No se requiere la transferencia inmediata de datos.</li><li>Recopilación de datos para crear un gran grupo de audiencias de usuarios cualificados.</li></ul> | Recopilación de datos a lo largo del tiempo (horas o días) para usarlos en una campaña configurada para ejecutarse en una fecha posterior. | <ul><li>Transfiere datos sobre visitantes del sitio nuevos y anteriores. </li><li>No es necesario volver a ver los visitantes para poder acceder a otros segmentos.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** o **cookie**) | Debe transferir los datos inmediatamente para que un destino pueda actuar en forma inmediata sobre un usuario cualificado. | Envío de datos desde un sitio de compra de entradas. Use un [!UICONTROL URL] o [!UICONTROL cookie destination] para calificar al usuario y volver a realizar el destinatario inmediatamente. | <ul><li>Solo transfiere datos sobre nuevos visitantes. </li><li>Se deben volver a ver los visitantes para poder optar al segmento.</li></ul> |
