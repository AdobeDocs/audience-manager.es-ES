---
description: Alrededor del 14 de octubre de 2019, noté que las poblaciones de características integradas para el gráfico de ID de dispositivo habían caído a 0, donde anteriormente eran mucho más altas.
seo-description: Alrededor del 14 de octubre de 2019, noté que las poblaciones de características integradas para el gráfico de ID de dispositivo habían caído a 0, donde anteriormente eran mucho más altas.
seo-title: ¿Por qué las poblaciones de características integradas cayeron a 0 alrededor del 15 de octubre?
solution: Audience Manager
title: ¿Por qué las poblaciones de características integradas cayeron a 0 alrededor del 15 de octubre?
translation-type: tm+mt
source-git-commit: eb129bbf642cb666ce3ea05ff606c051e02f4d1e

---


# ¿Por qué las poblaciones de características integradas cayeron a 0 alrededor del 15 de octubre? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

Alrededor del 14 de octubre de 2019, noté que las poblaciones de características integradas para el gráfico de ID de dispositivo habían caído a 0, donde anteriormente eran mucho más altas.

![Imagen de la colocación del ID del dispositivo](/help/using/support-issues/assets/device_id_populationdrop.png)

**Respuesta**

El 15 de octubre, se cambió una actualización de la funcionalidad de regla de combinación de perfiles de Audience Manager a la que ya no se realizan comparaciones de los identificadores de dispositivo con los datos integrados con un ID de CRM cargado en una fuente de datos entre dispositivos.  Anteriormente, Audience Manager se estaba realizando con el ID entre dispositivos (o el ID de CRM), así como copiando estas realizaciones en los UUID de Audience Manager (ID de dispositivo) asociados.  El cambio se realizó para reflejar con mayor precisión la naturaleza de los datos de características y los perfiles que se están realizando.

Para ver las realizaciones de características, seleccione la opción &quot;ID entre dispositivos&quot; en la lista desplegable situada en la esquina superior derecha de la vista de características.

![Ver las realizaciones por ID de varios dispositivos](/help/using/support-issues/assets/deviceid-crossdevice.png)

