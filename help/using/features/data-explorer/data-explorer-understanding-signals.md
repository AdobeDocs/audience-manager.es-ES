---
description: Las señales son la unidad de información más pequeña dentro del Audience Manager. Representan interacciones del usuario o actividad del usuario en sus propiedades en línea y se pasan al Audience Manager para su uso en reglas de características.
seo-description: Las señales son la unidad de información más pequeña dentro del Audience Manager. Representan interacciones del usuario o actividad del usuario en sus propiedades en línea y se pasan al Audience Manager para su uso en reglas de características.
seo-title: Explicación de las señales
title: Explicación de las señales
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: 'Explorador de datos '
exl-id: 12ab53e5-302b-4a82-9d8e-07b60139c65e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# Explicación de las señales

Las señales son la unidad de información más pequeña dentro del Audience Manager. Representan interacciones del usuario o actividad del usuario en sus propiedades en línea y se pasan al Audience Manager para su uso en reglas de características.

[!DNL Audience Manager] utiliza pares clave-valor para representar señales. Por ejemplo, la siguiente señal podría indicar que un visitante ha llegado a una página web que contiene componentes electrónicos:

* `page = electronics`

El [Panel de señales](../../features/data-explorer/data-explorer-signals-dashboard.md) muestra varios tipos de atributos de señal que puede utilizar para crear nuevos rasgos. A continuación se muestra una vista detallada de las propiedades de señal disponibles:

* *Los* pares clave-valor muestran el par clave-valor de la señal recibida por  [!DNL Audience Manager].
* *El* tipo de señal describe la categoría de cada señal. Las señales se dividen en una de las siguientes categorías:
   * [Archivos](/help/using/integration/media-data-integration/actionable-log-files.md) de registro procesables: señales en tiempo real recibidas de sus archivos de registro de rendimiento de los medios;
   * [!DNL Adobe Analytics]: señales en tiempo real recibidas de su  [!DNL Adobe Analytics] cuenta;
   * Datos generales en línea: datos en tiempo real generados por su actividad de audiencia y no incluidos en archivos de registro procesables y [!DNL Adobe Analytics];
   * Registros incorporados: datos recibidos mediante transferencias de datos por lotes.
* *El* origen de la señal depende del tipo de señal:
   * Para las señales incorporadas, la fuente de señal es el nombre de la fuente de datos.
   * Para las señales procedentes de [!DNL Adobe Analytics], la fuente de datos siempre será un grupo de informes.
   * Para archivos de registro procesables y datos generales en línea, no se muestra ninguna información de fuente de señal.
* *Total* de cuenta muestra el número total de veces que se recibió una señal  [!DNL Audience Manager] en tiempo real en los últimos 7 días.
* *Incluida en* Características le muestra si la señal forma parte de algún rasgo. Haga clic en la flecha para ver los rasgos que incluyen la señal correspondiente. Para señales que no forman parte de ningún rasgo, el valor de columna cambia a [!UICONTROL Create Onboarded Trait] o [!UICONTROL Create Rule-Based Trait].

## Frecuencia de actualización de datos de señal

Debido a la gran cantidad de datos que el Audience Manager procesa diariamente, [!UICONTROL Data Explorer] actualiza los datos de señal mostrados a intervalos de tiempo fijos, según el tipo de señal:

* Los datos de señal en tiempo real (archivos de registro procesables, [!DNL Adobe Analytics] datos y datos generales en línea) se actualizan cada 4 a 6 horas.
* Los datos de señal incorporados se actualizan cada 24 horas.

## Conceptos relacionados

[Señales, rasgos y segmentos](/help/using/reference/signal-trait-segment.md)
