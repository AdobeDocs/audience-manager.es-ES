---
description: Un informe General devuelve datos de rendimiento sobre características, segmentos y destinos.
seo-description: Un informe General en Audience Manager devuelve datos de rendimiento sobre características, segmentos y destinos.
seo-title: Informes generales en Audience Manager
solution: Audience Manager
title: Informes generales
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
feature: general & trend reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 1%

---


# Informes generales{#general-reports}

Un informe [!UICONTROL General] devuelve datos de rendimiento sobre características, segmentos y destinos.

## Información general {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] utiliza  [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para ampliar los permisos de grupo de usuarios a los  [!UICONTROL General] informes. Los usuarios solo pueden ver las características y los segmentos en sistema de informes de que tienen permisos para la vista. [!UICONTROL RBAC] le permite controlar qué datos de sistema de informes pueden realizar la vista los equipos internos. Por ejemplo, una agencia que gestione diferentes cuentas de anunciante puede configurar permisos de grupo de usuarios para que un equipo que administre la cuenta del Anunciante A no pueda ver los datos de sistema de informes del Anunciante B.

Ejecute un informe [!UICONTROL General] cuando necesite:

* Revise el rendimiento por características, segmento o destino.
* Rastree impresiones (totales y únicas) en intervalos de 1, 7, 14, 30, 60 y 90 días.
* Revise los recuentos de carga totales y únicos.
* Compare el rendimiento de los segmentos y las características.
* Identifique los segmentos y las características de rendimiento sólidas o deficientes, analice la demanda o compare los datos de carga y fuego con los informes de terceros.
* Exporte datos (formato .csv) para mayor análisis y uso compartido.

La siguiente ilustración proporciona una visión general de alto nivel de los elementos clave en el informe [!UICONTROL General].

![](assets/general_reports.png)

1. Configure las siguientes opciones:

   * **Tipo de informe:** seleccione el tipo de informe que desee (características, segmento o destino).

   * **Para Fechas hasta:** especifique el intervalo de fechas del informe.

2. Busque un rasgo, segmento o destino por nombre o ID.
3. En la lista de carpetas, arrastre y suelte las características, los segmentos o los destinos de los que desee informar en el panel [!UICONTROL Selections] de la derecha.
4. Genere el informe para mostrarlo en una tabla exportable.

## Ejecutar un informe general {#run-general-report}

En esta sección se describe cómo ejecutar un informe [!UICONTROL General] y cómo establecer la hora y otras opciones de rendimiento.

<!-- 

t_run_general_report.xml

 -->

1. En el panel **[!UICONTROL Analytics]**, haga clic en **[!UICONTROL General Reports]**.
1. En la lista desplegable **[!UICONTROL Report Type]**, seleccione el tipo que desee: Característica, Segmento o Destino.
1. ** CondicionalHaga clic en el cuadro de fecha para mostrar un calendario y, a continuación, seleccione la fecha de finalización del informe si desea especificar una fecha distinta de hoy.
1. Busque un rasgo, segmento o destino por nombre o ID.
1. En la lista de carpetas, arrastre y suelte las características, los segmentos o los destinos de los que desee informar en el panel [!UICONTROL Selections] de la derecha.
1. Haga clic **[!UICONTROL Run Report]**.

   Los resultados se muestran en una tabla exportable. Haga clic en los encabezados de columna para ordenar los resultados en orden ascendente o descendente.
1. Seleccione el botón de opción que desee en la parte superior del informe para filtrar los datos por rendimiento ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] o [!UICONTROL Total Trait Population]) o por tiempo (1, 7, 14, 30, 60 o intervalo de 90 días).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] se calculan  [!UICONTROL Rule-based Traits] únicamente.

1. ** OpcionalHaga clic  **[!UICONTROL Export to CSV]**. Esto exporta los [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] y [!UICONTROL Total Trait Population] para todos los intervalos de días.

## Informes generales Resultados explicados {#general-reports-explained}

Los números de [!UICONTROL General Reports] se generan directamente a partir de nuestro [!UICONTROL User Profile Store]. Los resultados reflejan el número de usuarios que [!DNL Audience Manager] contenía en el servidor en el momento en que se generaron estos números de sistema de informes.

* Estos números no incluyen los ID de visitante con tráfico excesivo. El tráfico de bots se filtra antes de llegar a nuestro sistema back-end. Además, parte del tráfico de bots se descarta durante una ejecución semanal de trabajos de limpieza en segundo plano.
* Si los datos incorporados mediante el procesamiento entrante bloquean el UUID [!DNL Audience Manager] y estos ID incluyen usuarios que ya no están activos en nuestro sistema, estos UUID inactivos [!DNL Audience Manager] nunca alcanzan el [!UICONTROL User Profile Store] y no se incluyen en los informes.
* [!UICONTROL Total Trait Realizations] se calculan  [!UICONTROL Rule-based Traits] únicamente.

## Resultados de informes generales para características {#general-report-results-traits}

Los filtros siguientes están disponibles cuando ejecuta un informe General y selecciona **[!UICONTROL Trait]** como tipo de informe.

Al filtrar los resultados por [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] es el número de visitantes de dispositivos anónimos que han agregado la característica a su perfil dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Realization] es el número total de realizaciones anónimas de características dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Population] es el número de visitantes de dispositivos anónimos que tienen esta característica en su perfil.

![general-report-traits-device](assets/general-report-traits-deviceid.png)

Al filtrar los resultados por [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] es el número de visitantes autenticados que han agregado la característica a su perfil, dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Realization] es el número total de realizaciones de características autenticadas dentro del intervalo de tiempo seleccionado.
* [!UICONTROL Total Trait Population] es el número de visitantes autenticados que tienen esta característica en su perfil.

![general-report-traits-cross-device](assets/general-report-traits-cross-device.png)

<!-- 
### Unique Trait Realizations

This metric represents the unique number of [Audience Manager Unique User IDs (UUID)](../reference/ids-in-aam.md) that qualified for the trait in your selected time range. For example, if a user visited your homepage three times on 10/1, you would see one Unique Trait Realization.

### Total Trait Realizations

This metric represents the total amount of trait fires for the trait in your selected time range. For example, if a user visited your homepage, then navigated to your tech news and your sports news sections, they would appear in the General Report as three total trait realizations, and one unique trait realization.

### Total Trait Population

This metric represents the total amount of Audience Manager UUIDs that are currently qualified for the trait. Use this number to understand the total amount of users you could use for segmentation and targeting. Typically, users remain part of a trait for [120 days](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). For example, a user visiting your homepage three times today and never returning afterwards, would remain as a user in this population every day until 120 days from now. At the 120 day mark, they would be removed from the population. Read our [Trait and Segment Qualification Reference](../features/traits/trait-and-segment-qualification-reference.md) for more examples on the difference between Unique Trait Realizations and Total Trait Population.

The illustration below shows the results of running a general report for the Trait report type. -->
<!-- 
![](assets/general_reports_metrics.png) -->


## Resultados de informes generales para segmentos {#general-report-results-segments}

Las métricas siguientes están disponibles cuando ejecuta un informe General y selecciona **[!UICONTROL Segment]** como tipo de informe:

### Población de segmentos en tiempo real

Esta métrica representa el número real de visitantes únicos vistos en tiempo real durante el intervalo de tiempo especificado y que estaban cualificados para el segmento en el momento en que los vio el Audience Manager.

### Población total del segmento

Esta métrica representa el número total de UUID de Audience Manager calificados para el segmento dentro del período de retrospectiva seleccionado. La población total del segmento de 1 día representa la base de usuarios más precisa para la segmentación.

>[!NOTE]
>
>Seleccione **[!UICONTROL Include Destination Mappings]** para ver un desglose de la población de segmentos para los destinos activados.

La siguiente ilustración muestra los resultados de ejecutar un informe general para el tipo de informe Segmento.

![](assets/general_reports_segment_metrics.png)

## Resultados de informes generales para destinos {#general-report-results-destinations}

Las métricas siguientes están disponibles cuando ejecuta un informe General y selecciona **[!UICONTROL Destination]** como tipo de informe:

**Población de segmentos en tiempo real**

Esta métrica representa el número real de visitantes únicos vistos en tiempo real durante el intervalo de tiempo especificado y que estaban cualificados para el segmento en el momento en que los vio el Audience Manager.

**Población total del segmento**

Esta métrica representa el número total de UUID de Audience Manager que pertenecen a un segmento dentro del período de retrospectiva, que se enviaron a un destino.

La siguiente ilustración muestra los resultados de ejecutar un informe general para el tipo de informe Destinos.

![](assets/general_reports_destinations.png)
