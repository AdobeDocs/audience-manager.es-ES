---
description: Audience Lab habilita varios casos de uso, ya que permite utilizar segmentos de línea de base para crear grupos de prueba. Puede dividir los grupos de prueba en varios segmentos de prueba mutuamente excluyentes, asignarlos a diferentes destinos y luego determinar cuál de los segmentos es más eficaz para impulsar las conversiones.
seo-description: Audience Lab enables several use cases by allowing you to use baseline segments for creating test groups. You can divide test groups into several mutually exclusive test segments, map these to different destinations and then determine which of the segments are most effective in driving conversions.
seo-title: Audience Lab Use Cases
solution: Audience Manager
title: Casos de uso de Audience Lab
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 1%

---

# Casos de uso de Audience Lab {#audience-lab-use-cases}

[!UICONTROL Audience Lab] activa varios casos de uso, ya que permite utilizar segmentos de línea de base para crear grupos de prueba. Puede dividir los grupos de prueba en varios segmentos de prueba mutuamente excluyentes, asignarlos a diferentes destinos y luego determinar cuál de los segmentos es más eficaz para impulsar las conversiones.

## Comparar modelos en Audience Lab {#compare-models}

Puede utilizar varios tipos y fuentes diferentes de modelos en [!DNL Audience Manager]. [!UICONTROL Audience Lab] ofrece una forma sencilla de comparar las tasas de conversión de sus clientes entre sus modelos activos.

<!-- audience-lab-compare-models.xml -->

En este caso de uso, se comparan distintos modelos. Puede utilizar modelos creados mediante un almacén de datos interno e importarlos en [!DNL Audience Manager] as [Características integradas](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) o puede usar el complemento [Modelos algorítmicos](../../features/algorithmic-models/understanding-models.md) función en [!DNL Audience Manager].

1. Cree dos modelos, ya sea en la variable [Generador de modelos](../../features/algorithmic-models/create-model.md), o a través de una plataforma externa.
1. Crear [rasgos algorítmicos](../../features/traits/create-algorithmic-traits.md) del modelo algorítmico o importe sus propios modelos como rasgos integrados.
1. Cree segmentos mutuamente excluyentes para que los usuarios de ambos modelos no se superpongan:

   * Crear un *Segmento del modelo 1* y una *Segmento del modelo 2*.
   * Tener la regla de segmento para *Segmento del modelo 1* ser rasgo del modelo 1 [!DNL AND NOT] rasgo del modelo 2 y viceversa para *Segmento del modelo 2*.

1. [Crear dos grupos de prueba de segmentos](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) in [!UICONTROL Audience Lab], uno con *Segmento del modelo 1* como línea de base, la otra con *Segmento del modelo 2* como línea de base.

   * Mantenga las variables iguales para ambos grupos de prueba: mismos destinos, creatividad, rasgos de conversión.
   * Asegúrese de que los segmentos de prueba tengan un número de usuarios similar (por ejemplo, 1,6 millones y 1,8 millones están bien, 1,6 millones y 16 millones no).
   * Reserve un segmento de control en cada grupo de prueba de segmento de prueba. De este modo, puede reservar una pequeña parte de cada segmento y no segmentarla explícitamente en la prueba.

1. Examine los resultados:

   * El [Vista de informes de Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) mostrará el número de conversiones que cada modelo está generando. Para las campañas basadas en conversiones, el segmento de prueba que genera la mayoría de las conversiones indicará el modelo con el mejor rendimiento.
   * Como tiene segmentos de control, también puede evaluar el rendimiento del modelo en comparación con la &quot;segmentación estándar&quot;. No solo está probando un modelo en comparación con el otro, sino que también está probando la pregunta &quot;¿este modelo hizo mejor que las prácticas normales?&quot;

## Prueba de elementos creativos en distintos destinos {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Uso [!UICONTROL Audience Lab] para medir el número de conversiones que un creativo está impulsando en diferentes destinos. Este caso de uso también le permite medir las conversiones del creativo frente a las conversiones que se producen de forma natural.

1. [Crear un grupo de prueba de segmentos](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups), seleccionando el segmento con el que desea probar el elemento creativo como segmento de línea de base.
1. Divida el segmento de línea de base en segmentos de prueba y segmentos de control.
1. Asigne los segmentos de prueba a los diferentes destinos que desee probar.
1. El segmento de control se puede retener y no se puede asignar a ningún destino. El segmento de control no debe ser el objetivo del creativo de la prueba para establecer una línea de base de resultados para las conversiones que se producen de forma natural.
1. Especifique una fecha de inicio y una fecha de finalización para la prueba.
1. Configure el segmento y el creativo en los destinos.
1. El [Vista de informes de Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) mostrará el número de conversiones que el creativo está impulsando en los destinos.
1. Dado que ha creado un segmento de control, también puede evaluar el comportamiento del creativo frente a las conversiones que se producen de forma natural. Está probando la pregunta: &quot;¿Generó este creativo una tasa de conversión mayor que las prácticas normales?&quot;
