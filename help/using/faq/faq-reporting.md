---
description: Cuestiones y problemas comunes relacionados con la creación de informes.
seo-description: Common reporting-related questions and issues.
seo-title: Reporting FAQ
solution: Audience Manager
title: Preguntas frecuentes sobre la creación de informes
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
feature: Reporting Reference
exl-id: 1e6531b2-bb39-4056-9d5e-164f50955f99
source-git-commit: 3bddd51582f3f8c46908dba5c5ac1938cb480013
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 100%

---

# Preguntas frecuentes sobre la creación de informes{#reporting-faq}

Cuestiones y problemas comunes relacionados con la creación de informes.

<br> 

<!-- 

faq_reports.xml

 -->

**En el caso de los nuevos rasgos integrados, ¿por qué [!UICONTROL Trait Graph] a veces muestra números inferiores a los esperados o 0?**

A veces, después de cargar rasgos, el informe [!UICONTROL Trait Graph] no muestra ningún resultado o muestra números inferiores a los esperados. Esto sucede cuando el volumen de datos que recibimos es tan grande que el trabajo de procesamiento entrante no puede terminar de incorporar esta información hasta que ha pasado el límite de tiempo para la creación de informes de ese día.

Como resultado, estos datos se envían tarde al sistema de creación de informes y no aparecen en el intervalo de sistema de informes de 1 día que se utiliza para trazar el [!UICONTROL Trait Graph]. Sin embargo, puede ver estos datos en los intervalos de informes de 7, 14, 30 y 60 días en [Tendencias](../reporting/trend-reports.md#trend-report-overview) o [Informe general](../reporting/general-reports.md#general-reports-overview) al día siguiente.

<br> 

**Faltan algunos segmentos en un informe [!UICONTROL Overlap]. ¿Dónde están?**

Para reducir la demanda computacional, estos informes omiten los datos estadísticamente insignificantes de los resultados. No faltan segmentos, simplemente se pierden porque no muestran resultados significativos ni grupos de usuarios útiles que se puedan segmentar. Consulte también:

* [Informes y metodologías de muestreo de datos](../reporting/report-sampling.md)
* [Recuento de usuarios únicos en informes generales y superpuestos](../reporting/unique-user-counts.md).

<br> 

**Si llevo a cabo una campaña de marketing por correo electrónico, ¿cómo puedo establecer si los usuarios redirigidos llegan a mi sitio desde esa campaña o desde otras fuentes?**

Anexe una cadena de consulta específica de la campaña a la dirección URL de la sección del sitio que quiere controlar. Seguidamente, configure una norma de rasgos para capturar esta variable. Por ejemplo, si la dirección URL pasa un ID de campaña como `www.test123.com/electronics?campaign=123`, cree una norma de rasgos para capturar esos datos de la variable `h_referer` con una norma de rasgos que busque un encabezado como `h_referer = 'campaign=123'`.

<br> 

**¿Qué diferencia existe entre los recuentos de población de segmentos en tiempo real y totales?**

* **Tiempo real:** el número de usuarios únicos que forman parte del segmento y están activos en sus propiedades durante un período de tiempo establecido (es decir, [!DNL Audience Manager] deben haber registrado la actividad de ese usuario durante el período de tiempo específico).

* **Población total del segmento:** una suma de todos los usuarios que están clasificados actualmente en ese segmento.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**Tengo un segmento con un solo rasgo. Cuando miro las métricas de Creación de informes, sus recuentos no coinciden. ¿A qué se debe?**

Consulte [Datos de tamaño de segmentos y rasgos en el Generador de segmentos](../features/segments/segment-builder-data.md)

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**Incorporo un archivo y la recepción entrante muestra un número elevado de registros procesados correctamente, pero el sistema de informes muestra números muy inferiores. ¿Por qué?**

En segundo plano, los datos incorporados solo se adjuntan a usuarios que aún están activos en AAM (el usuario debe haber tenido una actividad [!DNL DCS] en los últimos 120 días). Por lo tanto, si incorpora datos para usuarios que ya han caducado en [!DNL Audience Manager], [!UICONTROL Inbound] podría indicarle que se ha incorporado un cierto número de registros de usuario, pero si estos usuarios no han tenido ninguna actividad reciente, estos datos se perderán cuando lleguen a nuestro sitio de [!UICONTROL User Profile Store] y el sistema de informes lo mostrará.

<br> 

**¿Por qué los rasgos únicos de mis rasgos integrados en varios dispositivos son mucho más elevados que el número total de registros incorporados?**

Si ha incorporado un archivo para un proveedor de datos entre dispositivos que contiene la clave del ID de cliente, Audience Manager realiza una búsqueda para obtener todos los ID de dispositivo asociados a cada uno de los ID de cliente incorporados. Seguidamente, Audience Manager asigna los rasgos integrados al ID de dispositivo asociado al ID de cliente.

A modo de ejemplo, supongamos que ha incorporado 100 registros. De media, para cada uno de estos ID de cliente, AAM tiene tres ID de dispositivo asociados. Como resultado, el rasgo que se incorporó se asigna a 300 ID de dispositivo.

Existen dos razones por las que un único ID de cliente entre dispositivos se puede asociar con varios ID de dispositivo:

* Los usuarios inician sesión en la misma cuenta entre dispositivos desde varios equipos o navegadores.
* Los usuarios están borrando sus cookies. Nota: las cookies “abandonadas” se eliminan tras 120 días de inactividad del usuario.

<br> 

**¿Por qué las [!UICONTROL Total Trait Realizations] para mis rasgos integrados siempre es 0?**

[!UICONTROL Total Trait Realizations] corresponde a las cargas de página. [!UICONTROL Total Trait Realizations] proporciona el número de veces que se ha activado ese rasgo específico en tiempo real. Este número solo se calcula para rasgos basados en normas. Los rasgos integrados siempre muestran [!UICONTROL Total Trait Realizations] como 0.

<br> 

**Creé un rasgo y [!UICONTROL Trait Graph] muestra un número superior de [!UICONTROL Unique Trait Realizations] que de [!UICONTROL Total Trait Population]. ¿Es normal?**

Esto se debe a que las [!UICONTROL Unique Trait Realizations] son métricas en tiempo real, pero los trabajos de sistema de informes que hacemos para calcular la [!UICONTROL Total Trait Population] no son en tiempo real. La [!UICONTROL Total Trait Population] debería ser mayor que el [!UICONTROL Unique Trait Realizations] de un par de días.
