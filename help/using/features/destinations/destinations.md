---
description: 'Descubra las ventajas, tipos y usos de los destinos: cualquier sistema de terceros, como un servidor de publicidad o DSP, en que comparte datos. Utilice Destination Builder para crear y administrar destinos de servidor a servidor, direcciones URL o cookies.'
keywords: código de integración, destino, descripción general de destino, destino, destino, destino, destino, destino, destino, destino, destino, destino, destino, destino
landing-page-description: 'Descubra las ventajas, tipos y usos de los destinos: cualquier sistema de terceros, como un servidor de publicidad o DSP, en que comparte datos. Utilice Destination Builder para crear y administrar destinos de servidor a servidor, direcciones URL o cookies.'
seo-title: Destinations
solution: Audience Manager
title: Destinos
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 865800eb076811db38aec8e98714ad9712804f77
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 15%

---

# [!UICONTROL Destinations] Información general {#destinations}

En Audience Manager, un [!UICONTROL destination] es cualquier sistema de terceros (servidor de publicidad, [!DNL DSP], red de publicidad, etc.) con el que se desea compartir datos. [!UICONTROL Destination Builder] es la herramienta que se ha utilizado para crear y administrar [!UICONTROL cookie], [!DNL URL]o [!UICONTROL server-to-server destinations].

## Finalidad y ventajas {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] y [!UICONTROL Destination Builder] permite crear [!UICONTROL destinations] y enviar información sobre usuarios segmentados a su socio de datos. Esto le ayuda a:

* **Valor de datos de Protect:** En lugar de enviar todos los datos de usuario a un [!UICONTROL destination], [!UICONTROL Destination Builder] permite compartir información específica sobre usuarios cualificados únicamente.
* **Realice acciones con sus datos:** Envío de datos a un [!UICONTROL destination] partner les ayuda a desarrollar y segmentar rápidamente segmentos de audiencia cualificados.
* **Reduzca la sobrecarga técnica:** Los usuarios empresariales pueden configurar [!UICONTROL destinations] de forma segura en el [!UICONTROL Destination Builder] interfaz. Esto ayuda a reducir el tiempo necesario para las pruebas previas a la implementación. con [!UICONTROL Destination Builder], cree, administre y elimine [!UICONTROL destinations] a medida que cambien sus necesidades comerciales, todo sin tener que pasar por un largo ciclo de desarrollo.

## Consideraciones técnicas {#technical-considerations}

<!-- destination-delivery-methods.xml -->

La entrega de datos depende de cómo desee o pueda recibir su socio de datos [!UICONTROL destination] información. Las limitaciones técnicas o de ingeniería pueden impedir que [!UICONTROL destination] desde la recepción de datos a través de [!DNL URL], [!UICONTROL cookie]o [!UICONTROL server-to-server] procesos. Póngase en contacto con su socio de terceros para determinar qué método pueden utilizar.

## Consideraciones empresariales {#business-considerations}

Las decisiones comerciales para seleccionar un método de envío en lugar de otro dependen de las capacidades técnicas de su [!UICONTROL destination] y lo que desea hacer con la información de usuario cualificada. Por ejemplo, las restricciones técnicas pueden limitar las opciones si [!UICONTROL destination] no puede recibir datos por un método de envío determinado. Sin embargo, si no hay problemas técnicos, puede enviar información en función de cómo desee realizar acciones con esos datos. Por ejemplo:

* [!DNL URL]s y [!UICONTROL cookie-based destinations] trabajar casi sincrónicamente con acciones del usuario en una página.
* [!UICONTROL Server-to-server] Los métodos son adecuados para generar segmentos de audiencia profundos a lo largo del tiempo.

## [!UICONTROL Destination] Tipos y usos típicos {#destination-types}

Los ejemplos de la tabla siguiente pueden ayudarle a comprender cuándo utilizar un [!UICONTROL destination] y las diferencias entre cada tipo.

| [!UICONTROL Destination] Escriba | Normalmente se utiliza cuando | Ejemplo | Consideraciones |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Debe enviar datos a otras soluciones de Adobe Experience Cloud. | Envío de datos a Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Debe enviar segmentos de audiencia a entornos basados en personas, como Facebook. | Entrega de ofertas personalizadas a clientes existentes, según su historial de compras | La segmentación de audiencias se realiza mediante identificadores hash. Consulte [Destinos basados en personas](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Servidor a servidor**) | <ul><li>No se requiere la transferencia inmediata de datos.</li><li>Recopilación de datos para crear un gran grupo de audiencias de usuarios cualificados.</li></ul> | Recopilación de datos a lo largo del tiempo (horas o días) para utilizarlos en una campaña configurada para ejecutarse en una fecha posterior. | <ul><li>Transfiere datos sobre visitantes nuevos y anteriores al sitio. </li><li>No es necesario volver a ver a los visitantes para poder pertenecer a otros segmentos.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** o **Cookie**) | Debe transferir los datos inmediatamente para que un destino pueda realizar acciones en un usuario cualificado de inmediato. | Envío de datos desde un sitio de compra de entradas. Utilice un [!UICONTROL URL] o [!UICONTROL cookie destination] para calificar al usuario y volver a dirigirse inmediatamente. | <ul><li>Transfiere únicamente datos sobre visitantes nuevos. </li><li>Se debe volver a ver a los visitantes para que cumplan los requisitos del segmento.</li></ul> |
