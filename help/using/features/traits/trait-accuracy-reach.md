---
description: Describe la relación entre precisión y alcance en características algorítmicas.
seo-description: Describe la relación entre precisión y alcance en características algorítmicas.
seo-title: Precisión y alcance
solution: Audience Manager
title: Precisión y alcance
uuid: d121e099-6642-4003-ad4f-507d21e478d8
feature: 'Rasgos '
exl-id: 647b283a-fcfa-4e3f-8667-50c6aacbc78a
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 3%

---

# Precisión y alcance {#accuracy-and-reach}

Describe la relación entre precisión y alcance en características algorítmicas.

<!-- c_accuracy_reach.xml -->

## Precisión frente a alcance: Acerca de

Es importante comprender la relación entre precisión y alcance al trabajar con características algorítmicas. La precisión está representada por un valor puntuado que refleja la similitud de los usuarios con la línea base. La escala de precisión va de 0 (menos precisa) a 1 (más precisa). Alcance es simplemente un valor que representa el número de usuarios únicos que desea incluir en un rasgo. El alcance y la precisión están relacionados de forma inversa. Las características exactas llegan a menos usuarios y las características con bueno alcance son menos precisas. La siguiente imagen ilustra este concepto.

![](assets/Reach_v_Accuracy.png)

## La precisión y el alcance afectan al tamaño de la audiencia

Los objetivos empresariales deben ayudarle a tomar las decisiones correctas sobre la precisión y el alcance al trabajar con características algorítmicas. Si la precisión es su objetivo, tenga en cuenta que la población de un rasgo puede aumentar o disminuir en las ejecuciones de modelos. Los cambios de población son los resultados de la toma de decisiones por parte del algoritmo durante cada periodo de evaluación. A veces, el algoritmo encuentra usuarios más cualificados durante un ciclo de procesamiento y, durante otros, puede encontrar menos. Los resultados se determinan mediante los datos de línea de base utilizados para crear el modelo y los visitantes nuevos y las cualificaciones de rasgos que se han producido desde la ejecución del modelo anterior. Por el contrario, al trabajar con alcance, el recuento de población del usuario se mantiene constante. Por ejemplo, si desea alcanzar los 10 000 usuarios, el algoritmo se asegurará de que siempre alcance ese número para cada ejecución de modelo.

## Casos generales de uso de precisión frente al alcance

El enfoque en la precisión o el alcance depende de lo que desee lograr con un segmento en particular. La siguiente tabla puede ayudarle a evaluar la precisión frente al alcance al crear un rasgo.

| Favoritos de decisión de rasgos | Ayuda a encontrar |
|---|---|
| **Precisión** | Usuarios similares a los clientes de línea de base del modelo. Útil para campañas dirigidas cuando desea llegar a una audiencia específica. |
| **Alcance** | Un número específico de usuarios para cada ejecución de datos. Resulta útil para campañas de marca cuando le interesa llegar a una audiencia de un tamaño específico. |
