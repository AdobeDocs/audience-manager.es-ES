---
description: En Audience Manager, un destino es cualquier sistema de terceros (servidor de publicidad, DSP, red de publicidad, etc.) con el que se desea compartir datos. El Generador de destinos es la herramienta que se utiliza para crear y administrar destinos de cookie, URL o servidor a servidor.
keywords: código de integración, destino, descripción general de destino, destino, destino, destino, destino, destino, destino, destino, destino, destino, destino, destino
landing-page-description: Un destino es cualquier sistema de terceros, como un servidor de anuncios o DSP, con el que se comparten datos. Utilice Destination Builder para crear y administrar destinos de servidor a servidor, direcciones URL o cookies.
seo-title: 'Destinos '
solution: Audience Manager
title: Destinos
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Conceptos básicos de destino
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 15%

---

# [!UICONTROL Destinations] Información general {#destinations}

En Audience Manager, [!UICONTROL destination] es cualquier sistema de terceros (servidor de publicidad, [!DNL DSP], red de publicidad, etc.) con el que se desea compartir datos. [!UICONTROL Destination Builder] es la herramienta que se utiliza para crear y administrar  [!UICONTROL cookie],  [!DNL URL] o  [!UICONTROL server-to-server destinations].

## Finalidad y ventajas {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] y  [!UICONTROL Destination Builder] permiten crear  [!UICONTROL destinations] y enviar información sobre usuarios segmentados a su socio de datos. Esto le ayuda a:

* **Valor de datos de Protect:** en lugar de enviar todos los datos de usuario a un  [!UICONTROL destination],  [!UICONTROL Destination Builder] permite compartir información específica solo sobre usuarios cualificados.
* **Tome medidas sobre los datos:** el envío de datos a un  [!UICONTROL destination] socio les ayuda a desarrollar y segmentar rápidamente segmentos de audiencia cualificados.
* **Reducir la sobrecarga técnica:** los usuarios empresariales pueden configurarse de  [!UICONTROL destinations] forma segura en la  [!UICONTROL Destination Builder] interfaz. Esto ayuda a reducir el tiempo necesario para las pruebas previas a la implementación. Con [!UICONTROL Destination Builder], usted crea, administra y elimina [!UICONTROL destinations] a medida que cambian sus necesidades comerciales, todo sin tener que pasar por un largo ciclo de desarrollo.

## Consideraciones técnicas {#technical-considerations}

<!-- destination-delivery-methods.xml -->

El envío de datos depende de cómo el socio de datos desee o pueda recibir la información [!UICONTROL destination]. Las restricciones técnicas o de ingeniería pueden impedir que un [!UICONTROL destination] reciba datos a través de procesos [!DNL URL], [!UICONTROL cookie] o [!UICONTROL server-to-server]. Póngase en contacto con su socio de terceros para determinar qué método pueden utilizar.

## Consideraciones empresariales {#business-considerations}

Las decisiones comerciales para seleccionar un método de envío en lugar de otro dependen de las capacidades técnicas de su socio [!UICONTROL destination] y de lo que desee hacer con la información de usuario calificada. Por ejemplo, las restricciones técnicas pueden limitar las opciones si un [!UICONTROL destination] no puede recibir datos por un método de envío determinado. Sin embargo, si no hay problemas técnicos, puede enviar información en función de cómo desee realizar acciones con esos datos. Por ejemplo:

* [!DNL URL]y  [!UICONTROL cookie-based destinations] trabajan casi sincrónicamente con las acciones del usuario en una página.
* [!UICONTROL Server-to-server] Los métodos son adecuados para generar segmentos de audiencia profundos a lo largo del tiempo.

## [!UICONTROL Destination] Tipos y usos típicos  {#destination-types}

Los ejemplos de la tabla siguiente pueden ayudarle a comprender cuándo utilizar un [!UICONTROL destination] concreto y las diferencias entre cada tipo.

| [!UICONTROL Destination] Escriba | Normalmente se utiliza cuando | Ejemplo | Consideraciones |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Debe enviar datos a otras soluciones de Adobe Experience Cloud. | Envío de datos a Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Debe enviar segmentos de audiencia a entornos basados en personas, como Facebook. | Entrega de ofertas personalizadas a clientes existentes, según su historial de compras | La segmentación de audiencias se realiza mediante identificadores hash. Consulte [People-Based Destinations](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Servidor a servidor**) | <ul><li>No se requiere la transferencia inmediata de datos.</li><li>Recopilación de datos para crear un gran grupo de audiencias de usuarios cualificados.</li></ul> | Recopilación de datos a lo largo del tiempo (horas o días) para utilizarlos en una campaña configurada para ejecutarse en una fecha posterior. | <ul><li>Transfiere datos sobre visitantes nuevos y anteriores al sitio. </li><li>No es necesario volver a ver a los visitantes para poder pertenecer a otros segmentos.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**** URLo  **cookie**) | Debe transferir los datos inmediatamente para que un destino pueda realizar acciones en un usuario cualificado de inmediato. | Envío de datos desde un sitio de compra de entradas. Use [!UICONTROL URL] o [!UICONTROL cookie destination] para calificar al usuario y volver a dirigirse inmediatamente. | <ul><li>Transfiere únicamente datos sobre visitantes nuevos. </li><li>Se debe volver a ver a los visitantes para que cumplan los requisitos del segmento.</li></ul> |
