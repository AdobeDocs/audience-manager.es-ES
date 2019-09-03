---
description: Un informe General devuelve datos de rendimiento sobre características, segmentos y destinos.
seo-description: Un informe General de Audience Manager devuelve datos de rendimiento sobre características, segmentos y destinos.
seo-title: Informes generales en Audience Manager
solution: Audience Manager
title: Informes generales
uuid: 0 cea 75 a 0-969 e -4 ee 3-971 a -60 b 911711 e 52
translation-type: tm+mt
source-git-commit: 1c626c770208150d209d93f666b581113ada8de9

---


# Informes generales{#general-reports}

[!UICONTROL General] Un informe devuelve datos de rendimiento en características, segmentos y destinos.

## Información general {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] utiliza [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para ampliar los permisos de grupos de usuarios a [!UICONTROL General] los informes. Los usuarios solo pueden ver las características y los segmentos en los informes que tienen permisos para ver. [!UICONTROL RBAC] permite controlar qué datos de informes pueden ver los equipos internos. Por ejemplo, una agencia que administra diferentes cuentas de anunciante puede configurar permisos de grupos de usuarios para que un equipo que administra la cuenta de Anunciante A pueda ver los datos de informes del Anunciante B.

Ejecute [!UICONTROL General] un informe cuando necesite:

* Revise el rendimiento por características, segmentos o destinos.
* Rastree impresiones (total y único) en intervalos 1, 7, 14, 30, 60 y 90 días.
* Revise el total y los recuentos únicos de carga.
* Compare el rendimiento de características y segmentos.
* Identifique los segmentos y características de rendimiento fuerte o deficiente, analice la demanda o compare los datos de carga y activador con informes de terceros.
* Exporte datos (formato. csv) para realizar análisis y compartir más.

La siguiente ilustración proporciona información general de alto nivel sobre los elementos clave del [!UICONTROL General] informe.

![](assets/general_reports.png)

1. Configure las siguientes opciones:

   * **Tipo de informe:** Seleccione el tipo de informe deseado (Características, Segmento o Destino).

   * **Para fechas mediante:** Especifique el intervalo de fechas del informe.

2. Busque un atributo, segmento o destino por nombre o ID.
3. En la lista de carpetas, arrastre y suelte las características, segmentos o destinos que desee notificar al [!UICONTROL Selections] panel del lado derecho.
4. Genere el informe para que se muestre en una tabla exportable.

## Run a General Report {#run-general-report}

En esta sección se describe cómo ejecutar [!UICONTROL General] un informe y establecer la hora y otras opciones de rendimiento.

<!-- 

t_run_general_report.xml

 -->

1. En el **[!UICONTROL Analytics]** tablero, haga clic **[!UICONTROL General Reports]** en.
1. En la lista **[!UICONTROL Report Type]** desplegable, seleccione el tipo que desee: Características, Segmentos o Destino.
1. *Condicional Haga clic en* el cuadro de fecha para mostrar un calendario y, a continuación, seleccione la fecha final del informe si desea especificar una fecha distinta a hoy.
1. Busque un atributo, segmento o destino por nombre o ID.
1. En la lista de carpetas, arrastre y suelte las características, segmentos o destinos que desee notificar al [!UICONTROL Selections] panel del lado derecho.
1. Haga clic en **[!UICONTROL Run Report]**.

   Los resultados se muestran en una tabla exportable. Haga clic en los encabezados de columna para ordenar los resultados en orden ascendente o descendente.
1. Seleccione el botón de opción que desee en la parte superior del informe para filtrar los datos por rendimiento ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]o [!UICONTROL Total Trait Population]) o por hora (1, 7, 14, 30, 60 o 90 días).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] solo se [!UICONTROL Rule-based Traits] calculan para.

1. *Clic opcional***[!UICONTROL Export to CSV]**. Esto exporta, [!UICONTROL Unique Trait Realizations][!UICONTROL Total Trait Realizations]y [!UICONTROL Total Trait Population] para todos los intervalos de día.

## Resultados de informes generales explicados {#general-reports-explained}

Los números que se [!UICONTROL General Reports] generan directamente provienen de nuestra [!UICONTROL User Profile Store]. Los resultados reflejan el número de usuarios que [!DNL Audience Manager] contiene el back-end al momento de generarse estos números de informes.

* Estos números no incluyen ID de visitante con tráfico excesivo. El tráfico de bots se filtra antes de alcanzar nuestro sistema de backend. Además, el tráfico de bots se descarta durante un trabajo de limpieza semanal ejecutado en el back-end.
* Si realiza un seguimiento de los datos mediante el proceso de entrada inenlazado del [!DNL Audience Manager] UUID y estos ID incluyen usuarios que ya no están activos en nuestro sistema, estos [!DNL Audience Manager] UUID inactivos nunca llegan al [!UICONTROL User Profile Store] y no se registran.
* [!UICONTROL Total Trait Realizations] solo se [!UICONTROL Rule-based Traits] calculan para.

## Resultados generales de informes para características {#general-report-results-traits}

Las métricas siguientes están disponibles al ejecutar un informe General y seleccionar **[!UICONTROL Trait]** como tipo de informe:

**Realización de características únicas**

Esta métrica representa el número único de [ID de usuarios únicos de Audience Manager (UUID)](../reference/ids-in-aam.md) que cumplen los requisitos del intervalo de tiempo seleccionado. Por ejemplo, si un usuario visitó la página principal tres veces el 1 de marzo, vería una realización única de características.

**Realización total de características**

Esta métrica representa la cantidad total de características que se activan para la característica en el intervalo de tiempo seleccionado. Por ejemplo, si un usuario visitó su página principal, navegó a sus noticias técnicas y a las secciones de noticias deportivas, aparecerían en el informe general como tres características de características totales y una realización única de características.

**Población total de características**

Esta métrica representa la cantidad total de UUID de Audience Manager que están actualmente cualificados para la característica. Utilice este número para comprender la cantidad total de usuarios que puede utilizar para segmentación y segmentación. Normalmente, los usuarios siguen formando parte de un rasgo durante [120 días](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). Por ejemplo, un usuario que visite la página principal tres veces hoy y que nunca vuelva después, permanecerá como usuario de esta población todos los días hasta que transcurran 120 días desde ahora. En la marca de 120 días, se eliminarían de la población. Lea nuestra [Referencia de cualificación de características](../features/traits/trait-qualification-reference.md) para obtener más ejemplos sobre la diferencia entre Características únicas de características y Población de rasgos totales.

La siguiente ilustración muestra los resultados de ejecutar un informe general para el tipo de informe Características.

![](assets/general_reports_metrics.png)

## Resultados generales de informes para segmentos {#general-report-results-segments}

Las métricas siguientes están disponibles al ejecutar un informe General y seleccionar **[!UICONTROL Segment]** como tipo de informe:

**Población de segmentos en tiempo real**

Esta métrica representa la cantidad real de visitantes únicos que se vieron en tiempo real durante el intervalo de tiempo especificado y que fueron calificados para el segmento en el momento en que fueron vistos por Audience Manager.

**Población total de segmentos**

Esta métrica representa el número total de UUID de Audience Manager que están cualificados para el segmento dentro del período de retroceso seleccionado. La población de segmentos totales de 1 día representa la base de usuarios más precisa para la segmentación.

>[!NOTE]
>
>Seleccione **[!UICONTROL Include Destination Mappings]** para ver un desglose de la población de segmentos para destinos activados.

La siguiente ilustración muestra los resultados de ejecutar un informe general para el tipo de informe Segmento.

![](assets/general_reports_segment_metrics.png)

## Resultados generales de informes para destinos {#general-report-results-destinations}

Las métricas siguientes están disponibles al ejecutar un informe General y seleccionar **[!UICONTROL Destination]** como tipo de informe:

**Población de segmentos en tiempo real**

Esta métrica representa la cantidad real de visitantes únicos que se vieron en tiempo real durante el intervalo de tiempo especificado y que fueron calificados para el segmento en el momento en que fueron vistos por Audience Manager.

**Población total de segmentos**

Esta métrica representa el número total de UUID de Audience Manager que pertenecen a un segmento dentro del período de retroceso, que se enviaron a un destino.

La siguiente ilustración muestra los resultados de ejecutar un informe general para el tipo de informe Destinos.

![](assets/general_reports_destinations.png)
