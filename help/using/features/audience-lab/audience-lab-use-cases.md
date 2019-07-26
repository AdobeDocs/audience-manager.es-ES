---
description: Audience Lab habilita varios casos de uso permitiéndole utilizar segmentos de base para crear grupos de prueba. Puede dividir los grupos de prueba en varios segmentos de prueba mutuamente excluyentes, asignarlos a destinos diferentes y luego determinar cuál de los segmentos es más eficaz en generar conversiones.
seo-description: Audience Lab habilita varios casos de uso permitiéndole utilizar segmentos de base para crear grupos de prueba. Puede dividir los grupos de prueba en varios segmentos de prueba mutuamente excluyentes, asignarlos a destinos diferentes y luego determinar cuál de los segmentos es más eficaz en generar conversiones.
seo-title: Casos de uso de Audience Lab
solution: Audience Manager
title: Casos de uso de Audience Lab
topic: API DIL
uuid: 727 bec 8 a-df 9 a -40 cc-b 8 a 7-e 1980 d 146 a 84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab Use Cases {#audience-lab-use-cases}

[!UICONTROL Audience Lab] habilita varios casos de uso permitiéndole utilizar segmentos de base para crear grupos de prueba. Puede dividir los grupos de prueba en varios segmentos de prueba mutuamente excluyentes, asignarlos a destinos diferentes y luego determinar cuál de los segmentos es más eficaz en generar conversiones.

## Compare Models in Audience Lab {#compare-models}

You can use several different types and sources of models in [!DNL Audience Manager]. [!UICONTROL Audience Lab] ofrece una manera fácil de comparar las tasas de conversión de sus clientes con los modelos activos.

<!-- audience-lab-compare-models.xml -->

En este caso de uso, está comparando distintos modelos. You can either use models created via an in-house data warehouse and import them in [!DNL Audience Manager] as [Onboarded Traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) or you can use the [Algorithmic Models](../../features/algorithmic-models/understanding-models.md) feature in [!DNL Audience Manager].

1. Create two models, either in the [Model Builder](../../features/algorithmic-models/create-model.md), or via an outside platform.
1. Create [algorithmic traits](../../features/traits/create-algorithmic-traits.md) from the algorithmic model or import your own models as onboarded traits.
1. Cree segmentos mutuamente exclusivos para que los usuarios de ambos modelos no superpongan:

   * Create a *Model 1 Segment* and a *Model 2 Segment*.
   * Have the segment rule for *Model 1 Segment* be model 1 trait [!DNL AND NOT] model 2 trait, and vice-versa for *Model 2 Segment*.

1. [Cree dos grupos de prueba de segmentos](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) en [!UICONTROL Audience Lab], uno con *el segmento del Modelo 1* como línea de base y otro con el segmento *del Modelo 2* como punto de referencia.

   * Mantenga las variables iguales para los dos grupos de prueba: mismos destinos, elementos creativos, características de conversión.
   * Asegúrese de que los segmentos de prueba tengan un número de usuarios similar (p. ej., 1,6 millones y 1,8 millones es alderecho, 1,6 millones y 16 millones).
   * Reserve un segmento de control en cada grupo de prueba de segmentos de prueba. De esta forma, puede separar una pequeña parte de cada segmento y no establecerlos explícitamente en la prueba.

1. Examine los resultados:

   * The [Audience Lab reporting view](../../features/audience-lab/audience-lab-reporting-view.md) will show the number of conversions each model is driving. Para las campañas basadas en conversión, el segmento de prueba que genera la mayor cantidad de conversiones significará el modelo que tiene mejor rendimiento.
   * Como tiene segmentos de control, también puede evaluar cómo se hizo el modelo con "targeting estándar". No solo está probando un modelo en comparación con el otro, sino que pruebe la pregunta de "¿este modelo hace mejor que las prácticas normales?"

## Testing Creatives Across Destinations {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Use [!UICONTROL Audience Lab] to measure the number of conversions a creative is driving across different destinations. Este caso de uso también permite medir las conversiones del elemento creativo frente a conversiones que ocurren naturales.

1. [Cree un grupo de prueba de segmento](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)y seleccione el segmento al que desee probar el elemento creativo como segmento de línea de base.
1. Divida el segmento de línea base en segmentos de prueba y controle segmentos.
1. Asigne los segmentos de prueba a los diferentes destinos que desee probar.
1. El segmento de control se puede retener y no asignar a ningún destino. El elemento creativo de prueba no debe segmentar el segmento de control para establecer una línea base de resultados para conversiones que ocurren naturales.
1. Especifique una fecha de inicio y una fecha de finalización para la prueba.
1. Configure el segmento y el elemento creativo en los destinos.
1. [La vista](../../features/audience-lab/audience-lab-reporting-view.md) de informes Lab Lab mostrará el número de conversiones que el creativo está impulsando en los destinos.
1. Debido a que creó un segmento de control, también puede evaluar cómo hizo el elemento creativo contra conversiones naturales. Está probando la pregunta: "¿Ha generado este creativo una tasa de conversión mayor que las prácticas normales? "
