---
description: Las señales son la unidad de información más pequeña dentro de Audience Manager. Representan las interacciones del usuario o la actividad del usuario en sus propiedades en línea y pasan a Audience Manager para su uso en reglas de características.
seo-description: Las señales son la unidad de información más pequeña dentro de Audience Manager. Representan las interacciones del usuario o la actividad del usuario en sus propiedades en línea y pasan a Audience Manager para su uso en reglas de características.
seo-title: Explicación de las señales
title: Explicación de las señales
uuid: 04a0554e-954e-484a-8838-9161ef416872
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Explicación de las señales

Las señales son la unidad de información más pequeña dentro de Audience Manager. Representan las interacciones de los usuarios o la actividad de los usuarios en sus propiedades en línea y se pasan a Audience Manager para su uso en reglas de características.

[!DNL Audience Manager] utiliza pares clave-valor para representar señales. Por ejemplo: la siguiente señal podría indicar que un visitante ha llegado a una página Web que contiene componentes electrónicos:

* `page = electronics`

El panel [Señales](../../features/data-explorer/data-explorer-signals-dashboard.md) muestra varios tipos de atributos de señal que puede utilizar para crear nuevas características. Esta es una vista detallada de las propiedades de señal disponibles:

* *El par* clave-valor muestra el par clave-valor de la señal recibida por [!DNL Audience Manager].
* *El tipo* de señal describe la categoría de cada señal. Las señales se clasifican en una de las siguientes categorías:
   * [Archivos](/help/using/integration/media-data-integration/actionable-log-files.md)de registro procesables: señales en tiempo real recibidas de los archivos de registro de rendimiento multimedia;
   * [!DNL Adobe Analytics]:: señales en tiempo real recibidas de su [!DNL Adobe Analytics] cuenta;
   * Datos generales en línea: datos en tiempo real generados por su actividad de audiencia y no incluidos en archivos de registro procesables [!DNL Adobe Analytics];
   * Registros incorporados: datos recibidos mediante transferencias de datos por lotes.
* *La fuente* de señal depende del tipo de señal:
   * En el caso de las señales incorporadas, la fuente de señales es el nombre de la fuente de datos.
   * Para las señales procedentes de [!DNL Adobe Analytics], la fuente de datos siempre será un grupo de informes.
   * En el caso de archivos de registro procesables y datos generales en línea, no se muestra la información de la fuente de señales.
* *Recuentos* totales muestra la cantidad total de veces que se recibió una señal en tiempo real [!DNL Audience Manager] en los últimos 7 días.
* *Incluido en Características* muestra si la señal es parte de alguna característica. Haga clic en la flecha para ver las características que incluyen la señal correspondiente. Para señales que no forman parte de ninguna característica, el valor de la columna cambia a [!UICONTROL Create Onboarded Trait] o [!UICONTROL Create Rule-Based Trait].

## Frecuencia de actualización de datos de señal

Debido a la gran cantidad de datos que Audience Manager procesa diariamente, [!UICONTROL Data Explorer] actualiza los datos de señal mostrados a intervalos de tiempo fijos, según el tipo de señal:

* Los datos de señal en tiempo real (archivos de registro procesables, datos y datos generales en línea) se actualizan cada 4 a 6 horas. [!DNL Adobe Analytics]
* Los datos de señal a bordo se actualizan cada 24 horas.

## Conceptos relacionados

[Señales, características y segmentos](/help/using/reference/signal-trait-segment.md)