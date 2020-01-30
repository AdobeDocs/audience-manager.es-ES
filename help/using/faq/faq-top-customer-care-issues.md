---
description: Esta página incluye los principales problemas notificados al Servicio de atención al cliente de Audience Manager.
seo-description: Esta página incluye los principales problemas notificados al Servicio de atención al cliente de Audience Manager.
seo-title: 'Atención al cliente: problemas informados con mayor frecuencia'
solution: Audience Manager
title: 'Atención al cliente: problemas informados con mayor frecuencia'
translation-type: tm+mt
source-git-commit: f9d57da86b7e8962353b01b693a2359cade7b024

---


# Atención al cliente: problemas informados con mayor frecuencia{#most-frequent-issues}

Esta página incluye los principales problemas notificados al Servicio de atención al cliente de Audience Manager en 2019.

## ¿Por qué nuestros usuarios de solo lectura pueden crear, editar o eliminar características y segmentos?

**Pregunta**

¿Por qué nuestros usuarios de solo lectura pueden crear, editar o eliminar características y segmentos?

**Respuesta**

Además de crear grupos y permisos en la sección de administración, debe ponerse en contacto con el Servicio de atención al cliente (amsupport@adobe.com) para que un representante pueda habilitar los controles de acceso basados en roles (RBAC) para su cuenta.

<br> 

## ¿Por qué las poblaciones de características integradas cayeron a 0 alrededor del 15 de octubre? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

Alrededor del 14 de octubre de 2019, noté que las poblaciones de características integradas para el gráfico de ID de dispositivo habían caído a 0, donde anteriormente eran mucho más altas.

![Imagen de la colocación del ID del dispositivo](/help/using/support-issues/assets/device_id_populationdrop.png)

**Respuesta**

El 15 de octubre, se cambió una actualización de la funcionalidad de regla de combinación de perfiles de Audience Manager a la que ya no se realizan comparaciones de los identificadores de dispositivo con los datos integrados con un ID de CRM cargado en una fuente de datos entre dispositivos.  Anteriormente, Audience Manager se estaba realizando con el ID entre dispositivos (o el ID de CRM), así como copiando estas realizaciones en los UUID de Audience Manager (ID de dispositivo) asociados.  El cambio se realizó para reflejar con mayor precisión la naturaleza de los datos de características y los perfiles que se están realizando.

Para ver las realizaciones de características, seleccione la opción &quot;ID entre dispositivos&quot; en la lista desplegable situada en la esquina superior derecha de la vista de características.

![Ver las realizaciones por ID de varios dispositivos](/help/using/support-issues/assets/deviceid-crossdevice.png)

<br> 

## ¿Por qué no aparecen mis características o segmentos en la página Informes de superposición?

Explicación de por qué las características y los segmentos podrían no aparecer en la página Informes de superposición.

**Pregunta**

¿Por qué los usuarios no ven ciertas características y segmentos enumerados en la página de informes de superposición al intentar ejecutar un informe de superposición?

**Respuesta**

Se debe cumplir un requisito mínimo de visitante único para que un rasgo o segmento aparezca en los informes de superposición.


* Para características: 28000 en un período de 14 días
* Para segmentos: 70000 usuarios en tiempo real durante un período de 14 días

Encontrará más detalles sobre esto en la página Muestreo de [datos y tasas de error en los informes](/help/using/reporting/report-sampling.md)de Audience Manager seleccionados.