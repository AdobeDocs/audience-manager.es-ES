---
description: Un informe de tendencias devuelve datos de tendencias sobre características y segmentos.
seo-description: A Trend report returns trend data on traits and segments.
seo-title: Trend Reports
solution: Audience Manager
title: Informes de tendencias
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: General & Trend Reports
exl-id: 3373f413-cc8f-49c7-9b4e-34b39e0efc38
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---

# Informes de tendencias{#trend-reports}

Un informe de tendencias devuelve datos de tendencias sobre características y segmentos.

## Información general {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] usa [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para extender permisos de grupos de usuarios a los informes de [!UICONTROL Trend]. Los usuarios solo pueden ver los rasgos y segmentos de los informes para los que tienen permisos de visualización. La funcionalidad [!UICONTROL RBAC] permite controlar qué datos de informes pueden ver los equipos internos.

Por ejemplo, una agencia que administra diferentes cuentas de anunciante puede configurar permisos de grupos de usuarios para que un equipo que administra la cuenta del anunciante A no pueda ver los datos de informes del anunciante B.

Ejecute un informe [!UICONTROL Trend] cuando necesite:

* Revise los datos de tendencia por características y segmentos.
* Rastree las tendencias en intervalos de 1, 7, 14, 30, 60 y 90 días.
* Compare tendencias de rasgos y segmentos a lo largo del tiempo.
* Identifique segmentos y rasgos de rendimiento sólidos o deficientes.
* Exporte datos (formato .csv) para su análisis y uso compartido adicionales.

La siguiente ilustración proporciona información general de alto nivel sobre los elementos clave del informe [!UICONTROL Trend].

![](assets/trend_reports.png)

1. Configure las siguientes opciones:
   **Tipo de informe:** Seleccione el tipo de informe deseado (Rasgo o Segmento).
   **Intervalo de fechas:** Especifique el intervalo de fechas para el informe (fecha de inicio y fecha de finalización).
   **Intervalo de visualización:** Especifique el intervalo de visualización (intervalos de 1, 7, 14, 30, 60 y 90 días).
1. Busque un rasgo o segmento por nombre o ID.
1. En la lista de carpetas, arrastre y suelte los rasgos o segmentos de los que desee informar en el panel [!UICONTROL Selections] de la derecha.
1. Genere el informe para mostrarlo en los datos en formato gráfico o exporte el informe a formato CSV.

## Ejecutar un informe de tendencias {#run-trend-report}

Este procedimiento describe cómo ejecutar un informe [!UICONTROL Trend].

<!-- 

t_working_with_trend_reports.xml

 -->

1. En el panel **[!UICONTROL Analytics]**, haga clic en **[!UICONTROL Trend Reports]**.
1. En la lista desplegable **[!UICONTROL Report Type]**, seleccione el tipo que desee: **[!UICONTROL Trait]** o **[!UICONTROL Segment]**.
1. Haga clic en los cuadros de fecha para mostrar un calendario y, a continuación, seleccione las fechas de inicio y finalización del informe.
1. Especifique el intervalo de visualización: por 1, 7, 14, 30, 60 o 90 días.
1. Busque un rasgo o segmento por nombre o ID.
1. En la lista de carpetas, arrastre y suelte los rasgos o segmentos de los que desee informar en el panel [!UICONTROL Selections] de la derecha.
   * Para obtener el mejor rendimiento, ejecute un informe de [!UICONTROL Trend] con menos de 20 características o segmentos a la vez.
1. Haga clic en **[!UICONTROL Graph Traits]** o **[!UICONTROL Graph Segments]**, según el tipo de informe que esté viendo (Características o Segmentos). Estas opciones ignoran todas las carpetas y gráficos, pero solo los rasgos o segmentos seleccionados individualmente.

   O

   Haga clic en **[!UICONTROL Export to CSV]** para exportar los datos de rasgos o segmentos y todas las carpetas en formato CSV para realizar un análisis y un uso compartido más profundos. Esto exporta [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] y [!UICONTROL Total Trait Population] para todos los intervalos de días.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] solo se han calculado para [!UICONTROL Rule-based Traits].

1. (Opcional) Pase el ratón sobre rasgos o segmentos individuales para mostrar el número de visitas y la fecha de cada punto de datos. Puede hacer clic en los encabezados de columna de la tabla para ordenar los resultados en orden ascendente o descendente.

## Resultados de informes de tendencias para características {#trend-report-results-traits}

Los filtros siguientes están disponibles cuando ejecuta un [!UICONTROL Trend Report] y selecciona **[!UICONTROL Trait]** como tipo de informe.

Al filtrar los resultados por [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] es el número de visitantes de su dispositivo anónimo que agregaron el rasgo a su perfil dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Realization] es el número total de realizaciones de rasgos anónimos del ratón dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Population] es el número de visitantes de su dispositivo anónimo que tienen este rasgo en su perfil.

Al filtrar los resultados por [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] es el número de visitantes autenticados que agregaron el rasgo a su perfil, dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Realization] es el número total de realizaciones de rasgos autenticados dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Population] es el número de los visitantes autenticados que tienen este rasgo en su perfil.

![rasgos de informe de tendencias](assets/trend-report-traits.png)

Los ceros indican que [!DNL Audience Manager] no recopiló datos para ese día. Las entradas en blanco indican que el rasgo no existía.

Vea el siguiente vídeo para obtener una visión detallada de cómo funcionan las métricas entre dispositivos.

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html?lang=es)

## Resultados de informes de tendencias para segmentos {#segment-report-results-traits}

Los filtros siguientes están disponibles cuando ejecuta un [!UICONTROL Trend Report] y selecciona **[!UICONTROL Segments]** como tipo de informe.

* **[!UICONTROL Real-time Segment Population]**: el número de visitantes calificados para el segmento dentro del intervalo de tiempo seleccionado.
* **[!UICONTROL Total Segment Population]**: el número total de visitantes calificados para el segmento.

![segmentos de informe de tendencias](assets/trend-report-segments.png)
