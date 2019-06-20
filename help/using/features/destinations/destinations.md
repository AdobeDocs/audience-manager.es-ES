---
description: En Audience Manager, un destino es cualquier sistema de terceros (servidor de publicidad, DSP, red de publicidad, etc.) a los que desee compartir datos. Generador de destino es la herramienta que utilizó para crear y administrar las cookies, la URL o los destinos servidor a servidor.
keywords: código de integración, destino, visión general de destino
seo-description: En Audience Manager, un destino es cualquier sistema de terceros (servidor de publicidad, DSP, red de publicidad, etc.) a los que desee compartir datos. Generador de destino es la herramienta que utilizó para crear y administrar las cookies, la URL o los destinos servidor a servidor.
seo-title: Destinos
solution: Audience Manager
title: Destinos
uuid: 5 c 7 dbdec-f 73 f -46 fe -9 f 12-7685 e 8 d 7334 f
translation-type: tm+mt
source-git-commit: 157e70906b80bd0a23ba6e7721d2c456d378ffb5

---


# Destinos {#destinations}

In Audience Manager, a destination is any third-party system (ad server, [!DNL DSP], ad network, etc.) a los que desee compartir datos. [!UICONTROL Destination Builder] es la herramienta que utilizó para crear y administrar [!DNL URL]destinos de servidor a servidor.

## Purpose and Advantages {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] y [!UICONTROL Destination Builder] permite crear destinos y enviar información acerca de los usuarios segmentados a su socio de datos. Esto le ayuda a:

* **Proteger valor de datos:** En lugar de enviar todos los datos de usuario a un destino, [!UICONTROL Destination Builder] le permiten compartir información específica sobre usuarios cualificados.
* **Tome medidas en los datos:** El envío de datos a un socio de destino ayuda a desarrollar y dirigirse rápidamente a segmentos de audiencia cualificados.
* **Reducir la sobrecarga técnica:** Los usuarios comerciales pueden configurar destinos de forma segura en [!UICONTROL Destination Builder] la interfaz. Esto ayuda a reducir el tiempo necesario para las pruebas previas a la implementación. With [!UICONTROL Destination Builder], you create, manage, and delete destinations as your business needs change, all without working through a long development cycle.

## Consideraciones técnicas {#technical-considerations}

<!-- destination-delivery-methods.xml -->

La entrega de datos depende de cómo desee el socio de datos, o puede, recibir información de destino. Technical or engineering constraints may prevent a destination from receiving data via [!DNL URL], cookie, or server-to-server processes. Trabaje con su socio de terceros para determinar qué método pueden utilizar.

## Consideraciones empresariales {#business-considerations}

Las decisiones comerciales para seleccionar un método de entrega sobre otro dependen de las capacidades técnicas de su socio de destino y lo que se desee hacer con la información de usuario cualificada. Por ejemplo, las restricciones técnicas pueden limitar las opciones si un destino no puede recibir datos por un método de entrega concreto. Sin embargo, si no hay problemas técnicos, puede enviar información en función de cómo desee realizar acciones en relación con esos datos. Por ejemplo:

* [!DNL URL]los destinos basados en cookies y s funcionan casi sincrónicamente con acciones de usuario en una página.
* Los métodos de servidor a servidor son buenos para crear segmentos de audiencia profundos con el paso del tiempo.

## Destination Types and Typical Uses {#destination-types}

Los ejemplos de la tabla siguiente pueden ayudarle a comprender cuándo utilizar un destino concreto y las diferencias entre cada tipo.

| Tipo de destino | Generalmente se utiliza cuando | Ejemplo | Consideraciones |
|--- |--- |--- |--- |
| **Dirección URL** o **cookie** | Es necesario transferir los datos inmediatamente para que un destino pueda realizar acciones en un usuario cualificado inmediatamente. | Envío de datos desde un sitio de compras. Utilice una dirección URL o un destino de cookie para calificar al usuario y volver a dirigirse inmediatamente. | <ul><li>Transfiere sólo los datos sobre visitantes nuevos. </li><li>Se debe volver a ver a los visitantes para que puedan optar al segmento.</li></ul> |
| **Servidor a servidor** | <ul><li>No se requiere transferencia inmediata de datos.</li><li>Recopilación de datos para crear un gran grupo de audiencias de usuarios cualificados.</li></ul> | Recopilar datos a lo largo del tiempo (horas o días) para usarlos en una campaña configurada para ejecutarse posteriormente. | <ul><li>Transfiere datos sobre visitantes nuevos y anteriores del sitio. </li><li>No es necesario volver a ver a los visitantes para que puedan optar a otros segmentos.</li></ul> |
