---
description: Un informe Tendencia devuelve datos de tendencia en características y segmentos.
seo-description: Un informe Tendencia devuelve datos de tendencia en características y segmentos.
seo-title: Informes de tendencias
solution: Audience Manager
title: Informes de tendencias
uuid: bedbe 7 d 4-7 cbb -4403-9104-312 f 9230 aea 1
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# Trend Reports{#trend-reports}

Un informe Tendencia devuelve datos de tendencia en características y segmentos.

## Información general {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] utiliza [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para ampliar los permisos de grupos de usuarios a [!UICONTROL Trend] los informes. Los usuarios solo pueden ver las características y los segmentos en los informes que tienen permisos para ver. [!UICONTROL RBAC] permite controlar qué datos de informes pueden ver los equipos internos.

Por ejemplo, una agencia que administra diferentes cuentas de anunciante puede configurar permisos de grupos de usuarios para que un equipo que administra la cuenta de Anunciante A pueda ver los datos de informes del Anunciante B.

Run a [!UICONTROL Trend] report when you need to:

* Revise los datos de tendencia por características y segmentos.
* Rastree tendencias por intervalos 1, 7, 14, 30, 60 y 90 días.
* Compare las tendencias de características y segmentos con el tiempo.
* Identifique los segmentos y características de rendimiento fuerte o deficiente.
* Exporte datos (formato. csv) para realizar análisis y compartir más.

The following illustration provides a high-level overview of key elements in the [!UICONTROL Trend] report.

![](assets/trend_reports.png)

1. Configure las siguientes opciones:

   **Tipo de informe:** Seleccione el tipo de informe deseado (Características o Segmento).

   **Intervalo de fecha:** Especifique el intervalo de fechas del informe (fecha de inicio y fecha de finalización).

   **Intervalo de visualización:** Especifique los intervalos intervalo de visualización (1, 7, 14, 30, 60 y 90 días).

2. Busque un rasgo o un segmento por nombre o ID.
3. From the folder list, drag and drop the traits or segments you want to report to the [!UICONTROL Selections] panel on the right side.
4. Genere el informe para que se muestre en los datos en formato gráfico o exporte el informe al formato CSV.

## Run a Trend Report {#run-trend-report}

This procedure describes how to run a [!UICONTROL Trend] report.

<!-- 

t_working_with_trend_reports.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL Trend Reports]**.
1. From the **[!UICONTROL Report Type]** drop-down list, select the desired type: **[!UICONTROL Trait]** or **[!UICONTROL Segment]**.
1. Haga clic en los cuadros de fecha para mostrar un calendario y, a continuación, seleccione las fechas de inicio y finalización del informe.
1. Especifique el intervalo de visualización: por 1, 7, 14, 30, 60 o 90 días.
1. Busque un rasgo o un segmento por nombre o ID.
1. From the folder list, drag and drop the traits or segments you want to report to the [!UICONTROL Selections] panel on the right side.

   For best performance, run a [!UICONTROL Trend] report on fewer than 20 traits or segments at a time.
1. Click **[!UICONTROL Graph Traits]** or **[!UICONTROL Graph Segments]**, depending on which type of report you are viewing (Traits or Segments).

   Estas opciones ignoran todas las carpetas y todos los gráficos únicamente de características o segmentos seleccionados individualmente.

   O

   Click **[!UICONTROL Export to CSV]** to export the trait or segment data and all folders in CSV format for further analysis and sharing. This exports the [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], and [!UICONTROL Total Trait Population] for all day ranges.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] solo se [!UICONTROL Rule-based Traits] calculan para.

1. (Opcional) Pase el ratón sobre características o segmentos individuales para mostrar el número de visitas y la fecha de cada punto de datos.

   Puede hacer clic en los encabezados de columna de la tabla para ordenar los resultados en orden ascendente o descendente.

For [!UICONTROL Trended Trait] reports, zeroes indicate that [!DNL Audience Manager] did not collect data for that day. Las entradas en blanco indican que la característica no existía. El ejemplo siguiente muestra ejemplos de ambos tipos de entradas:

![](assets/trended_data.png)
