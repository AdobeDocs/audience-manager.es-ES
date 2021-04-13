---
description: Audience Lab permite utilizar varios casos de uso al permitirle utilizar segmentos de línea de base para crear grupos de prueba. Puede dividir los grupos de prueba en varios segmentos de prueba mutuamente excluyentes, asignarlos a distintos destinos y, a continuación, determinar cuál de los segmentos es el más eficaz para generar conversiones.
seo-description: Audience Lab permite utilizar varios casos de uso al permitirle utilizar segmentos de línea de base para crear grupos de prueba. Puede dividir los grupos de prueba en varios segmentos de prueba mutuamente excluyentes, asignarlos a distintos destinos y, a continuación, determinar cuál de los segmentos es el más eficaz para generar conversiones.
seo-title: Casos de uso de Audience Lab
solution: Audience Manager
title: Casos de uso de Audience Lab
topic-edit: DIL API
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: 'Audience Lab '
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# Casos de uso de Audience Lab {#audience-lab-use-cases}

[!UICONTROL Audience Lab] activa varios casos de uso permitiéndole utilizar segmentos de línea de base para crear grupos de prueba. Puede dividir los grupos de prueba en varios segmentos de prueba mutuamente excluyentes, asignarlos a distintos destinos y, a continuación, determinar cuál de los segmentos es el más eficaz para generar conversiones.

## Comparar modelos en Audience Lab {#compare-models}

Puede utilizar varios tipos y fuentes de modelos diferentes en [!DNL Audience Manager]. [!UICONTROL Audience Lab] ofrece una manera sencilla de comparar las tasas de conversión de sus clientes en todos sus modelos activos.

<!-- audience-lab-compare-models.xml -->

En este caso de uso, está comparando distintos modelos. Puede utilizar modelos creados mediante un almacén de datos interno e importarlos en [!DNL Audience Manager] como [Características integradas](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) o puede utilizar la función [Modelos algorítmicos](../../features/algorithmic-models/understanding-models.md) en [!DNL Audience Manager].

1. Cree dos modelos, ya sea en el [Generador de modelos](../../features/algorithmic-models/create-model.md) o a través de una plataforma externa.
1. Cree [rasgos algorítmicos](../../features/traits/create-algorithmic-traits.md) a partir del modelo algorítmico o importe sus propios modelos como rasgos integrados.
1. Cree segmentos mutuamente excluyentes para que los usuarios de ambos modelos no se superpongan:

   * Cree un segmento *Modelo 1* y un segmento *Modelo 2*.
   * Haga que la regla de segmento para *Modelo 1 Segmento* sea el rasgo modelo 1 [!DNL AND NOT] modelo 2 y viceversa para *Modelo 2 Segmento*.

1. [Cree dos ](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) grupos de prueba de segmentos en  [!UICONTROL Audience Lab], uno con  *Modelo 1* Segmento como línea de base y otro con  *Modelo 2* Segmentación como línea de base.

   * Mantenga las variables iguales para ambos grupos de prueba: los mismos destinos, características creativas y de conversión.
   * Asegúrese de que los segmentos de prueba tengan un número de usuarios similar (por ejemplo, 1,6 millones y 1,8 millones están bien, 1,6 millones y 16 millones no lo están).
   * Reserve un segmento de control en cada grupo de prueba de segmento de prueba. De este modo, puede apartar una pequeña parte de cada segmento y no dirigirlos explícitamente en la prueba.

1. Examine los resultados:

   * La [vista de informes de Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) mostrará el número de conversiones que cada modelo está impulsando. Para las campañas basadas en conversiones, el segmento de prueba que genera la mayor cantidad de conversiones significará el modelo que tiene el mejor rendimiento.
   * Como tiene segmentos de control, también puede evaluar cómo ha hecho el modelo en relación con la &quot;segmentación estándar&quot;. No solo está probando un modelo en comparación con el otro, sino también probando la pregunta de &quot;¿este modelo tuvo mejores resultados que las prácticas normales?&quot;

## Prueba de elementos creativos entre destinos {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Utilice [!UICONTROL Audience Lab] para medir el número de conversiones que un creativo está generando en diferentes destinos. Este caso de uso también le permite medir las conversiones del elemento creativo frente a conversiones naturales.

1. [Cree un grupo de prueba de segmentos](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups), seleccionando el segmento con el que desea probar el elemento creativo como segmento de línea de base.
1. Dividir el segmento de línea de base en segmentos de prueba y segmentos de control.
1. Asigne los segmentos de prueba a los diferentes destinos que desee probar.
1. El segmento de control se puede retener y no asignar a ningún destino. El creador de la prueba no debe segmentar el segmento de control para establecer una línea de base de resultados para las conversiones que se producen de forma natural.
1. Especifique una fecha de inicio y una fecha de finalización para la prueba.
1. Configure el segmento y el elemento creativo en los destinos.
1. La [vista de informes de Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) mostrará el número de conversiones que el creativo está generando en los destinos.
1. Como ha creado un segmento de control, también puede evaluar cómo ha hecho el elemento creativo frente a las conversiones que se producen de forma natural. Está probando la pregunta: &quot;¿Generó este elemento creativo una tasa de conversión mayor que la normal?&quot;
