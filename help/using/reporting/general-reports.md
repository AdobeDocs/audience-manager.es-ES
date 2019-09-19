---
description: Un informe General devuelve datos de rendimiento sobre características, segmentos y destinos.
seo-description: Un informe General de Audience Manager devuelve datos de rendimiento sobre características, segmentos y destinos.
seo-title: Informes generales en Audience Manager
solution: Audience Manager
title: Informes generales
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
translation-type: tm+mt
source-git-commit: 1c626c770208150d209d93f666b581113ada8de9

---


# Informes generales{#general-reports}

Un [!UICONTROL General] informe devuelve datos de rendimiento sobre características, segmentos y destinos.

## Información general {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] utiliza [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para ampliar los permisos de grupo de usuarios a los [!UICONTROL General] informes. Los usuarios solo pueden ver esas características y segmentos en los informes que tienen permisos para ver. [!UICONTROL RBAC] permite controlar los datos que pueden ver los equipos internos de informes. Por ejemplo, una agencia que gestiona diferentes cuentas de anunciante puede configurar permisos de grupo de usuarios para que un equipo que administra la cuenta del anunciante A no pueda ver los datos de informes del anunciante B.

Ejecute un [!UICONTROL General] informe cuando necesite:

* Revise el rendimiento por características, segmento o destino.
* Rastree impresiones (totales y únicas) en intervalos de 1, 7, 14, 30, 60 y 90 días.
* Revise los recuentos de carga totales y únicos.
* Compare el rendimiento de los segmentos y las características.
* Identifique los segmentos y las características de rendimiento sólidas o deficientes, analice la demanda o compare los datos de carga y fuego con los informes de terceros.
* Exporte datos (formato .csv) para realizar más análisis y compartir.

En la siguiente ilustración se proporciona una visión general de alto nivel de los elementos clave del [!UICONTROL General] informe.

![](assets/general_reports.png)

1. Configure las siguientes opciones:

   * **** Tipo de informe: Seleccione el tipo de informe que desee (característica, segmento o destino).

   * **** Para fechas hasta: Especifique el intervalo de fechas del informe.

2. Busque un rasgo, segmento o destino por nombre o ID.
3. En la lista de carpetas, arrastre y suelte las características, los segmentos o los destinos de los que desee informar en el panel de la derecha [!UICONTROL Selections] .
4. Genere el informe para mostrarlo en una tabla exportable.

## Run a General Report {#run-general-report}

En esta sección se describe cómo ejecutar un [!UICONTROL General] informe y cómo establecer la hora y otras opciones de rendimiento.

<!-- 

t_run_general_report.xml

 -->

1. En el **[!UICONTROL Analytics]** tablero, haga clic en **[!UICONTROL General Reports]**.
1. En la lista **[!UICONTROL Report Type]** desplegable, seleccione el tipo que desee: Característica, Segmento o Destino.
1. *Condicional* Haga clic en el cuadro de fecha para mostrar un calendario y, a continuación, seleccione la fecha de finalización del informe si desea especificar una fecha distinta de hoy.
1. Busque un rasgo, segmento o destino por nombre o ID.
1. En la lista de carpetas, arrastre y suelte las características, los segmentos o los destinos de los que desee informar en el panel de la derecha [!UICONTROL Selections] .
1. Haga clic en **[!UICONTROL Run Report]**.

   Los resultados se muestran en una tabla exportable. Haga clic en los encabezados de columna para ordenar los resultados en orden ascendente o descendente.
1. Seleccione el botón de opción que desee en la parte superior del informe para filtrar los datos por rendimiento ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], o [!UICONTROL Total Trait Population]) o por tiempo (intervalo de 1, 7, 14, 30, 60 o 90 días).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] se calculan [!UICONTROL Rule-based Traits] únicamente para.

1. *Clic opcional* **[!UICONTROL Export to CSV]**. Esto exporta el [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]y [!UICONTROL Total Trait Population] para todos los intervalos de días.

## Informes generales Resultados explicados {#general-reports-explained}

Los números en el [!UICONTROL General Reports] se generan directamente a partir de nuestro [!UICONTROL User Profile Store]. Los resultados reflejan el número de usuarios que [!DNL Audience Manager] contenía el servidor en el momento en que se generaron estos números de informes.

* Estos números no incluyen las ID de visitantes con tráfico excesivo. El tráfico de bots se filtra antes de llegar a nuestro sistema back-end. Además, parte del tráfico de bots se descarta durante una ejecución semanal de trabajos de limpieza en segundo plano.
* Si los datos incorporados mediante el procesamiento entrante se desactivan en el [!DNL Audience Manager] UUID y estos ID incluyen usuarios que ya no están activos en nuestro sistema, estos [!DNL Audience Manager] UUID inactivos nunca llegan al [!UICONTROL User Profile Store] y no se incluyen en los informes.
* [!UICONTROL Total Trait Realizations] se calculan [!UICONTROL Rule-based Traits] únicamente para.

## Resultados de informes generales para características {#general-report-results-traits}

Las métricas siguientes están disponibles cuando ejecuta un informe General y selecciona **[!UICONTROL Trait]** como tipo de informe:

**Realizaciones de características únicas**

Esta métrica representa el número único de ID de usuario único (UUID) [de](../reference/ids-in-aam.md) Audience Manager que cumplen los requisitos para la característica en el intervalo de tiempo seleccionado. Por ejemplo: si un usuario visitó la página principal tres veces el 10/1, verá una Realización de características únicas.

**Realizaciones de características totales**

Esta métrica representa la cantidad total de activaciones de características para la característica en el intervalo de tiempo seleccionado. Por ejemplo: si un usuario visitó la página principal y luego navegó a las noticias tecnológicas y a las secciones de noticias deportivas, aparecerán en el Informe general como tres realizaciones totales de características y una realización única de características.

**Población total de características**

Esta métrica representa la cantidad total de UUID de Audience Manager que actualmente están cualificados para la característica. Utilice este número para comprender la cantidad total de usuarios que puede utilizar para segmentación y segmentación. Normalmente, los usuarios permanecen como parte de una característica durante [120 días](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). Por ejemplo: si un usuario visita su página principal tres veces hoy y nunca regresa después, permanecerá como usuario en esta población todos los días hasta dentro de 120 días. A los 120 días, serían retirados de la población. Lea nuestra Referencia [de cualificación](../features/traits/trait-qualification-reference.md) de características para obtener más ejemplos de la diferencia entre las Realizaciones de características únicas y la Población total de características.

La siguiente ilustración muestra los resultados de ejecutar un informe general para el tipo de informe de características.

![](assets/general_reports_metrics.png)

## Resultados de informes generales para segmentos {#general-report-results-segments}

Las métricas siguientes están disponibles cuando ejecuta un informe General y selecciona **[!UICONTROL Segment]** como tipo de informe:

**Población de segmentos en tiempo real**

Esta métrica representa el número real de visitantes únicos que se vieron en tiempo real durante el intervalo de tiempo especificado y que fueron calificados para el segmento en el momento en que fueron vistos por Audience Manager.

**Población total del segmento**

Esta métrica representa el número total de UUID de Audience Manager cualificados para el segmento dentro del período de retrospectiva seleccionado. La población total del segmento de 1 día representa la base de usuarios más precisa para la segmentación.

>[!NOTE]
>
>Seleccione **[!UICONTROL Include Destination Mappings]** para ver un desglose de la población de segmentos para los destinos activados.

La siguiente ilustración muestra los resultados de ejecutar un informe general para el tipo de informe Segmento.

![](assets/general_reports_segment_metrics.png)

## Informes generales Resultados para destinos {#general-report-results-destinations}

Las métricas siguientes están disponibles cuando ejecuta un informe General y selecciona **[!UICONTROL Destination]** como tipo de informe:

**Población de segmentos en tiempo real**

Esta métrica representa el número real de visitantes únicos que se vieron en tiempo real durante el intervalo de tiempo especificado y que fueron calificados para el segmento en el momento en que fueron vistos por Audience Manager.

**Población total del segmento**

Esta métrica representa el número total de UUID de Audience Manager que pertenecen a un segmento dentro del período de retrospectiva y que se enviaron a un destino.

La siguiente ilustración muestra los resultados de ejecutar un informe general para el tipo de informe Destinos.

![](assets/general_reports_destinations.png)
