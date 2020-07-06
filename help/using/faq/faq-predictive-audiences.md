---
description: Predictive Audiences le ayuda a clasificar en tiempo real audiencias desconocidas como personalidades diferenciadas, mediante el uso de la ciencia de datos.
seo-description: Predictive Audiences le ayuda a clasificar en tiempo real audiencias desconocidas como personalidades diferenciadas, mediante el uso de la ciencia de datos.
seo-title: Preguntas frecuentes sobre Predictive Audiences
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 100%

---


# Preguntas frecuentes sobre Predictive Audiences

Preguntas frecuentes sobre [!UICONTROL Predictive Audiences].

 

**¿Cuándo debería usar [!UICONTROL Predictive Audiences] en lugar de [!UICONTROL Look-alike modeling]?**

[!UICONTROL Predictive Audiences] y [!UICONTROL Look-alike modeling] sirven para diferentes casos de uso. Estas son las principales diferencias entre los dos algoritmos:

1. [!UICONTROL Look-alike modeling] toma una pequeña audiencia como entrada y la amplía. [!UICONTROL Predictive Audiences] toma una audiencia grande como entrada y la divide en distintas audiencias más pequeñas, definidas por las personalidades.
1. El número de segmentos de base es diferente en cada algoritmo. [!UICONTROL Predictive Audiences] requiere al menos dos líneas de base, mientras que [!UICONTROL Look-alike modeling] utiliza una línea de base como máximo.
1. [!UICONTROL Predictive Audiences] realiza una evaluación de segmentos en tiempo real, mientras que [!UICONTROL Look-alike modeling] no lo hace.

En función de su caso de uso, debe decidir qué modelo será más relevante para usted.

Puede considerar la construcción de un modelo de [!UICONTROL Predictive Audiences] con una serie de líneas de base, lo que equivale a construir el mismo número de modelos de similitud, aunque sin la evaluación en tiempo real, y con una alta probabilidad de tener visitantes que se corresponden con diferentes personalidades, en lugar de con una sola personalidad diferenciada.

 

**¿Cuántas personalidades o modelos puedo crear?**

Puede crear hasta diez modelos de [!UICONTROL Predictive Audiences]. Para cada uno, puede definir hasta 50 rasgos o segmentos de base.

 

**¿Cómo puedo generar nuevos segmentos a partir de un segmento de [!UICONTROL Predictive Audiences]?**

Vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** y haga clic en la carpeta **[!UICONTROL Predictive Audiences]**. Busque el segmento deseado, haga un duplicado y edítelo según sus necesidades.

 

**¿Por qué algunos de mis visitantes incorporados no están clasificados?**

Actualmente, la clasificación de audiencias solo funciona para cualificaciones en tiempo real, excepto para usuarios autenticados definidos como parte de [!UICONTROL Profile Merge Rules].

En una actualización futura se agregará la compatibilidad total con los datos incorporados.

 

**¿Cuándo puedo ver los primeros resultados producidos por mi modelo?**

Los resultados del modelo de [!UICONTROL Predictive Audiences] están disponibles en un plazo de 24 horas a partir de la creación del modelo, si este se ejecuta correctamente.

Si el modelo no produce resultados en un plazo de 24 horas, póngase en contacto con su representante de Adobe.

 

**¿Por qué mi modelo no produce resultados o muestra el estado de advertencia?**

Las razones por las que los modelos de [!UICONTROL Predictive Audiences] no producen resultados pueden ser varias:

1. Ninguno de los segmentos o rasgos de personalidad seleccionados tiene suficientes perfiles de usuario. Recomendamos que elija sus rasgos o segmentos de modo que cada personalidad tenga unos cientos de perfiles de usuario, al menos.
1. Ninguno de los segmentos o rasgos de personalidad seleccionados contiene datos suficientes en sus perfiles de usuario (no hay suficientes rasgos para analizar).
1. El rasgo de la audiencia o del segmento objetivo no tuvo usuarios activos o incorporados en los últimos 30 días.
1. Los usuarios de la audiencia destinataria activos o incorporados en los últimos 30 días no tienen datos suficientes en sus perfiles de usuario (no tiene los rasgos suficientes para analizar).

Para obtener resultados relevantes, el algoritmo [!UICONTROL Predictive Audiences] evalúa las realizaciones de rasgos y segmentos en función de la actividad del usuario en tiempo real vista por el DCS. Si selecciona nuevos segmentos y rasgos básicos que aún no tienen suficientes usuarios, el algoritmo puede tardar un par de días en clasificar la audiencia.

Para obtener resultados óptimos, siga las directrices sugeridas en [Criterios de selección de personalidades](../features/algorithmic-models/predictive-audiences.md#selection-personas) y [Criterios de selección de la audiencia de destino](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**¿Por qué mi modelo muestra el estado de error?**

No se pudo ejecutar el modelo. En estos casos, póngase en contacto con su representante de Adobe.

 

**¿Cómo puedo cambiar la regla de combinación de Perfiles para un segmento de Predictive Audiences?**

Haga un duplicado del segmento de [!UICONTROL Predictive Audiences] y cambie la [!UICONTROL Profile Merge Rule] para el segmento duplicado.

 

**¿Podría dejar de clasificarse a un usuario de la audiencia de destino que no forme parte de ningún rasgo o segmento de personalidad?**

Sí, en caso de que el usuario no tenga ningún rasgo en su perfil. En ese caso, el usuario obtendrá una puntuación de coincidencia de 0 en todos los rasgos o segmentos personales y, por lo tanto, no se clasificará en ninguno de los segmentos predictivos.

 

**¿Un usuario que ha sido clasificado en uno de los segmentos predictivos puede reubicarse en otro segmento de [!UICONTROL Predictive Audiences]?**

Sí. Como el algoritmo se forma a diario, aplica los cambios para cada una de las personalidades en términos de puntuación de rasgos. Si un usuario que forma parte de un segmento [!UICONTROL Predictive Audiences] está activo, los cambios en su puntuación de rasgos pueden modificar la clasificación en función de la actividad de los últimos 30 días.

 

**¿Puedo ver los rasgos que rigen la clasificación de audiencias?**

Sí, puede ver todos los rasgos influyentes de todas las líneas de base en la página de creación de informes del modelo. Consulte [Rasgos influyentes](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**¿Qué le ocurre al modelo si edito uno de sus rasgos o segmentos de línea de base?**

El modelo evalúa los rasgos o segmentos una vez al día. La clasificación actualizada debería verse al día siguiente de su actualización.

 

**¿Puedo seleccionar las fuentes de datos de las que aprenderá el modelo?**

No, no se admite la selección de fuentes de datos. El algoritmo de [!UICONTROL Predictive Audiences] aprende de todos los rasgos de origen.