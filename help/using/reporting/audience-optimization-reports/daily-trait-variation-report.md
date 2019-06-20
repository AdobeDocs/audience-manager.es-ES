---
description: Este informe devuelve una lista de características que se han obtenido al menos 10.000 veces en los 30 días anteriores a la fecha seleccionada y tienen una desviación estándar mayor o igual a 1,7 en cualquier dirección durante el mismo intervalo de tiempo. El informe ayuda a evaluar cómo el número de impresiones de usuarios únicos de un rasgo fluctuan a lo largo del tiempo.
seo-description: Este informe devuelve una lista de características que se han obtenido al menos 10.000 veces en los 30 días anteriores a la fecha seleccionada y tienen una desviación estándar mayor o igual a 1,7 en cualquier dirección durante el mismo intervalo de tiempo. El informe ayuda a evaluar cómo el número de impresiones de usuarios únicos de un rasgo fluctuan a lo largo del tiempo.
seo-title: Informe Variación de características diarias
solution: Audience Manager
title: Informe Variación de características diarias
uuid: 4 e 82 bb 17-d 447-4 ed 1-a 4 fc-e 15 b 0 f 1 b 47 f 0
translation-type: tm+mt
source-git-commit: 8f2ec880cbbe2f516ebc240a712337dc09c4e7f7

---


# Daily Trait Variation Report {#daily-trait-variation-report}

Este informe devuelve una lista de características que se han obtenido al menos 10.000 veces en los 30 días anteriores a la fecha seleccionada y tienen una desviación estándar mayor o igual a 1,7 en cualquier dirección durante el mismo intervalo de tiempo. El informe ayuda a evaluar cómo el número de impresiones de usuarios únicos de un rasgo fluctuan a lo largo del tiempo.

>[!NOTE]
>
>El informe Variación de características diarias de Audience Manager se adhiere a principios RBAC. You can only see traits from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

La desviación estándar mide la cantidad de variación o dispersión de la media (o valor promedio/esperado). Una desviación estándar baja indica que los puntos de datos tienden a ser muy cercanos a la media. Una desviación estándar alta indica que los puntos de datos se propagan a través de un gran rango de valores.

![](assets/daily_trait_variation.png)

Use the [!UICONTROL Date] list to select one or more dates for your report. Se muestra un gráfico de barras con códigos de colores en la parte inferior de la lista que proporciona un representante visual del rango de desviación estándar para todas las características en todas las fechas seleccionadas. La línea vertical negra indica la media.

The middle column contains a list of traits, identified by [!UICONTROL Trait ID] and [!UICONTROL Trait Name]. Haga clic en cualquier característica para acceder a un cuadro de diálogo emergente que le permite seleccionar entre las siguientes opciones:

* **Mantener solamente:** Quita el resto de características del informe y muestra los datos únicamente para esta característica.
* **Excluir:** Quita esta característica del informe y muestra los datos para todas las demás características. Puede excluir varias características.
* **Ver datos:** Permite mostrar los datos de esa fila. También puede descargar todas las filas como archivo de texto.

The [!UICONTROL Standard Deviation] column displays color-coded bar charts that display the standard deviation for each trait over the selected interval. Las barras rojas indican características con una desviación estándar negativa (los puntos de datos tienden a estar por debajo de la media). Las barras verdes indican características con una desviación estándar positiva (los puntos de datos tienden a estar por encima de la media). Pase el ratón sobre cualquier barra para mostrar un cuadro de diálogo emergente con más información y opciones para conservar o excluir esa característica y ver más información.

Los iconos se muestran en la parte inferior del informe que permiten exportar datos en diversos formatos, revertir los cambios que haya realizado en el informe (por ejemplo, excluyendo características), habilitar o deshabilitar las actualizaciones automáticas y actualizar los datos del informe. See [Report Icons and Tools Explained](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Casos de uso {#use-cases}

**Ejemplo n. º 1**: este informe puede resultar muy útil en situaciones en las que tiene características con un nivel de temporada elevado. Por ejemplo: supongamos que su tienda en línea está probando promociones temporada de diversos tipos y precios. You have the following traits defined in [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Say you run the [!UICONTROL Daily Trait Variation] report on the 20th of December and you notice a solid positive deviation on the above mentioned traits in the past 30 days. Esto sugiere que los visitantes buscan los productos mencionados en la promoción de temporada. Para capitalizar esta tendencia, puede invertir más esfuerzos en dirigir los elementos creativos para esa categoría de productos específica en los visitantes interesados en ellos.

**Ejemplo n. º 2**: Este informe puede ayudarle a identificar anomalías de objetivo relacionadas con problemas de etiquetado o inconfiguraciones de rasgos. Imagine que ha definido el siguiente rasgo en función de las categorías de su tienda en línea:

* `productPage == "smartphones"`

Debido a la reconfiguración de su tienda, está dividiendo la página smartphones en varias páginas, según los nombres de marcas. However, you forget to update the traits defined in [!DNL Audience Manager].

One month later, you run the [!UICONTROL Daily Trait Variation] report and notice a large negative deviation on the `productPage == "smartphones"` trait, although your visitor number has increased, according to your site analytics. Based on this information, you realize that you haven&#39;t updated the traits in [!DNL Audience Manager] for your new product pages, so you know that you need to create the following traits:

* Productpage = = &quot;samsung&quot;
* Productpage = = &quot;manzana&quot;
* Productpage = = &quot;huawei&quot;

Una vez que realice esto, verá que la audiencia cumple los requisitos de las características recién creadas.
