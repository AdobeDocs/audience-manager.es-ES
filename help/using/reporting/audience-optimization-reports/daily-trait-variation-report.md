---
description: Este informe devuelve una lista de rasgos que se han realizado al menos 10 000 veces en los 30 días anteriores a las fechas seleccionadas y que tienen una desviación estándar buena o igual a 1,7 en cualquier dirección durante el mismo intervalo de tiempo. El informe ayuda a evaluar cómo fluctúa con el tiempo el número de impresiones de usuarios únicos en un rasgo.
seo-description: Este informe devuelve una lista de rasgos que se han realizado al menos 10 000 veces en los 30 días anteriores a las fechas seleccionadas y que tienen una desviación estándar buena o igual a 1,7 en cualquier dirección durante el mismo intervalo de tiempo. El informe ayuda a evaluar cómo fluctúa con el tiempo el número de impresiones de usuarios únicos en un rasgo.
seo-title: Informe de variación del rasgo diario
solution: Audience Manager
title: Informe de variación del rasgo diario
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: Audience Optimization Reports
exl-id: c84a3f13-70fb-4167-b05b-de5cf518ec03
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 2%

---

# Informe de variación del rasgo diario {#daily-trait-variation-report}

Este informe devuelve una lista de rasgos que se han realizado al menos 10 000 veces en los 30 días anteriores a las fechas seleccionadas y que tienen una desviación estándar buena o igual a 1,7 en cualquier dirección durante el mismo intervalo de tiempo. El informe ayuda a evaluar cómo fluctúa con el tiempo el número de impresiones de usuarios únicos en un rasgo.

>[!NOTE]
>
>El informe Variación de rasgos diaria del Audience Manager se adhiere a los principios de RBAC. Solo puede ver los rasgos de fuentes de datos a las que tiene acceso en función del [Grupo de usuarios de RBAC](/help/using/features/administration/administration-overview.md) al que pertenece.

La desviación estándar mide la cantidad de variación o dispersión con respecto a la media (o valor medio/esperado). Una desviación estándar baja indica que los puntos de datos tienden a estar muy cerca de la media. Una desviación estándar alta indica que los puntos de datos se distribuyen en un gran rango de valores.

![](assets/daily_trait_variation.png)

Utilice la lista [!UICONTROL Date] para seleccionar una o más fechas para el informe. Aparece un gráfico de barras con códigos de color en la parte inferior de la lista que proporciona un representativo visual del rango de desviación estándar para todos los rasgos en todas las fechas seleccionadas. La línea vertical negra indica la media.

La columna central contiene una lista de rasgos, identificados por [!UICONTROL Trait ID] y [!UICONTROL Trait Name]. Haga clic en cualquier rasgo para acceder a un cuadro de diálogo emergente que le permite seleccionar una de las siguientes opciones:

* **Mantener solo:** elimina todas las demás características del informe y solo muestra los datos de esta característica.
* **Excluir:** elimina este rasgo del informe y muestra los datos de todos los demás rasgos. Puede excluir varios rasgos.
* **Ver datos:** permite mostrar los datos de esa fila. También puede descargar todas las filas como un archivo de texto.

La columna [!UICONTROL Standard Deviation] muestra gráficos de barras con códigos de color que muestran la desviación estándar de cada rasgo en el intervalo seleccionado. Las barras rojas indican características con una desviación estándar negativa (los puntos de datos tienden a estar por debajo de la media). Las barras verdes indican características con una desviación estándar positiva (los puntos de datos tienden a estar por encima de la media). Pase el ratón sobre cualquier barra para mostrar un cuadro de diálogo emergente con más información y opciones para mantener o excluir ese rasgo y ver más información.

En la parte inferior del informe se muestran iconos que permiten exportar datos en distintos formatos, revertir cualquier cambio que haya realizado en el informe (como excluir características), habilitar o deshabilitar las actualizaciones automáticas y actualizar los datos del informe. Consulte [Iconos de informe y herramientas explicadas](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Casos de uso {#use-cases}

**Ejemplo 1**: este informe puede ser muy útil en situaciones en las que tiene características con un nivel de temporada alto. Por ejemplo, supongamos que su tienda en línea está probando promociones estacionales de diversos tipos y precios. Tiene los siguientes rasgos definidos en [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Supongamos que ejecuta el informe [!UICONTROL Daily Trait Variation] el 20 de diciembre y observa una desviación positiva sólida en los rasgos mencionados en los últimos 30 días. Esto puede sugerir que los visitantes están buscando los productos mencionados en su promoción de temporada. Para sacar el máximo partido a esta tendencia, puede invertir más esfuerzos en crear productos específicos para esa categoría de productos específica en visitantes que estén interesados en ellos.

**Ejemplo 2**: este informe puede ayudarle a identificar anomalías de segmentación relacionadas con problemas de etiquetado o configuraciones erróneas de características. Imagine que ha definido el siguiente rasgo en función de las categorías de su tienda en línea:

* `productPage == "smartphones"`

Debido a la reconfiguración de su tienda, está dividiendo la página de smartphones en varias páginas, basadas en nombres de marcas. Sin embargo, olvida actualizar los rasgos definidos en [!DNL Audience Manager].

Un mes después, ejecuta el informe [!UICONTROL Daily Trait Variation] y observa una gran desviación negativa en el rasgo `productPage == "smartphones"`, aunque el número de visitantes ha aumentado, según los análisis del sitio. En función de esta información, es consciente de que no ha actualizado las características en [!DNL Audience Manager] para sus nuevas páginas de productos, por lo que sabe que necesita crear las siguientes características:

* productPage == &quot;samsung&quot;
* productPage == &quot;apple&quot;
* productPage == &quot;huawei&quot;

Una vez que lo haga, verá que su audiencia cumple los requisitos para los rasgos recién creados.
