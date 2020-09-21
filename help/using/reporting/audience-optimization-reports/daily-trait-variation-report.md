---
description: Este informe devuelve una lista de características que se han realizado al menos 10.000 veces en los 30 días anteriores a las fechas seleccionadas y que tienen una desviación estándar buena o igual a 1,7 en cualquier dirección durante el mismo intervalo de tiempo. El informe le ayuda a evaluar cómo el número de impresiones de usuarios únicos en una característica varía con el tiempo.
seo-description: Este informe devuelve una lista de características que se han realizado al menos 10.000 veces en los 30 días anteriores a las fechas seleccionadas y que tienen una desviación estándar buena o igual a 1,7 en cualquier dirección durante el mismo intervalo de tiempo. El informe le ayuda a evaluar cómo el número de impresiones de usuarios únicos en una característica varía con el tiempo.
seo-title: Informe de variación del rasgo diario
solution: Audience Manager
title: Informe de variación del rasgo diario
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: a41f0beffba686f283a2933ad7066cb124e4d380
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 1%

---


# Informe de variación del rasgo diario {#daily-trait-variation-report}

Este informe devuelve una lista de características que se han realizado al menos 10.000 veces en los 30 días anteriores a las fechas seleccionadas y que tienen una desviación estándar buena o igual a 1,7 en cualquier dirección durante el mismo intervalo de tiempo. El informe le ayuda a evaluar cómo el número de impresiones de usuarios únicos en una característica varía con el tiempo.

>[!NOTE]
>
>El informe Variación de rasgo diario en Audience Manager se ajusta a los principios de RBAC. Solo puede ver características de fuentes de datos a las que tiene acceso en función del grupo [de usuarios de](/help/using/features/administration/administration-overview.md) RBAC al que pertenece.

La desviación típica mide la cantidad de variación o dispersión con respecto a la media (o valor medio/esperado). Una desviación estándar baja indica que los puntos de datos tienden a estar muy cerca de la media. Una desviación estándar alta indica que los puntos de datos se distribuyen en un gran rango de valores.

![captura de pantalla del informe de variación de características diarias](assets/daily_trait_variation.png)

Utilice la [!UICONTROL Date] lista para seleccionar una o más fechas para el informe. En la parte inferior de la lista se muestra un gráfico de barras con códigos de color que representa de forma visual el rango de desviación estándar para todas las características de todas las fechas seleccionadas. La línea vertical negra indica la media.

La columna central contiene una lista de características, identificadas por [!UICONTROL Trait ID] y [!UICONTROL Trait Name]. Haga clic en cualquier característica para acceder a un cuadro de diálogo emergente que le permite seleccionar entre las siguientes opciones:

* **Mantener solamente:** Quita todas las demás características del informe y muestra los datos de esta característica solamente.
* **Excluir:** Quita esta característica del informe y muestra los datos de todas las demás características. Puede excluir varias características.
* **Datos de vista:** Permite mostrar datos para esa fila. También puede descargar todas las filas como un archivo de texto.

La [!UICONTROL Standard Deviation] columna muestra gráficos de barras con códigos de color que muestran la desviación estándar de cada característica a lo largo del intervalo seleccionado. Las barras rojas indican características con una desviación estándar negativa (los puntos de datos tienden a estar por debajo de la media). Las barras verdes indican características con una desviación estándar positiva (los puntos de datos tienden a estar por encima de la media). Pase el ratón sobre cualquier barra para mostrar un cuadro de diálogo emergente con más información y opciones para mantener o excluir esa característica y vista más información.

En la parte inferior del informe se muestran iconos que permiten exportar datos en diversos formatos, revertir cualquier cambio que haya realizado en el informe (como excluir características), habilitar o deshabilitar las actualizaciones automáticas y actualizar los datos del informe. Consulte Herramientas e iconos [de informes explicados](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Casos de uso {#use-cases}

**Ejemplo 1**: este informe puede resultar muy útil en situaciones en las que tiene características con un nivel de temporada alto. Por ejemplo: supongamos que su tienda en línea está probando promociones estacionales de diversos tipos y precios. Tiene las siguientes características definidas en [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Digamos que usted ejecuta el [!UICONTROL Daily Trait Variation] informe el 20 de diciembre y usted nota una sólida desviación positiva en las características antes mencionadas en los últimos 30 días. Esto puede sugerir que sus visitantes buscan los productos mencionados en su promoción de temporada. Para capitalizar esta tendencia, puede invertir más esfuerzos en destinar elementos creativos para esa categoría de productos específica a visitantes que les interesen.

**Ejemplo #2**: este informe puede ayudarle a identificar anomalías de objetivo relacionadas con problemas de etiquetado o configuraciones erróneas de características. Imagine que ha definido la siguiente característica en función de las categorías de su tienda en línea:

* `productPage == "smartphones"`

Debido a la reconfiguración de su tienda, está dividiendo la página de smartphones en varias páginas, en función de los nombres de las marcas. Sin embargo, olvida actualizar las características definidas en [!DNL Audience Manager].

Un mes después, ejecuta el [!UICONTROL Daily Trait Variation] informe y observa una gran desviación negativa en la `productPage == "smartphones"` característica, aunque el número de visitantes ha aumentado, según los análisis del sitio. En base a esta información, se da cuenta de que no ha actualizado las características [!DNL Audience Manager] de las páginas de productos nuevas, por lo que debe crear las siguientes características:

* `productPage == "samsung"`
* `productPage == "apple"`
* `productPage == "huawei"`

Una vez que lo haga, verá que su audiencia cumple los requisitos para las nuevas características creadas.
