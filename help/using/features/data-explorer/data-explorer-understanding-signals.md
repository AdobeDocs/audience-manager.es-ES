---
description: Las señales son la unidad de información más pequeña de Audience Manager. Representan las interacciones del usuario o la actividad del usuario en sus propiedades en línea y se pasan a Audience Manager para su uso en reglas de rasgos.
seo-description: Signals are the smallest unit of information within Audience Manager. They represent user interactions or user activity on your online properties, and get passed on to Audience Manager to be used in trait rules.
seo-title: Understanding Signals
title: Explicación de señales
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
exl-id: 12ab53e5-302b-4a82-9d8e-07b60139c65e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 1%

---

# Explicación de señales

Las señales son la unidad de información más pequeña de Audience Manager. Representan las interacciones del usuario o la actividad del usuario en sus propiedades en línea y se pasan a Audience Manager para su uso en reglas de rasgos.

[!DNL Audience Manager] utiliza pares clave-valor para representar señales. Por ejemplo, la siguiente señal podría indicar que un visitante ha llegado a una página web que contiene componentes electrónicos:

* `page = electronics`

El [Tablero de señales](../../features/data-explorer/data-explorer-signals-dashboard.md) le muestra varios tipos de atributos de señales que puede usar para crear características nuevas. A continuación se muestra una vista detallada de las propiedades de señal disponibles:

* *Par clave-valor* muestra el par clave-valor de la señal recibida por [!DNL Audience Manager].
* *Tipo de señal* describe la categoría de cada señal. Las señales se clasifican en una de las siguientes categorías:
   * [Archivos de registro procesables](/help/using/integration/media-data-integration/actionable-log-files.md): señales en tiempo real recibidas de sus archivos de registro de rendimiento multimedia;
   * [!DNL Adobe Analytics]: señales en tiempo real recibidas de su cuenta de [!DNL Adobe Analytics];
   * Datos generales en línea: datos en tiempo real generados por su actividad de audiencia y no incluidos en archivos de registro procesables y [!DNL Adobe Analytics].
   * Registros incorporados: datos recibidos mediante transferencias de datos por lotes.
* *La señal Source* depende del tipo de señal:
   * Para las señales integradas, la fuente de señales es el nombre de la fuente de datos.
   * Para las señales que se originan desde [!DNL Adobe Analytics], la fuente de datos siempre será un grupo de informes.
   * En el caso de archivos de registro procesables y datos en línea generales, no se muestra información de la fuente de señal.
* *Recuentos totales* muestra la cantidad total de veces que [!DNL Audience Manager] recibió una señal en tiempo real en los últimos siete días.
* *Incluido en características* le muestra si la señal es parte de alguna característica. Haga clic en la flecha para ver los rasgos que incluyen la señal correspondiente. Para las señales que no forman parte de ningún rasgo, el valor de la columna cambia a [!UICONTROL Create Onboarded Trait] o [!UICONTROL Create Rule-Based Trait].

## Frecuencia de actualización de datos de señal

Debido a la gran cantidad de datos que Audience Manager procesa diariamente, [!UICONTROL Data Explorer] actualiza los datos de señal mostrados a intervalos de tiempo fijos, según el tipo de señal:

* Los datos de señales en tiempo real (archivos de registro procesables, datos de [!DNL Adobe Analytics] y datos en línea generales) se actualizan cada 4 a 6 horas.
* Los datos de señal incorporados se actualizan cada 24 horas.

## Conceptos relacionados

[Señales, rasgos y segmentos](/help/using/reference/signal-trait-segment.md)
