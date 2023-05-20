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
source-wordcount: '636'
ht-degree: 1%

---

# Informes de tendencias{#trend-reports}

Un informe de tendencias devuelve datos de tendencias sobre características y segmentos.

## Información general {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] utiliza [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para ampliar los permisos de grupos de usuarios a [!UICONTROL Trend] informes. Los usuarios solo pueden ver los rasgos y segmentos de los informes para los que tienen permisos de visualización. [!UICONTROL RBAC] La funcionalidad permite controlar qué datos de informes pueden ver los equipos internos.

Por ejemplo, una agencia que administra diferentes cuentas de anunciante puede configurar permisos de grupos de usuarios para que un equipo que administra la cuenta del anunciante A no pueda ver los datos de informes del anunciante B.

Ejecute un [!UICONTROL Trend] informar cuando sea necesario:

* Revise los datos de tendencia por características y segmentos.
* Rastree las tendencias en intervalos de 1, 7, 14, 30, 60 y 90 días.
* Compare tendencias de rasgos y segmentos a lo largo del tiempo.
* Identifique segmentos y rasgos de rendimiento sólidos o deficientes.
* Exporte datos (formato .csv) para su análisis y uso compartido adicionales.

La siguiente ilustración proporciona información general de alto nivel sobre los elementos clave de la [!UICONTROL Trend] informe.

![](assets/trend_reports.png)

1. Configure las siguientes opciones:
   **Tipo de informe:** Seleccione el tipo de informe deseado (rasgo o segmento).
   **Intervalo de fecha:** Especifique el intervalo de fechas para el informe (fechas de inicio y finalización).
   **Intervalo de visualización:** Especifique el intervalo de visualización (intervalos de 1, 7, 14, 30, 60 y 90 días).
1. Busque un rasgo o segmento por nombre o ID.
1. En la lista de carpetas, arrastre y suelte los rasgos o segmentos de los que desee informar en [!UICONTROL Selections] panel en el lado derecho.
1. Genere el informe para mostrarlo en los datos en formato gráfico o exporte el informe a formato CSV.

## Ejecutar un informe de tendencias {#run-trend-report}

Este procedimiento describe cómo ejecutar un [!UICONTROL Trend] informe.

<!-- 

t_working_with_trend_reports.xml

 -->

1. En el **[!UICONTROL Analytics]** panel, haga clic en **[!UICONTROL Trend Reports]**.
1. Desde el **[!UICONTROL Report Type]** , seleccione el tipo que desee: **[!UICONTROL Trait]** o **[!UICONTROL Segment]**.
1. Haga clic en los cuadros de fecha para mostrar un calendario y, a continuación, seleccione las fechas de inicio y finalización del informe.
1. Especifique el intervalo de visualización: por 1, 7, 14, 30, 60 o 90 días.
1. Busque un rasgo o segmento por nombre o ID.
1. En la lista de carpetas, arrastre y suelte los rasgos o segmentos de los que desee informar en [!UICONTROL Selections] panel en el lado derecho.
   * Para obtener el mejor rendimiento, ejecute un [!UICONTROL Trend] informar sobre menos de 20 rasgos o segmentos a la vez.
1. Clic **[!UICONTROL Graph Traits]** o **[!UICONTROL Graph Segments]**, en función del tipo de informe que visualice (rasgos o segmentos). Estas opciones ignoran todas las carpetas y gráficos, pero solo los rasgos o segmentos seleccionados individualmente.

   O

   Clic **[!UICONTROL Export to CSV]** para exportar los datos de rasgos o segmentos y todas las carpetas en formato CSV para su posterior análisis y uso compartido. Esto exporta el [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], y [!UICONTROL Total Trait Population] para todos los intervalos de días.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] se calculan para [!UICONTROL Rule-based Traits] solo.

1. (Opcional) Pase el ratón sobre rasgos o segmentos individuales para mostrar el número de visitas y la fecha de cada punto de datos. Puede hacer clic en los encabezados de columna de la tabla para ordenar los resultados en orden ascendente o descendente.

## Resultados de informes de tendencias para características {#trend-report-results-traits}

Los filtros siguientes están disponibles cuando ejecuta una [!UICONTROL Trend Report] y seleccione **[!UICONTROL Trait]** como el tipo de informe.

Al filtrar los resultados por [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] es el número de visitantes de su dispositivo anónimo que han añadido el rasgo a su perfil en el intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Realization] es el número total de realizaciones de rasgos anónimos del ratón dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Population] es el número de visitantes de su dispositivo anónimo que tienen este rasgo en su perfil.

Al filtrar los resultados por [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] es el número de visitantes autenticados que han agregado el rasgo a su perfil, dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Realization] es el número total de realizaciones de rasgos autenticadas dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Population] es el número de los visitantes autenticados que tienen este rasgo en su perfil.

![tendencia-informe-características](assets/trend-report-traits.png)

Los ceros indican que [!DNL Audience Manager] no recopiló datos de ese día. Las entradas en blanco indican que el rasgo no existía.

Vea el siguiente vídeo para obtener una visión detallada de cómo funcionan las métricas entre dispositivos.

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## Resultados de informes de tendencias para segmentos {#segment-report-results-traits}

Los filtros siguientes están disponibles cuando ejecuta una [!UICONTROL Trend Report] y seleccione **[!UICONTROL Segments]** como el tipo de informe.

* **[!UICONTROL Real-time Segment Population]**: el número de visitantes clasificados para el segmento en el intervalo de tiempo seleccionado.
* **[!UICONTROL Total Segment Population]**: el número total de visitantes clasificados para el segmento.

![tend-report-segments](assets/trend-report-segments.png)
