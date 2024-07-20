---
description: Describe la relación entre precisión y alcance en rasgos algorítmicos.
seo-description: Describes the relationship between accuracy and reach in algorithmic traits.
seo-title: Accuracy and Reach
solution: Audience Manager
title: Precisión y alcance
uuid: d121e099-6642-4003-ad4f-507d21e478d8
feature: Traits
exl-id: 647b283a-fcfa-4e3f-8667-50c6aacbc78a
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 0%

---

# Precisión y alcance {#accuracy-and-reach}

Describe la relación entre precisión y alcance en rasgos algorítmicos.

<!-- c_accuracy_reach.xml -->

## Precisión frente a alcance: Acerca de

Es importante comprender la relación entre precisión y alcance al trabajar con rasgos algorítmicos. La precisión se representa mediante un valor puntuado que refleja la similitud de los usuarios con la línea de base. La escala de precisión varía de 0 (menos precisa) a 1 (más precisa). Alcance es simplemente un valor que representa el número de usuarios únicos que desea incluir en un rasgo. El alcance y la precisión están inversamente relacionados. Las características precisas llegan a menos usuarios y las características con un mayor alcance son menos precisas. La siguiente imagen ilustra este concepto.

![](assets/Reach_v_Accuracy.png)

## La precisión y el alcance afectan al tamaño de audiencia

Los objetivos de su empresa deben ayudarle a tomar las decisiones correctas sobre precisión y alcance al trabajar con características algorítmicas. Si el objetivo es la precisión, tenga en cuenta que la población de un rasgo puede aumentar o disminuir entre ejecuciones de modelos. Los cambios poblacionales son el resultado de la toma de decisiones del algoritmo durante cada periodo de evaluación. A veces, el algoritmo encuentra usuarios más cualificados durante un ciclo de procesamiento y, durante otros, puede encontrar menos. Los resultados están determinados por los datos de línea de base utilizados para crear el modelo y los nuevos visitantes y clasificaciones de rasgos que han llegado desde que se ejecutó el modelo anterior. Por el contrario, cuando se trabaja con alcance, el recuento de población de usuarios permanece constante. Por ejemplo, si desea alcanzar los 10 000 usuarios, el algoritmo se asegurará de que siempre alcance ese número para cada ejecución de modelo.

## Casos de uso generales de precisión frente a alcance

El enfoque en la precisión o el alcance depende de lo que desee lograr con un segmento en particular. La siguiente tabla puede ayudarle a evaluar la precisión frente al alcance al crear un rasgo.

| Favoritos de decisión de rasgos | Ayuda a encontrar |
|---|---|
| **Precisión** | Usuarios similares a los clientes de línea de base del modelo. Útil para campañas segmentadas cuando desea llegar a una audiencia específica. |
| **Alcance** | Un número específico de usuarios para cada ejecución de datos. Útil para campañas de marca cuando está interesado en llegar a una audiencia de un tamaño específico. |
