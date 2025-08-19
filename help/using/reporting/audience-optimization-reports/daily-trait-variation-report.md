---
description: Este informe devuelve un lista de características que se han realizado por lo menos 10.000 veces en los 30 días anteriores a las fechas seleccionadas y que tienen una desviación estándar mayor o igual a 1,7 en cualquier dirección durante el mismo intervalo de tiempo. El informe ayuda a evaluar cómo el número de impresiones de usuarios únicos en un rasgo fluctúa con el tiempo.
seo-description: This report returns a list of traits that have been realized at least 10,000 times in the 30 days prior to the selected date(s) and have a standard deviation greater or equal to 1.7 in either direction over the same time interval. The report helps you evaluate how the number of impressions from unique users in a trait fluctuate over time.
seo-title: Daily Trait Variation Report
solution: Audience Manager
title: Informe de variación diaria de rasgos
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: Audience Optimization Reports
exl-id: c84a3f13-70fb-4167-b05b-de5cf518ec03
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 0%

---

# Informe de variación diaria de rasgos {#daily-trait-variation-report}

Este informe devuelve un lista de características que se han realizado por lo menos 10.000 veces en los 30 días anteriores a las fechas seleccionadas y que tienen una desviación estándar mayor o igual a 1,7 en cualquier dirección durante el mismo intervalo de tiempo. El informe ayuda a evaluar cómo el número de impresiones de usuarios únicos en un rasgo fluctúa con el tiempo.

>[!NOTE]
>
>El informe Variación diaria de rasgos de Audience Manager se adhiere a los principios de RBAC. Solo puede ver características de orígenes de datos a los que tiene acceso en función del grupo[ de usuarios de ](/help/using/features/administration/administration-overview.md)RBAC al que pertenece.

La desviación estándar mide la cantidad de variación o dispersión de la media (o valor promedio/esperado). Una desviación estándar baja indica que los puntos de datos tienden a estar muy cerca de la media. Una desviación estándar alta indica que los puntos de datos se distribuyen entre un gran rango de valores.

![](assets/daily_trait_variation.png)

Utilice el [!UICONTROL Date] lista para seleccionar una o más fechas para el informe. En la parte inferior del lista se muestra un gráfico de barras codificado por colores que proporciona un representante visual del rango de desviación estándar para todos los rasgos en todas las fechas seleccionadas. La línea vertical negra indica la media.

La columna central contiene una lista de características, identificadas por [!UICONTROL Trait ID] y [!UICONTROL Trait Name]. Haga clic en cualquier característica para acceder a un cuadro de diálogo elemento emergente que le permite seleccionar entre las siguientes opciones:

* **Solo conservar:** elimina todas las demás características del informe y muestra datos solo para esta característica.
* **Excluir:** elimina esta característica del informe y muestra los datos de todas las demás características. Se pueden excluir varias características.
* **Ver datos:** le permite mostrar los datos de esa fila. También puede descargar todas las filas como un archivo de texto.

La [!UICONTROL Standard Deviation] columna muestra gráficos de barras codificados por colores que muestran la desviación estándar de cada rasgo durante el intervalo seleccionado. Las barras rojas indican características con una desviación estándar negativa (los puntos de datos tienden a estar por debajo de la media). Las barras verdes indican características con una desviación estándar positiva (los puntos de datos tienden a estar por encima de la media). Pase el ratón sobre cualquier barra para mostrar un cuadro de diálogo elemento emergente con más información y opciones para mantener o excluir esa característica y vista más información.

En la parte inferior del informe aparecen iconos que le permiten exportar datos en varios formatos, revertir cualquier cambio que haya realizado en el informe (como excluir características), habilitar o deshabilitar actualizaciones automáticas y actualizar los datos del informe. Consulte [los iconos del informe y Herramientas explicaciones](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Casos de uso {#use-cases}

**Ejemplo #1**: este informe puede ser muy útil en situaciones en las que tiene características con un alto nivel de estacionalidad. Por instancia, digamos que su tienda en línea está probando promociones de temporada de varios tipos y precios. Tiene las siguientes características definidas en [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Digamos que ejecuta el [!UICONTROL Daily Trait Variation] informe el 20 de diciembre y nota una desviación positiva sólida en los rasgos mencionados anteriormente en los últimos 30 días. Esto puede sugerir que los visitantes están buscando los productos mencionados en su promoción de temporada. Para capitalizar esta tendencia, puede invertir más esfuerzo en direccionamiento creatividades para ese producto específico categoría en los visitantes que estén interesados en ellos.

**Ejemplo #2**: este informe puede ayudarlo a identificar anomalías direccionamiento relacionadas con problemas de etiquetado o configuraciones incorrectas de características. Imagina que has definido el siguiente rasgo en función de las categorías de tu en línea tienda:

* `productPage == "smartphones"`

Debido a una reconfiguración de su tienda, está dividiendo los teléfonos inteligentes Página en varias páginas, según marca nombres. Sin embargo, olvida actualizar las características definidas en [!DNL Audience Manager].

Un mes después, ejecuta el [!UICONTROL Daily Trait Variation] informe y nota una gran desviación negativa en el `productPage == "smartphones"` rasgo, aunque su número de visitante ha aumentado, según su sitio análisis. En base a esta información, te das cuenta de que no has actualizado las características para [!DNL Audience Manager] las páginas de nuevo producto, por lo que sabes que necesitas crear las siguientes características:

* productPage == &quot;samsung&quot;
* productPage == &quot;manzana&quot;
* productPage == &quot;huawei&quot;

Una vez que haga esto, verá que su audiencia califica para los rasgos recién creados.
