---
description: Preguntas y problemas comunes relacionados con los informes.
seo-description: Preguntas y problemas comunes relacionados con los informes.
seo-title: Preguntas más frecuentes sobre la creación de informes
solution: Audience Manager
title: Preguntas más frecuentes sobre la creación de informes
uuid: 78 cd 6 c 86-8 a 4 a -4748-ab 71-b 6 e 8 d 6078 c 94
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Preguntas más frecuentes sobre la creación de informes{#reporting-faq}

Preguntas y problemas comunes relacionados con los informes.

<br> 

<!-- 

faq_reports.xml

 -->

**Para las nuevas características integradas,¿por qué la visualización[!UICONTROL Trait Graph]a veces es menor que los números esperados o 0?**

Sometimes, after you upload traits, the [!UICONTROL Trait Graph] doesn't show any results or shows lower than expected numbers. Esto sucede cuando el volumen de datos que recibimos es tan genial que el trabajo de procesamiento de entrada no puede terminar de ingestar esta información hasta que la fecha límite del informe para ese día.

As a result, this data is sent to the reporting system late and won't show up in the 1-day reporting interval which is used for plotting the [!UICONTROL Trait Graph]. However, you can view this data in the 7, 14, 30, and 60-day report intervals in a [Trend](../reporting/trend-reports.md#trend-report-overview) or [General Report](../reporting/general-reports.md#general-reports-overview) on the following day.

<br> 

**Algunos segmentos no aparecen en[!UICONTROL Overlap]un informe. Where are they?**

Para ayudar a reducir la demanda de computadores, estos informes omiten datos estadísticamente insignificantes de los resultados. No faltan los segmentos, solo se retiran porque no generan resultados significativos ni grupos útiles de usuarios que pueda segmentar. Consulte también:

* [Metodologías de muestreo de datos y informes](../reporting/report-sampling.md)
* [Recuento de usuarios únicos en informes superpuestos e informes generales](../reporting/unique-user-counts.md).

<br> 

**Si ejecuto una campaña de mercadotecnia por correo electrónico,¿cómo puedo determinar si los usuarios redireccionados llegan al sitio desde esa campaña o desde otras fuentes?**

Anexe una cadena de consulta específica de campaña a la dirección URL de la sección del sitio que desee monitorear. A continuación, configure una regla de características para capturar esta variable. For example, if your URL passes in a campaign ID like this, `www.test123.com/electronics?campaign=123`, then create a trait rule to capture that data from the `h_referer` variable with a trait rule that looks for a header like `h_referer = 'campaign=123'`).

<br> 

**¿Cuál es la diferencia entre los recuentos de población en tiempo real y total de segmentos?**

* **Tiempo real:** El número de usuarios únicos que forman parte del segmento y activo en las propiedades durante un período de tiempo establecido (es decir [!DNL Audience Manager] , debe tener actividad grabada para ese usuario durante el período de tiempo específico).

* **Población total de segmentos:** Agregación de todos los usuarios que están clasificados actualmente en ese segmento.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**Tengo un segmento que consiste en un solo rasgo. Cuando miro métricas de informes, sus recuentos no coinciden. ¿A qué se debe?**

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

**I Entrada de un archivo y Recibo entrante muestra un número elevado de registros procesados correctamente, pero los informes muestran números mucho más bajos. ¿Por qué?**

In the backend, onboarded data gets attached only to users that are still active in AAM (user must have had recent [!UICONTROL DCS] activity in the past 120 days). Therefore, if you onboard data for users that have already expired in [!DNL Audience Manager], [!UICONTROL Inbound] might tell you that a certain number of user records were onboarded, but if these users have not had any recent activity, this data is dropped when it reaches our [!UICONTROL User Profile Store] and reporting will surface that.

<br> 

**¿Por qué son los únicos únicos de las características integradas entre dispositivos mucho mayor que el número total de registros introducidos?**

Si rastrea un archivo para un proveedor de datos entre dispositivos con el ID de cliente, Audience Manager realiza una búsqueda para obtener todos los ID de dispositivo asociados con cada ID de cliente incorporado. A continuación, Audience Manager asigna las características integradas al ID del dispositivo asociado con el ID de cliente.

Como ejemplo, supongamos que tiene 100 registros onbogged. Para cada uno de estos ID de cliente, AAM ha asociado tres ID de dispositivo. Como resultado, la característica integrada se asigna a 300 ID de dispositivo.

Existen dos motivos por los cuales un solo ID de cliente entre dispositivos puede asociarse con varios ID de dispositivo:

* Los usuarios inician sesión en la misma cuenta entre dispositivos desde varios equipos o navegadores.
* Los usuarios borran sus cookies. Nota: Las cookies «abandonadas» se eliminan después de 120 días de inactividad del usuario.

<br> 

**¿Por qué son[!UICONTROL Total Trait Realizations]siempre 0?**

[!UICONTROL Total Trait Realizations] corresponden a las cargas de página. [!UICONTROL Total Trait Realizations] proporcione el número de veces que se activó la característica específica en tiempo real. Este número se calcula únicamente para características basadas en reglas. Onboarded traits always show [!UICONTROL Total Trait Realizations] as 0.

<br> 

**He creado una característica y la[!UICONTROL Trait Graph]muestra un número mayor[!UICONTROL Unique Trait Realizations]que[!UICONTROL Total Trait Population]. Is this normal?**

You are seeing this because the [!UICONTROL Unique Trait Realizations] are real-time metrics, but the reporting jobs we do to calculate the [!UICONTROL Total Trait Population] are not real-time. [!UICONTROL Total Trait Population] El valor debe ser mayor que [!UICONTROL Unique Trait Realizations] el de un par de días.
