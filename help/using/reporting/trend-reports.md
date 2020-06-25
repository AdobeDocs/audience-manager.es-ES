---
description: Un informe de tendencias devuelve datos de tendencias en características y segmentos.
seo-description: Un informe de tendencias devuelve datos de tendencias en características y segmentos.
seo-title: Informes de tendencias
solution: Audience Manager
title: Informes de tendencias
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: general & trend reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 0%

---


# Informes de tendencias{#trend-reports}

Un informe de tendencias devuelve datos de tendencias en características y segmentos.

## Información general {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] utiliza [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para ampliar los permisos de grupo de usuarios a los [!UICONTROL Trend] informes. Los usuarios solo pueden ver las características y los segmentos en sistema de informes de que tienen permisos para la vista. [!UICONTROL RBAC] le permite controlar qué datos de sistema de informes pueden realizar la vista los equipos internos.

Por ejemplo, una agencia que gestione diferentes cuentas de anunciante puede configurar los permisos de grupo de usuarios para que un equipo que administre la cuenta del Anunciante A no pueda ver los datos de sistema de informes del Anunciante B.

Ejecute un [!UICONTROL Trend] informe cuando necesite:

* Revise los datos de tendencia por características y segmentos.
* Rastree las tendencias en intervalos de 1, 7, 14, 30, 60 y 90 días.
* Compare las tendencias de rasgos y segmentos con el paso del tiempo.
* Identifique los segmentos y características de rendimiento sólidos o deficientes.
* Exporte datos (formato .csv) para mayor análisis y uso compartido.

En la siguiente ilustración se proporciona una visión general de alto nivel de los elementos clave del [!UICONTROL Trend] informe.

![](assets/trend_reports.png)

1. Configure las siguientes opciones:
   **Tipo de informe:** Seleccione el tipo de informe deseado (característica o segmento).
   **Intervalo de fechas:** Especifique el intervalo de fechas del informe (fecha de inicio y fecha de finalización).
   **Intervalo de visualización:** Especifique el intervalo de visualización (intervalos de 1, 7, 14, 30, 60 y 90 días).
1. Busque un rasgo o segmento por nombre o ID.
1. En la lista de carpetas, arrastre y suelte las características o los segmentos que desee incluir en el informe en el panel de la derecha [!UICONTROL Selections] .
1. Genere el informe para mostrarlo en formato gráfico o exporte el informe a formato CSV.

## Run a Trend Report {#run-trend-report}

Este procedimiento describe cómo ejecutar un [!UICONTROL Trend] informe.

<!-- 

t_working_with_trend_reports.xml

 -->

1. En el **[!UICONTROL Analytics]** panel, haga clic en **[!UICONTROL Trend Reports]**.
1. En la lista **[!UICONTROL Report Type]** desplegable, seleccione el tipo que desee: **[!UICONTROL Trait]** o **[!UICONTROL Segment]**.
1. Haga clic en los cuadros de fecha para mostrar un calendario y, a continuación, seleccione las fechas de inicio y finalización del informe.
1. Especifique el intervalo de visualización: por 1, 7, 14, 30, 60 o 90 días.
1. Busque un rasgo o segmento por nombre o ID.
1. En la lista de carpetas, arrastre y suelte las características o los segmentos que desee incluir en el informe en el panel de la derecha [!UICONTROL Selections] .
   * Para obtener el mejor rendimiento, ejecute un [!UICONTROL Trend] informe con menos de 20 características o segmentos a la vez.
1. Haga clic en **[!UICONTROL Graph Traits]** o **[!UICONTROL Graph Segments]**, según el tipo de informe que esté viendo (características o segmentos). Estas opciones ignoran todas las carpetas y gráficos solo en los segmentos o características seleccionados individualmente.

   O

   Haga clic en **[!UICONTROL Export to CSV]** para exportar los datos de características o segmentos y todas las carpetas en formato CSV para una mayor análisis y uso compartido. Esto exporta el [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]y [!UICONTROL Total Trait Population] para todos los intervalos de días.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] se calculan [!UICONTROL Rule-based Traits] únicamente para.

1. (Opcional) Pase el cursor sobre características o segmentos individuales para mostrar el número de visitas y la fecha de cada punto de datos. Puede hacer clic en los encabezados de columna de la tabla para ordenar los resultados en orden ascendente o descendente.

## Resultados del informe de tendencias para características {#trend-report-results-traits}

Los filtros siguientes están disponibles cuando ejecuta un informe [!UICONTROL Trend Report] y lo selecciona **[!UICONTROL Trait]** como el tipo de informe.

Al filtrar los resultados por [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] es el número de visitantes de dispositivos anónimos que han agregado la característica a su perfil dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Realization] es el número total de realizaciones de características de anonimouse dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Population] es el número de visitantes de dispositivos anónimos que tienen esta característica en su perfil.

Al filtrar los resultados por [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] es el número de visitantes autenticados que han agregado la característica a su perfil, dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Realization] es el número total de realizaciones de características autenticadas dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Population] es el número de visitantes autenticados que tienen esta característica en su perfil.

![tendr-report-traits](assets/trend-report-traits.png)

Los ceros indican que [!DNL Audience Manager] no recopilaron datos para ese día. Las entradas en blanco indican que la característica no existe.

Vea el siguiente vídeo para ver en detalle cómo funcionan las métricas entre dispositivos.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## Resultados del informe de tendencias para segmentos {#segment-report-results-traits}

Los filtros siguientes están disponibles cuando ejecuta un informe [!UICONTROL Trend Report] y lo selecciona **[!UICONTROL Segments]** como el tipo de informe.

* **[!UICONTROL Real-time Segment Population]**:: el número de visitantes cualificados para el segmento dentro del intervalo de tiempo seleccionado.
* **[!UICONTROL Total Segment Population]**:: el número total de visitantes cualificados para el segmento.

![tendr-report-segments](assets/trend-report-segments.png)