---
description: Alrededor del 14 de octubre de 2019, noté que las poblaciones de características integradas para el gráfico de ID de dispositivo habían caído a 0, donde anteriormente eran mucho más altas.
seo-description: Alrededor del 14 de octubre de 2019, noté que las poblaciones de características integradas para el gráfico de ID de dispositivo habían caído a 0, donde anteriormente eran mucho más altas.
seo-title: ¿Por qué las poblaciones de características integradas cayeron a 0 alrededor del 15 de octubre?
solution: Audience Manager
title: ¿Por qué las poblaciones de características integradas cayeron a 0 alrededor del 15 de octubre?
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---


# ¿Por qué las poblaciones de características integradas cayeron a 0 alrededor del 15 de octubre? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

## pregunta

Alrededor del 14 de octubre de 2019, noté que las poblaciones de características integradas para el gráfico de ID de dispositivo habían caído a 0, donde anteriormente eran mucho más altas. ¿Por qué pasó esto?

![Imagen de la colocación del ID del dispositivo](assets/device_id_populationdrop.png)

## Respuesta

El 15 de octubre, se cambió una actualización de la funcionalidad de la regla de combinación de Perfiles de Audience Manager a la que ya no se realizan comparaciones de los identificadores de dispositivo con los datos incorporados con un ID de CRM cargado en una fuente de datos entre dispositivos.  Anteriormente, el Audience Manager se estaba dando cuenta tanto del ID entre dispositivos (o ID de CRM) como de la copia de esas realizaciones en los UUID de Audience Manager (ID de dispositivo) asociados.  El cambio se realizó para reflejar con mayor precisión la naturaleza de los datos de características y los perfiles que se están obteniendo.

Para vista de las realizaciones de características, seleccione la opción &quot;ID entre dispositivos&quot; en la lista desplegable situada en la esquina superior derecha de la vista de características.

![Realizaciones de Vista por ID de varios dispositivos](assets/deviceid-crossdevice.png)