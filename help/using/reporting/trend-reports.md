---
description: Un informe de tendencias devuelve datos de tendencia sobre características y segmentos.
seo-description: Un informe de tendencias devuelve datos de tendencia sobre características y segmentos.
seo-title: Informes de tendencias
solution: Audience Manager
title: Informes de tendencias
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: Informes generales y de tendencias
exl-id: 3373f413-cc8f-49c7-9b4e-34b39e0efc38
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 1%

---

# Informes de tendencias{#trend-reports}

Un informe de tendencias devuelve datos de tendencia sobre características y segmentos.

## Información general {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] utiliza  [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para ampliar los permisos de grupo de usuarios a los  [!UICONTROL Trend] informes. Los usuarios solo pueden ver esos rasgos y segmentos en los informes que tienen permisos para ver. [!UICONTROL RBAC] permite controlar los datos que pueden ver los equipos internos de informes.

Por ejemplo, una agencia que administre diferentes cuentas de anunciante puede configurar permisos de grupo de usuarios para que un equipo que administre la cuenta del Anunciante A no pueda ver los datos de informes del Anunciante B.

Ejecute un informe [!UICONTROL Trend] cuando necesite:

* Revise los datos de tendencias por características y segmentos.
* Rastree las tendencias en intervalos de 1, 7, 14, 30, 60 y 90 días.
* Compare las tendencias de rasgos y segmentos a lo largo del tiempo.
* Identifique rasgos y segmentos de rendimiento sólidos o deficientes.
* Exportar datos (formato .csv) para un análisis y un uso compartido más profundos.

La siguiente ilustración proporciona información general de alto nivel sobre los elementos clave del informe [!UICONTROL Trend].

![](assets/trend_reports.png)

1. Configure las siguientes opciones:
   **Tipo de informe:** seleccione el tipo de informe que desee (rasgo o segmento).
   **Intervalo de fechas:** especifique el intervalo de fechas del informe (fecha de inicio y fecha de finalización).
   **Intervalo de visualización:** especifique el intervalo de visualización (intervalos de 1, 7, 14, 30, 60 y 90 días).
1. Busque un rasgo o segmento por nombre o ID.
1. En la lista de carpetas, arrastre y suelte los rasgos o segmentos de los que desee informar al panel [!UICONTROL Selections] de la derecha.
1. Genere el informe para mostrar los datos en formato gráfico o exporte el informe al formato CSV.

## Ejecutar un informe de tendencias {#run-trend-report}

Este procedimiento describe cómo ejecutar un informe [!UICONTROL Trend].

<!-- 

t_working_with_trend_reports.xml

 -->

1. En el tablero **[!UICONTROL Analytics]**, haga clic en **[!UICONTROL Trend Reports]**.
1. En la lista desplegable **[!UICONTROL Report Type]**, seleccione el tipo deseado: **[!UICONTROL Trait]** o **[!UICONTROL Segment]**.
1. Haga clic en los cuadros de fecha para mostrar un calendario y, a continuación, seleccione las fechas de inicio y finalización del informe.
1. Especifique el intervalo de visualización: por 1, 7, 14, 30, 60 o 90 días.
1. Busque un rasgo o segmento por nombre o ID.
1. En la lista de carpetas, arrastre y suelte los rasgos o segmentos de los que desee informar al panel [!UICONTROL Selections] de la derecha.
   * Para obtener el mejor rendimiento, ejecute un informe [!UICONTROL Trend] en menos de 20 rasgos o segmentos a la vez.
1. Haga clic en **[!UICONTROL Graph Traits]** o **[!UICONTROL Graph Segments]**, según el tipo de informe que esté viendo (características o segmentos). Estas opciones ignoran todas las carpetas y gráficos solo los rasgos o segmentos seleccionados individualmente.

   O

   Haga clic en **[!UICONTROL Export to CSV]** para exportar los datos de rasgos o segmentos y todas las carpetas en formato CSV para analizarlos y compartirlos más a fondo. Esto exporta los [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] y [!UICONTROL Total Trait Population] para todos los intervalos de días.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] se calculan  [!UICONTROL Rule-based Traits] solo para .

1. (Opcional) Pase el cursor sobre rasgos o segmentos individuales para mostrar el número de visitas y la fecha de cada punto de datos. Puede hacer clic en los encabezados de columna de la tabla para ordenar los resultados en orden ascendente o descendente.

## Resultados del informe de tendencias para características {#trend-report-results-traits}

Los filtros siguientes están disponibles cuando ejecuta [!UICONTROL Trend Report] y selecciona **[!UICONTROL Trait]** como tipo de informe.

Al filtrar los resultados por [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] es el número de visitantes anónimos del dispositivo que han agregado el rasgo a su perfil dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Realization] es el número total de realizaciones de características de anonymouse dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Population] es el número de visitantes anónimos del dispositivo que tienen este rasgo en su perfil.

Al filtrar los resultados por [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] es el número de visitantes autenticados que han agregado el rasgo a su perfil, dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Realization] es el número total de realizaciones de características autenticadas dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Population] es el número de visitantes autenticados que tienen este rasgo en su perfil.

![tendr-report-traits](assets/trend-report-traits.png)

Los ceros indican que [!DNL Audience Manager] no recopiló datos para ese día. Las entradas en blanco indican que el rasgo no existía.

Vea el siguiente vídeo para obtener una vista detallada del funcionamiento de las métricas entre dispositivos.

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## Resultados del informe de tendencias para segmentos {#segment-report-results-traits}

Los filtros siguientes están disponibles cuando ejecuta [!UICONTROL Trend Report] y selecciona **[!UICONTROL Segments]** como tipo de informe.

* **[!UICONTROL Real-time Segment Population]**: el número de visitantes que cumplen los requisitos para el segmento dentro del intervalo de tiempo seleccionado.
* **[!UICONTROL Total Segment Population]**: el número total de visitantes clasificados para el segmento.

![informes de tendencias-segmentos](assets/trend-report-segments.png)
