---
description: Las Audiencias predictivas ayudan a clasificar audiencias desconocidas en personalidades distintas en tiempo real, mediante el uso de la ciencia de datos.
seo-description: Las Audiencias predictivas ayudan a clasificar audiencias desconocidas en personalidades distintas en tiempo real, mediante el uso de la ciencia de datos.
seo-title: Preguntas más frecuentes sobre Audiencias predictivas
solution: Audience Manager
title: Audiencias predictivas de Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 0%

---


# Preguntas más frecuentes sobre Audiencias predictivas

Preguntas más frecuentes sobre [!UICONTROL Predictive Audiences].

 

**¿Cuándo debo usar[!UICONTROL Predictive Audiences]en oposición a[!UICONTROL Look-alike modeling]?**

[!UICONTROL Predictive Audiences] y [!UICONTROL Look-alike modeling] atender diferentes casos de uso. Las principales diferencias entre los dos algoritmos son las siguientes:

1. [!UICONTROL Look-alike modeling] toma una pequeña audiencia como entrada y la expande. [!UICONTROL Predictive Audiences] toma una audiencia grande como entrada y la divide en audiencias distintas más pequeñas, definidas por las personas.
1. El número de segmentos base es diferente para cada algoritmo. [!UICONTROL Predictive Audiences] requiere al menos dos líneas de base, mientras que [!UICONTROL Look-alike modeling] utiliza una línea de base como máximo.
1. [!UICONTROL Predictive Audiences] realiza una evaluación de segmentos en tiempo real, mientras que [!UICONTROL Look-alike modeling] no lo hace.

En función de su caso de uso, debe decidir qué modelo será más relevante para usted.

Se puede pensar en construir un [!UICONTROL Predictive Audiences] modelo con una serie de líneas de base como el equivalente de construir el mismo número de modelos similares, solamente sin la evaluación en tiempo real, y con una alta probabilidad de tener visitantes que pertenezcan a varias personas diferentes, en lugar de una persona distinta.

 

**¿Cuántas personas o modelos puedo crear?**

Puede crear hasta 10 [!UICONTROL Predictive Audiences] modelos. Para cada modelo, puede definir hasta 50 rasgos o segmentos de línea de base.

 

**¿Cómo puedo generar nuevos segmentos a partir de un[!UICONTROL Predictive Audiences]segmento?**

Vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** y haga clic en la **[!UICONTROL Predictive Audiences]** carpeta. Busque el segmento deseado, duplicado y edítelo según sus necesidades.

 

**¿Por qué algunos de mis visitantes incorporados no están clasificados?**

Actualmente, la clasificación de audiencias solo funciona para cualificaciones en tiempo real, excepto para usuarios autenticados que se definieron como parte de [!UICONTROL Profile Merge Rules].

En una actualización futura se agregará compatibilidad total con los datos incorporados.

 

**¿Cuándo puedo ver los primeros resultados producidos por mi modelo?**

[!UICONTROL Predictive Audiences] los resultados del modelo están disponibles en un plazo de 24 horas a partir de la creación del modelo, si éste se ejecuta correctamente.

Si el modelo no produce resultados en un plazo de 24 horas, póngase en contacto con su representante de Adobe.

 

**¿Por qué mi modelo no produce resultados o muestra el estado de advertencia?**

[!UICONTROL Predictive Audiences] los modelos pueden no producir resultados debido a una serie de razones:

1. Ninguno de los segmentos o características personales seleccionados tiene suficientes perfiles de usuario. Le recomendamos que elija sus características o segmentos para que cada persona tenga al menos unos pocos cientos de perfiles de usuario.
1. Ninguno de los segmentos o características personales seleccionados tiene datos suficientes en sus perfiles de usuario (no hay suficientes características que analizar).
1. La característica de audiencia de destinatario/segmento no tenía usuarios activos o integrados en los últimos 30 días.
1. Los usuarios de la audiencia de destinatario que estuvieron activos o integrados en los últimos 30 días no tienen datos suficientes en sus perfiles de usuario (no son suficientes para analizar).

Para obtener resultados relevantes, el algoritmo evalúa las [!UICONTROL Predictive Audiences] realizaciones de rasgos y segmentos en función de la actividad del usuario en tiempo real que ve el DCS. Si selecciona nuevas características básicas y segmentos que aún no tienen suficientes usuarios, el algoritmo puede tardar un par de días en clasificar la audiencia.

Para obtener resultados óptimos, siga las directrices sugeridas en Criterios de [selección para personas](../features/algorithmic-models/predictive-audiences.md#selection-personas) y Criterios [de selección para la Audiencia](../features/algorithmic-models/predictive-audiences.md#selection-audience)de Destinatarios.

 

**¿Por qué mi modelo muestra el estado de error?**

No se pudo ejecutar el modelo. En estos casos, póngase en contacto con su representante de Adobe.

 

**¿Cómo puedo cambiar la regla de combinación de Perfiles para un segmento de Audiencias predictivas?**

Duplicado el [!UICONTROL Predictive Audiences] segmento y cambie el [!UICONTROL Profile Merge Rule] para el segmento duplicado.

 

**¿Podría no clasificarse a un usuario de la audiencia de destinatario que no forme parte de ningún rasgo o segmento personal?**

Sí, en caso de que el usuario no tenga ninguna característica en su perfil. En ese caso, el usuario obtendrá una puntuación de coincidencia de 0 con todos los rasgos o segmentos personales y, por lo tanto, no se clasificará en ninguno de los segmentos predictivos.

 

**¿Puede un usuario clasificado en uno de los segmentos predictivos reclasificarse en otro[!UICONTROL Predictive Audiences]segmento?**

Sí. Dado que el algoritmo se forma diariamente, aplica los cambios para cada una de las personas en términos de puntuación de características. Si un usuario que forma parte de un [!UICONTROL Predictive Audiences] segmento está activo, los cambios en su puntuación de características pueden cambiar la clasificación en función de la actividad de los últimos 30 días.

 

**¿Puedo ver las características por las que se realiza la clasificación de audiencias?**

Sí, puede ver todas las características influyentes de todas las líneas de base en la página de sistema de informes del modelo. Consulte Características [influyentes](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**¿Qué sucede con el modelo si edito una de sus características o segmentos de línea base?**

El modelo evalúa las características o segmentos una vez al día. Debe ver la clasificación actualizada al día siguiente de la actualización.

 

**¿Puedo seleccionar las fuentes de datos de las que aprenderá el modelo?**

No, no se admite la selección de fuentes de datos. El algoritmo [!UICONTROL Predictive Audiences] aprende de todas las características de origen.