---
description: El laboratorio de audiencia permite utilizar varios casos de uso al permitirle utilizar segmentos de línea de base para crear grupos de prueba. Puede dividir los grupos de prueba en varios segmentos de prueba mutuamente excluyentes, asignarlos a diferentes destinos y luego determinar cuáles de los segmentos son más eficaces para generar conversiones.
seo-description: El laboratorio de audiencia permite utilizar varios casos de uso al permitirle utilizar segmentos de línea de base para crear grupos de prueba. Puede dividir los grupos de prueba en varios segmentos de prueba mutuamente excluyentes, asignarlos a diferentes destinos y luego determinar cuáles de los segmentos son más eficaces para generar conversiones.
seo-title: Casos de uso de Audience Lab
solution: Audience Manager
title: Casos de uso de Audience Lab
topic: DIL API
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 1%

---


# Casos de uso de Audience Lab {#audience-lab-use-cases}

[!UICONTROL Audience Lab] permite utilizar varios casos de uso, ya que permite utilizar segmentos de línea de base para crear grupos de prueba. Puede dividir los grupos de prueba en varios segmentos de prueba mutuamente excluyentes, asignarlos a diferentes destinos y luego determinar cuáles de los segmentos son más eficaces para generar conversiones.

## Compare modelos en el Laboratorio de Audiencias {#compare-models}

Puede utilizar varios tipos y fuentes de modelos diferentes en [!DNL Audience Manager]. [!UICONTROL Audience Lab] ofertas es una forma sencilla de comparar las tasas de conversión de sus clientes en todos sus modelos activos.

<!-- audience-lab-compare-models.xml -->

En este caso de uso, está comparando distintos modelos. Puede utilizar modelos creados mediante un almacén de datos interno e importarlos en [!DNL Audience Manager] como [Características integradas](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) o puede utilizar la función [Modelos algorítmicos](../../features/algorithmic-models/understanding-models.md) en [!DNL Audience Manager].

1. Cree dos modelos, ya sea en el [Generador de modelos](../../features/algorithmic-models/create-model.md) o a través de una plataforma externa.
1. Cree [características algorítmicas](../../features/traits/create-algorithmic-traits.md) a partir del modelo algorítmico o importe sus propios modelos como características integradas.
1. Cree segmentos mutuamente excluyentes para que los usuarios de ambos modelos no se superpongan:

   * Cree un *Segmento de modelo 1* y un *Segmento de modelo 2*.
   * Haga que la regla de segmento para *Segmento del modelo 1* sea la característica del modelo 1 [!DNL AND NOT] modelo 2 y viceversa para *Segmento del modelo 2*.

1. [Cree dos ](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) grupos de prueba de segmentos en  [!UICONTROL Audience Lab], uno con  *el* segmento modelo 1 como línea de base, y el otro con el  *segmento modelo 2 como* línea de base.

   * Mantenga las variables iguales para ambos grupos de prueba: los mismos destinos, elementos creativos y características de conversión.
   * Asegúrese de que los segmentos de prueba tengan un número similar de usuarios (por ejemplo, 1,6 millones y 1,8 millones están bien, 1,6 millones y 16 millones no lo están).
   * Reserve un segmento de control en cada grupo de prueba de segmento de prueba. De este modo, puede separar una pequeña parte de cada segmento y no darles un destinatario explícito en la prueba.

1. Examine los resultados:

   * La [vista de sistema de informes del laboratorio de Audiencia](../../features/audience-lab/audience-lab-reporting-view.md) mostrará el número de conversiones que cada modelo genera. En el caso de campañas basadas en conversiones, el segmento de prueba que genera la mayor cantidad de conversiones significará el modelo con mejor rendimiento.
   * Dado que tiene segmentos de control, también puede evaluar cómo se comparó el modelo con la &quot;segmentación estándar&quot;. No sólo está probando un modelo contra el otro, sino también probando la pregunta de &quot;¿este modelo tuvo mejores resultados que las prácticas normales?&quot;

## Prueba de elementos creativos en varios destinos {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Utilice [!UICONTROL Audience Lab] para medir el número de conversiones que un creativo genera en diferentes destinos. Este caso de uso también le permite medir las conversiones del elemento creativo en comparación con las conversiones naturales.

1. [Cree un grupo](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) de prueba de segmentos, seleccionando el segmento con el que desea probar el elemento creativo como segmento de línea de base.
1. Dividir el segmento de línea de base en segmentos de prueba y segmentos de control.
1. Asigne los segmentos de prueba a los diferentes destinos que desee probar.
1. El segmento de control se puede retener y no asignar a ningún destino. El elemento creativo de la prueba no debe establecer como objetivo el segmento de control para establecer una línea de base de resultados para las conversiones naturales.
1. Especifique una fecha de inicio y una fecha de finalización para la prueba.
1. Configure el segmento y el elemento creativo en los destinos.
1. La [vista de sistema de informes del laboratorio de Audiencia](../../features/audience-lab/audience-lab-reporting-view.md) mostrará el número de conversiones que el creativo está generando en los destinos.
1. Dado que ha creado un segmento de control, también puede evaluar cómo ha actuado el elemento creativo frente a las conversiones naturales. Está probando la pregunta: &quot;¿Generó este elemento creativo una tasa de conversión mayor que las prácticas normales?&quot;
