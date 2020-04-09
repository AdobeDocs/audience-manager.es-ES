---
description: Alrededor del 14 de octubre de 2019, noté que las poblaciones de características integradas para el gráfico de ID de dispositivo habían caído a 0, donde anteriormente eran mucho más altas.
seo-description: Alrededor del 14 de octubre de 2019, noté que las poblaciones de características integradas para el gráfico de ID de dispositivo habían caído a 0, donde anteriormente eran mucho más altas.
seo-title: ¿Por qué las poblaciones de características integradas cayeron a 0 alrededor del 15 de octubre?
solution: Audience Manager
title: ¿Por qué las poblaciones de características integradas cayeron a 0 alrededor del 15 de octubre?
translation-type: tm+mt
source-git-commit: 0487a15c5fcd0e653bedf0e7fd8326f5cc363660

---


# ¿Por qué las poblaciones de características integradas cayeron a 0 alrededor del 15 de octubre? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

## pregunta

Alrededor del 14 de octubre de 2019, noté que las poblaciones de características integradas para el gráfico de ID de dispositivo habían caído a 0, donde anteriormente eran mucho más altas. ¿Por qué pasó esto?

![Imagen de la colocación del ID del dispositivo](assets/device_id_populationdrop.png)

## Respuesta

El 15 de octubre, se cambió una actualización de la funcionalidad de regla de combinación de Perfiles del Administrador de Audiencias a la que ya no se realizan comparaciones entre los identificadores de dispositivo con los datos incorporados de un ID de CRM cargado en una fuente de datos de varios dispositivos.  Anteriormente, el Administrador de Audiencias se estaba realizando con el ID entre dispositivos (o el ID de CRM), así como copiando esas realizaciones en los UUID del Administrador de Audiencias (ID de dispositivo) asociados.  El cambio se realizó para reflejar con mayor precisión la naturaleza de los datos de características y los perfiles que se están obteniendo.

Para vista de las realizaciones de características, seleccione la opción &quot;ID entre dispositivos&quot; en la lista desplegable situada en la esquina superior derecha de la vista de características.

![Realizaciones de Vista por ID de varios dispositivos](assets/deviceid-crossdevice.png)