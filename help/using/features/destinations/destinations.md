---
description: En Audience Manager, un destino es cualquier sistema de terceros (servidor de publicidad, DSP, red de publicidad, etc.) a los que desee compartir datos. Generador de destino es la herramienta que utilizó para crear y administrar las cookies, la URL o los destinos servidor a servidor.
keywords: código de integración, destino, información general de destino, destino, destino, destino, destino, destino, destino, destino, destino, destino, destino, destino
seo-description: En Audience Manager, un destino es cualquier sistema de terceros (servidor de publicidad, DSP, red de publicidad, etc.) a los que desee compartir datos. Generador de destino es la herramienta que utilizó para crear y administrar las cookies, la URL o los destinos servidor a servidor.
seo-title: Destinos
solution: Audience Manager
title: Destinos
uuid: 5 c 7 dbdec-f 73 f -46 fe -9 f 12-7685 e 8 d 7334 f
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Información general de destinos {#destinations}

En Audience Manager, un destino es cualquier sistema de terceros (servidor de publicidad, [!DNL DSP]red de publicidad, etc.) a los que desee compartir datos. [!UICONTROL Destination Builder] es la herramienta que utilizó para crear y administrar [!DNL URL]destinos de servidor a servidor.

## Propósito y ventajas {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] y [!UICONTROL Destination Builder] permite crear destinos y enviar información acerca de los usuarios segmentados a su socio de datos. Esto le ayuda a:

* **Proteger valor de datos:** En lugar de enviar todos los datos de usuario a un destino, [!UICONTROL Destination Builder] le permiten compartir información específica sobre usuarios cualificados.
* **Tome medidas en los datos:** El envío de datos a un socio de destino ayuda a desarrollar y dirigirse rápidamente a segmentos de audiencia cualificados.
* **Reducir la sobrecarga técnica:** Los usuarios comerciales pueden configurar destinos de forma segura en [!UICONTROL Destination Builder] la interfaz. Esto ayuda a reducir el tiempo necesario para las pruebas previas a la implementación. Con [!UICONTROL Destination Builder]ellas, se crean, administran y eliminan destinos a medida que cambian sus necesidades comerciales, sin necesidad de trabajar a través de un ciclo de desarrollo largo.

## Consideraciones técnicas {#technical-considerations}

<!-- destination-delivery-methods.xml -->

La entrega de datos depende de cómo desee el socio de datos, o puede, recibir información de destino. Las restricciones técnicas o de ingeniería pueden impedir que un destino reciba datos a través [!DNL URL]de procesos, cookies o procesos servidor a servidor. Trabaje con su socio de terceros para determinar qué método pueden utilizar.

## Consideraciones empresariales {#business-considerations}

Las decisiones comerciales para seleccionar un método de entrega sobre otro dependen de las capacidades técnicas de su socio de destino y lo que se desee hacer con la información de usuario cualificada. Por ejemplo, las restricciones técnicas pueden limitar las opciones si un destino no puede recibir datos por un método de entrega concreto. Sin embargo, si no hay problemas técnicos, puede enviar información en función de cómo desee realizar acciones en relación con esos datos. Por ejemplo:

* [!DNL URL]los destinos basados en cookies y s funcionan casi sincrónicamente con acciones de usuario en una página.
* Los métodos de servidor a servidor son buenos para crear segmentos de audiencia profundos con el paso del tiempo.

## Tipos de destino y usos típicos {#destination-types}

Los ejemplos de la tabla siguiente pueden ayudarle a comprender cuándo utilizar un destino concreto y las diferencias entre cada tipo.

| Tipo de destino | Generalmente se utiliza cuando | Ejemplo | Consideraciones |
|--- |--- |--- |--- |
| **Dirección URL** o **cookie** | Es necesario transferir los datos inmediatamente para que un destino pueda realizar acciones en un usuario cualificado inmediatamente. | Envío de datos desde un sitio de compras. Utilice una dirección URL o un destino de cookie para calificar al usuario y volver a dirigirse inmediatamente. | <ul><li>Transfiere sólo los datos sobre visitantes nuevos. </li><li>Se debe volver a ver a los visitantes para que puedan optar al segmento.</li></ul> |
| **Servidor a servidor** | <ul><li>No se requiere transferencia inmediata de datos.</li><li>Recopilación de datos para crear un gran grupo de audiencias de usuarios cualificados.</li></ul> | Recopilar datos a lo largo del tiempo (horas o días) para usarlos en una campaña configurada para ejecutarse posteriormente. | <ul><li>Transfiere datos sobre visitantes nuevos y anteriores del sitio. </li><li>No es necesario volver a ver a los visitantes para que puedan optar a otros segmentos.</li></ul> |
