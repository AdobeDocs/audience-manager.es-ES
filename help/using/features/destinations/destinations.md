---
description: En Audience Manager, un destino es cualquier sistema de terceros (servidor de publicidad, DSP, red de publicidad, etc.) que desea compartir datos con. El Generador de destinos es la herramienta que se utiliza para crear y administrar destinos de cookie, URL o servidor a servidor.
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: En Audience Manager, un destino es cualquier sistema de terceros (servidor de publicidad, DSP, red de publicidad, etc.) que desea compartir datos con. El Generador de destinos es la herramienta que se utiliza para crear y administrar destinos de cookie, URL o servidor a servidor.
seo-title: Destinos
solution: Audience Manager
title: Destinos
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
translation-type: tm+mt
source-git-commit: 431a254f1a70958db29621a59acc6239d2a6b005

---


# Descripción general de destinos {#destinations}

En Audience Manager, un destino es cualquier sistema de terceros (servidor de publicidad, [!DNL DSP], red de publicidad, etc.) que desea compartir datos con. [!UICONTROL Destination Builder] es la herramienta utilizada para crear y administrar cookies [!DNL URL]o destinos de servidor a servidor.

## Propósito y ventajas {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] y [!UICONTROL Destination Builder] permite crear destinos y enviar información sobre usuarios segmentados a su socio de datos. Esto le ayuda a:

* **** Proteger valor de datos: En lugar de enviar todos los datos de usuario a un destino, [!UICONTROL Destination Builder] permita compartir información específica solo sobre usuarios cualificados.
* **** Tome medidas sobre sus datos: El envío de datos a un socio de destino les ayuda a desarrollar y dirigir rápidamente segmentos de audiencia cualificados.
* **** Reduzca el overhead técnico: Los usuarios empresariales pueden configurar destinos de forma segura en la [!UICONTROL Destination Builder] interfaz. Esto ayuda a reducir el tiempo necesario para las pruebas previas a la implementación. Con [!UICONTROL Destination Builder], puede crear, administrar y eliminar destinos a medida que cambian las necesidades comerciales, todo ello sin tener que pasar por un largo ciclo de desarrollo.

## Consideraciones técnicas {#technical-considerations}

<!-- destination-delivery-methods.xml -->

La entrega de datos depende de cómo el socio de datos desee o pueda recibir la información de destino. Las restricciones técnicas o de ingeniería pueden impedir que un destino reciba datos a través de procesos [!DNL URL]de cookie o de servidor a servidor. Póngase en contacto con su socio de terceros para determinar qué método pueden utilizar.

## Consideraciones empresariales {#business-considerations}

Las decisiones comerciales para seleccionar un método de entrega sobre otro dependen de las capacidades técnicas de su socio de destino y de lo que desee hacer con la información de usuario cualificada. Por ejemplo, las restricciones técnicas pueden limitar las opciones si un destino no puede recibir datos mediante un método de entrega determinado. Sin embargo, si no hay problemas técnicos, puede enviar información en función de cómo desee tomar medidas en relación con esos datos. Por ejemplo:

* [!DNL URL]Los destinos basados en cookies y s funcionan casi sincrónicamente con las acciones del usuario en una página.
* Los métodos de servidor a servidor son adecuados para generar segmentos de audiencia profundos con el paso del tiempo.

## Tipos de destino y usos típicos {#destination-types}

Los ejemplos de la tabla siguiente pueden ayudarle a saber cuándo usar un destino determinado y las diferencias entre cada tipo.

| Tipo de destino | Normalmente se utiliza cuando | Ejemplo | Consideraciones |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Debe enviar datos a otras soluciones de Adobe Experience Cloud. | Envío de datos a Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Debe enviar segmentos de audiencia a entornos basados en personas, como Facebook. | Entregar ofertas personalizadas a los clientes existentes, según su historial de compras | La segmentación de audiencia se realiza mediante identificadores con hash. Consulte Destinos basados en [personas](people-based-destinations-overview.md) |
| **[!UICONTROL Device-Based Destinations]**(** Servidor a servidor **) | <ul><li>No se requiere la transferencia inmediata de datos.</li><li>Recopilación de datos para crear un gran grupo de audiencias de usuarios cualificados.</li></ul> | Recopilación de datos a lo largo del tiempo (horas o días) para usarlos en una campaña configurada para ejecutarse en una fecha posterior. | <ul><li>Transfiere datos sobre los visitantes nuevos y anteriores al sitio. </li><li>No es necesario volver a ver a los visitantes para poder acceder a otros segmentos.</li></ul> |
| **[!UICONTROL Custom Destinations]**(** URL **o** cookie **) | Debe transferir los datos inmediatamente para que un destino pueda actuar en forma inmediata sobre un usuario cualificado. | Envío de datos desde un sitio de compra de entradas. Use una dirección URL o un destino de cookie para calificar al usuario y volver a segmentar inmediatamente. | <ul><li>Transfiere solamente datos sobre visitantes nuevos. </li><li>Se debe volver a ver a los visitantes para que califiquen para el segmento.</li></ul> |

