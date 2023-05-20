---
description: Este informe devuelve una lista de características que se han realizado al menos 10 000 veces en los 30 días anteriores a la fecha o fechas seleccionadas y que tienen una desviación estándar buena o igual a 1,7 en cualquier dirección y durante el mismo intervalo de tiempo. El informe ayuda a evaluar cómo fluctúa con el tiempo el número de impresiones de usuarios únicos en un rasgo.
seo-description: This report returns a list of traits that have been realized at least 10,000 times in the 30 days prior to the selected date(s) and have a standard deviation greater or equal to 1.7 in either direction over the same time interval. The report helps you evaluate how the number of impressions from unique users in a trait fluctuate over time.
seo-title: Daily Trait Variation Report
solution: Audience Manager
title: Informe de variación del rasgo diario
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: Audience Optimization Reports
exl-id: c84a3f13-70fb-4167-b05b-de5cf518ec03
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 1%

---

# Informe de variación del rasgo diario {#daily-trait-variation-report}

Este informe devuelve una lista de características que se han realizado al menos 10 000 veces en los 30 días anteriores a la fecha o fechas seleccionadas y que tienen una desviación estándar buena o igual a 1,7 en cualquier dirección y durante el mismo intervalo de tiempo. El informe ayuda a evaluar cómo fluctúa con el tiempo el número de impresiones de usuarios únicos en un rasgo.

>[!NOTE]
>
>El informe Variación de rasgos diaria en Audience Manager se adhiere a los principios de RBAC. Solo puede ver características de fuentes de datos a las que tiene acceso en función de la variable [Grupo de usuarios RBAC](/help/using/features/administration/administration-overview.md) a la que pertenece.

La desviación estándar mide la cantidad de variación o dispersión con respecto a la media (o el valor medio/esperado). Una desviación estándar baja indica que los puntos de datos tienden a estar muy cerca de la media. Una desviación estándar alta indica que los puntos de datos se distribuyen en un gran intervalo de valores.

![](assets/daily_trait_variation.png)

Utilice el [!UICONTROL Date] para seleccionar una o más fechas para el informe. Se muestra un gráfico de barras con códigos de color en la parte inferior de la lista que proporciona un representante visual del rango de desviación estándar para todos los rasgos en todas las fechas seleccionadas. La línea vertical negra indica la media.

La columna central contiene una lista de rasgos, identificados por [!UICONTROL Trait ID] y [!UICONTROL Trait Name]. Haga clic en cualquier rasgo para acceder a un cuadro de diálogo emergente que le permite seleccionar entre las siguientes opciones:

* **Mantener solo:** Elimina todos los demás rasgos del informe y muestra solo los datos de este rasgo.
* **Excluir:** Elimina este rasgo del informe y muestra los datos de todos los demás rasgos. Puede excluir varios rasgos.
* **Ver datos:** Permite mostrar los datos de esa fila. También puede descargar todas las filas como archivo de texto.

El [!UICONTROL Standard Deviation] La columna muestra gráficos de barras con códigos de color que muestran la desviación estándar de cada rasgo durante el intervalo seleccionado. Las barras rojas indican rasgos con una desviación estándar negativa (los puntos de datos tienden a estar por debajo de la media). Las barras verdes indican rasgos con una desviación estándar positiva (los puntos de datos tienden a estar por encima de la media). Pase el ratón sobre cualquier barra para mostrar un cuadro de diálogo emergente con más información y opciones para mantener o excluir esa característica y ver más información.

Los iconos se muestran en la parte inferior del informe y permiten exportar datos en varios formatos, revertir cualquier cambio que haya realizado en el informe (como la exclusión de características), habilitar o deshabilitar las actualizaciones automáticas y actualizar los datos del informe. Consulte [Iconos y herramientas de informes explicados](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Casos de uso {#use-cases}

**#1 de ejemplo**: este informe puede resultar muy útil en situaciones en las que tiene rasgos con un nivel de estacionalidad alto. Por ejemplo, supongamos que su tienda en línea está probando promociones de temporada de varios tipos y precios. Tiene los siguientes rasgos definidos en [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Supongamos que ejecuta el [!UICONTROL Daily Trait Variation] informe del 20 de diciembre y observará una desviación positiva sólida en los rasgos mencionados en los últimos 30 días. Esto puede sugerir que sus visitantes están buscando los productos mencionados en su promoción de temporada. Para capitalizar esta tendencia, puede invertir más esfuerzo en segmentar los elementos creativos de esa categoría de producto específica en los visitantes que estén interesados en ellos.

**#2 de ejemplo**: este informe puede ayudarle a identificar anomalías de segmentación relacionadas con problemas de etiquetado o configuraciones incorrectas de rasgos. Imagine que ha definido el siguiente rasgo en función de las categorías de su tienda en línea:

* `productPage == "smartphones"`

Debido a la reconfiguración de tu tienda, estás dividiendo la página de los smartphones en varias páginas, según los nombres de las marcas. Sin embargo, olvida actualizar los rasgos definidos en [!DNL Audience Manager].

Un mes después, se ejecuta el [!UICONTROL Daily Trait Variation] informe y observe una gran desviación negativa en el `productPage == "smartphones"` característica, aunque el número de visitantes ha aumentado, según el análisis del sitio. En función de esta información, se da cuenta de que no ha actualizado los rasgos en [!DNL Audience Manager] para sus nuevas páginas de productos, de modo que sepa que necesita crear las siguientes características:

* productPage == &quot;samsung&quot;
* productPage == &quot;apple&quot;
* productPage == &quot;huawei&quot;

Una vez que lo haga, verá que su audiencia se clasifica para los rasgos recién creados.
