---
description: Cuestiones y problemas comunes relacionados con el sistema de informes.
seo-description: Cuestiones y problemas comunes relacionados con el sistema de informes.
seo-title: Preguntas más frecuentes sobre la creación de informes
solution: Audience Manager
title: Preguntas más frecuentes sobre la creación de informes
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 1%

---


# Preguntas más frecuentes sobre la creación de informes{#reporting-faq}

Cuestiones y problemas comunes relacionados con el sistema de informes.

<br> 

<!-- 

faq_reports.xml

 -->

**En el caso de las nuevas características integradas, ¿por qué a veces se muestran números[!UICONTROL Trait Graph]inferiores a los esperados o 0?**

A veces, después de cargar características, el informe [!UICONTROL Trait Graph] no muestra ningún resultado o muestra números inferiores a los esperados. Esto sucede cuando el volumen de datos que recibimos es tan bueno que el trabajo de procesamiento entrante no puede terminar de ingerir esta información hasta después de la fecha límite de sistema de informes de ese día.

Como resultado, estos datos se envían tarde al sistema de sistema de informes y no aparecerán en el intervalo de sistema de informes de 1 día que se utiliza para trazar el [!UICONTROL Trait Graph]. Sin embargo, puede vista estos datos en los intervalos de informes de 7, 14, 30 y 60 días en un informe de [tendencias](../reporting/trend-reports.md#trend-report-overview) o [](../reporting/general-reports.md#general-reports-overview) general al día siguiente.

<br> 

**Faltan algunos segmentos en un[!UICONTROL Overlap]informe. ¿Dónde están?**

Para ayudar a reducir la demanda computacional, estos informes omiten los datos estadísticamente insignificantes de los resultados. No faltan los segmentos, simplemente se pierden porque no arrojan resultados significativos ni grupos de usuarios útiles que se pueden destinatario. Consulte también:

* [Informes y metodologías de muestreo de datos](../reporting/report-sampling.md)
* [Recuento de usuarios únicos en informes](../reporting/unique-user-counts.md)generales y superpuestos.

<br> 

**Si ejecuto una campaña de mercadotecnia por correo electrónico, ¿cómo puedo determinar si los usuarios redirigidos llegan a mi sitio desde esa campaña o desde otras fuentes?**

Anexe una cadena de consulta específica de la campaña a la dirección URL de la sección del sitio que desee supervisar. A continuación, configure una regla de características para capturar esta variable. Por ejemplo, si la dirección URL pasa un ID de campaña como éste `www.test123.com/electronics?campaign=123`, cree una regla de características para capturar esos datos de la `h_referer` variable con una regla de características que busque un encabezado como `h_referer = 'campaign=123'`).

<br> 

**¿Cuál es la diferencia entre los recuentos de población de segmentos en tiempo real y totales?**

* **Tiempo real:** El número de usuarios únicos que forman parte del segmento y que están activos en sus propiedades durante un período de tiempo establecido (es decir, [!DNL Audience Manager] deben haber registrado la actividad de ese usuario durante el período de tiempo específico).

* **Población total del segmento:** Una agregación de todos los usuarios que están clasificados actualmente en ese segmento.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**Tengo un segmento que consiste en una sola característica. Cuando miro las métricas de Sistema de informes, sus recuentos no coinciden. ¿A qué se debe?**

See [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**I Entrada a un archivo y recepción entrante muestra un número elevado de registros procesados correctamente, pero sistema de informes muestra números mucho menores. ¿Por qué?**

En segundo plano, los datos incorporados solo se adjuntan a usuarios que aún están activos en AAM (el usuario debe haber tenido una [!DNL DCS] actividad reciente en los últimos 120 días). Por lo tanto, si los datos integrados para los usuarios que ya han caducado en [!DNL Audience Manager], [!UICONTROL Inbound] podría indicarle que se ha incorporado un cierto número de registros de usuario, pero si estos usuarios no han tenido ninguna actividad reciente, estos datos se perderán cuando lleguen a nuestro sitio [!UICONTROL User Profile Store] y el sistema de informes lo superará.

<br> 

**¿Por qué las características únicas de mis características integradas en varios dispositivos son mucho más altas que el número total de registros incorporados?**

Si ha incorporado un archivo para un proveedor de datos entre dispositivos que contiene la clave del ID de cliente, el Audience Manager realiza una búsqueda para obtener todos los ID de dispositivo asociados a cada uno de los ID de cliente incorporados. A continuación, el Audience Manager asigna las características integradas al ID de dispositivo asociado al ID de cliente.

Como ejemplo, supongamos que ha incorporado 100 registros. Por término medio, para cada uno de estos ID de cliente, AAM tiene tres ID de dispositivo asociados. Como resultado, la característica que se incorporó se asigna a 300 ID de dispositivo.

Existen dos razones por las que un único ID de cliente entre dispositivos se puede asociar con varios ID de dispositivo:

* Los usuarios inician sesión en la misma cuenta entre dispositivos desde varios equipos o navegadores.
* Los usuarios están borrando sus cookies. Nota: Las cookies &quot;abandonadas&quot; se eliminan tras 120 días de inactividad del usuario.

<br> 

**¿Por qué son siempre 0[!UICONTROL Total Trait Realizations]para mis rasgos onboardos?**

[!UICONTROL Total Trait Realizations] corresponden a las cargas de página. [!UICONTROL Total Trait Realizations] proporcione el número de veces que se activó esa característica específica en tiempo real. Este número se calcula solo para características basadas en reglas. Las características integradas siempre se muestran [!UICONTROL Total Trait Realizations] como 0.

<br> 

**Creé un rasgo y[!UICONTROL Trait Graph]muestra un número mayor de[!UICONTROL Unique Trait Realizations]que el[!UICONTROL Total Trait Population]. ¿Es normal?**

Esto se debe a que las métricas [!UICONTROL Unique Trait Realizations] son en tiempo real, pero los trabajos de sistema de informes que hacemos para calcular los [!UICONTROL Total Trait Population] no son en tiempo real. El [!UICONTROL Total Trait Population] tamaño debería ser mayor que el [!UICONTROL Unique Trait Realizations] en un par de días.
