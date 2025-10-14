---
description: Audience Lab habilita varios casos de uso al permitirle utilizar segmentos de línea de base para crear grupos prueba. Puede dividir prueba grupos en varios segmentos de prueba mutuamente excluyentes, asignarlos a diferentes destinos y, a continuación, determinar cuáles de los segmentos son los más eficaces para generar conversiones.
seo-description: Audience Lab enables several use cases by allowing you to use baseline segments for creating test groups. You can divide test groups into several mutually exclusive test segments, map these to different destinations and then determine which of the segments are most effective in driving conversions.
seo-title: Audience Lab Use Cases
solution: Audience Manager
title: Casos de uso de Audience Lab
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# Casos de uso de Audience Lab {#audience-lab-use-cases}

[!UICONTROL Audience Lab] Habilita varios casos de uso, permitiéndole utilizar segmentos de línea de base para crear grupos prueba. Puede dividir prueba grupos en varios segmentos de prueba mutuamente excluyentes, asignarlos a diferentes destinos y, a continuación, determinar cuáles de los segmentos son los más eficaces para generar conversiones.

## Comparar modelos en Audience Lab {#compare-models}

Puede utilizar varios tipos y fuentes diferentes de modelos en [!DNL Audience Manager]. [!UICONTROL Audience Lab] ofrece una manera fácil de comparar las tasas de Conversión de sus clientes, a través de sus modelos activos.

<!-- audience-lab-compare-models.xml -->

En este caso de uso, está comparando diferentes modelos. Puede utilizar modelos creados mediante un almacén de datos interno e importarlos como [!DNL Audience Manager] [rasgos](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) incorporados o puede utilizar la [función Modelos](../../features/algorithmic-models/understanding-models.md) algorítmicos en [!DNL Audience Manager].

1. Crear dos modelos, ya sea en el Generador[&#x200B; de &#x200B;](../../features/algorithmic-models/create-model.md)modelos o a través de una plataforma externa.
1. [Crear rasgos](../../features/traits/create-algorithmic-traits.md) algorítmicos del modelo algorítmico o importe sus propios modelos como rasgos incorporados.
1. Crear segmentos mutuamente excluyentes para que los usuarios de ambos modelos no se superpongan:

   * Crear un *segmento del Modelo* 1 y un *segmento* del Modelo 2.
   * Haga que el regla segmento para *el segmento del modelo* 1 sea el rasgo [!DNL AND NOT] del modelo 1 del modelo 2 y viceversa para *el segmento* del modelo 2.

1. [Crear dos grupos](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) prueba segmento en [!UICONTROL Audience Lab], uno con *el segmento* del modelo 1 como línea de base y el otro con *el segmento* del modelo 2 como línea base.

   * Mantenga las mismas variables para ambos grupos prueba: los mismos destinos, creativa Conversión características.
   * Asegúrese de que los segmentos prueba tengan un número similar de usuarios (por ejemplo, 1,6 millones y 1,8 millones está bien, 1,6 millones y 16 millones no).
   * Reserve un segmento de control en cada prueba segmento prueba grupo. De esta manera, puede apartar una pequeña parte de cada segmento y no destino explícitamente en el prueba.

1. Examine los resultados:

   * La [vista sistema de informes](../../features/audience-lab/audience-lab-reporting-view.md) de Audience Lab mostrará el número de conversiones que genera cada modelo. Para las campañas basadas en Conversión, el prueba segmento que genere la mayor cantidad de conversiones significará el modelo que mejor funciona.
   * Debido a que tiene segmentos de control, también puede evaluar cómo le fue al modelo en comparación con el &quot;direccionamiento estándar&quot;. No solo está probando un modelo frente al otro, sino que está probando la pregunta de &quot;¿este modelo funcionó mejor que las prácticas normales?&quot;

## Prueba de elementos creativos en distintos destinos {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Utilícelo [!UICONTROL Audience Lab] para medir el número de conversiones que genera una creativa en los distintos destinos. Este caso de uso también permite medir comparar las conversiones del creativa las conversiones naturales.

1. [Crear un grupo](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) de prueba de segmentos, seleccione la segmento en la que desea prueba la creativa como segmento de línea de base.
1. Divida los segmento de línea de base en segmentos de prueba y segmentos de control.
1. Asigne los segmentos de prueba a los diferentes destinos que desee prueba.
1. El segmento de control se puede retener y no asignar a ningún destino. El segmento de control no debe ser identificado por el prueba creativa establecer una línea base de resultados para las conversiones que se producen de forma natural.
1. Especifique una fecha inicio y una fecha de finalización para el prueba.
1. Configure el segmento y el creativa en los destinos.
1. La [vista](../../features/audience-lab/audience-lab-reporting-view.md) de sistema de informes de Audience Lab mostrará el número de conversiones que la creativa está generando en los destinos.
1. Dado que ha creado un segmento de control, también puede evaluar cómo ha funcionado el creativa con respecto a las conversiones naturales. Usted está probando la pregunta: &quot;¿Esta creativa generó un tasa de conversión más alto que las prácticas normales?&quot;
