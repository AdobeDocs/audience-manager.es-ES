---
description: Describe la relación entre precisión y alcance en características algorítmicas.
seo-description: Describe la relación entre precisión y alcance en características algorítmicas.
seo-title: Precisión y alcance
solution: Audience Manager
title: Precisión y alcance
uuid: d121e099-6642-4003-ad4f-507d21e478d8
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 3%

---


# Precisión y alcance {#accuracy-and-reach}

Describe la relación entre precisión y alcance en características algorítmicas.

<!-- c_accuracy_reach.xml -->

## Precisión frente a alcance: Acerca de

Es importante entender la relación entre la precisión y el alcance al trabajar con características algorítmicas. La precisión se representa mediante un valor de puntuación que refleja la similitud de usuarios con la línea base. La escala de precisión va de 0 (menos precisa) a 1 (más precisa). Alcance es simplemente un valor que representa el número de usuarios únicos que desea incluir en una característica. El alcance y la precisión están inversamente relacionados. Las características precisas llegan a menos usuarios y las características de bueno alcance son menos precisas. La siguiente imagen ilustra este concepto.

![](assets/Reach_v_Accuracy.png)

## La precisión y el alcance afectan al tamaño de la Audiencia

Sus objetivos comerciales le ayudarán a tomar las decisiones correctas sobre la precisión y el alcance al trabajar con características algorítmicas. Si su objetivo es la precisión, tenga en cuenta que la población de un rasgo puede aumentar o disminuir en las distintas ejecuciones de modelos. Los cambios de población son el resultado de que el algoritmo toma decisiones durante cada período de evaluación. A veces, el algoritmo encuentra más usuarios cualificados durante un ciclo de procesamiento y, durante otros, puede encontrar menos. Los resultados se determinan por los datos de base utilizados para crear el modelo y los nuevos visitantes y cualificaciones de características que se han producido desde la ejecución del modelo anterior. Por el contrario, al trabajar con el alcance, el recuento de población del usuario permanece constante. Por ejemplo, si desea llegar a los 10.000 usuarios, el algoritmo se asegurará de que siempre llegue a ese número para cada ejecución de modelo.

## Casos de uso general de precisión vs. alcance

El enfoque en la precisión o el alcance depende de lo que desee lograr con un segmento en particular. La siguiente tabla puede ayudarle a evaluar la precisión y el alcance al crear una característica.

| Favorecen la decisión sobre características | Ayuda a encontrar |
|---|---|
| **Precisión** | Usuarios similares a los clientes de línea de base del modelo. Resulta útil para campañas con objetivos cuando desea alcanzar una audiencia específica. |
| **Alcance** | Un número específico de usuarios para cada ejecución de datos. Resulta útil para campañas de marca cuando está interesado en alcanzar una audiencia de un tamaño específico. |