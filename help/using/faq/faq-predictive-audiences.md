---
description: Predictive Audiences le ayuda a clasificar en tiempo real audiencias desconocidas como personalidades diferenciadas, mediante el uso de la ciencia de datos.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences FAQ
solution: Audience Manager
title: Preguntas frecuentes sobre Predictive Audiences
feature: Algorithmic Models
exl-id: 21073970-8457-470b-89fc-724a118a18d2
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '949'
ht-degree: 59%

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

 

**¿Cuándo puedo ver los primeros resultados producidos por mi modelo?**

Los resultados del modelo de [!UICONTROL Predictive Audiences] están disponibles en un plazo de 24 horas a partir de la creación del modelo, si este se ejecuta correctamente.

Si el modelo no produce resultados en un plazo de 24 horas, póngase en contacto con su representante de Adobe.

 

**¿Por qué mi modelo no produce resultados o muestra el estado de advertencia?**

Las razones por las que los modelos de [!UICONTROL Predictive Audiences] no producen resultados pueden ser varias:

1. Ninguno de los personajes seleccionados [!UICONTROL traits] / [!UICONTROL segments] tiene suficientes perfiles de usuario. Recomendamos que elija su [!UICONTROL traits] o [!UICONTROL segments] de modo que cada personalidad tenga unos cientos de perfiles de usuario, al menos.
1. Ninguno de los personajes seleccionados [!UICONTROL traits] / [!UICONTROL segments] tienen suficientes datos en sus perfiles de usuario (no hay suficientes rasgos para analizar).
1. El rasgo de la audiencia o del segmento objetivo no tiene usuarios activos o incorporados.
1. Los usuarios de la audiencia destinataria activos o incorporados en los últimos 30 días no tienen datos suficientes en sus perfiles de usuario (no tiene los rasgos suficientes para analizar).
1. El segmento de audiencia de destino utiliza un [!UICONTROL Profile Merge Rule] del que eligió para el modelo.
1. Es posible que la fuente de datos de los rasgos de la audiencia de destino no se incluya en la [!UICONTROL Profile Merge Rule] que eligió para el modelo.

Para obtener resultados óptimos, siga las directrices sugeridas en [Criterios de selección de personalidades](../features/algorithmic-models/predictive-audiences.md#selection-personas) y [Criterios de selección de la audiencia de destino](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**[!UICONTROL Error]¿Por qué mi modelo muestra el estado de ?**

No se pudo ejecutar el modelo. En estos casos, póngase en contacto con su [!DNL Adobe] representante.

 

**¿Cómo puedo cambiar el [!UICONTROL Profile Merge Rule] para un [!UICONTROL Predictive Audiences] [!UICONTROL segment]?**

Cree un nuevo modelo seleccionando las mismas personas y la misma audiencia de destino que el modelo anterior. Durante la creación del modelo, asigne un diferente [!UICONTROL Profile Merge Rule].

>[!WARNING]
> Como alternativa, puede utilizar [Generador de segmentos](../features/segments/segment-builder.md) para crear manualmente una [!UICONTROL segment] con un predictivo existente [!UICONTROL trait] y asígnele un [!UICONTROL Profile Merge Rule] de su elección.
> 
> Sin embargo, no recomendamos esta práctica, ya que es predictiva [!UICONTROL traits] heredar automáticamente el [!UICONTROL Profile Merge Rule] del modelo al que pertenecen y se crean a partir de elementos influyentes [!UICONTROL traits] que cumplan con las [!UICONTROL Profile Merge Rule] del modelo.

 

**Qué [!UICONTROL Profile Merge Rule] ¿Debo elegir?**

Al elegir el [!UICONTROL Profile Merge Rule] para el modelo, analice detenidamente el caso de uso.

Digamos que su audiencia de destino [!UICONTROL segment] utiliza un [!UICONTROL Profile Merge Rule] basado en perfiles autenticados + [!DNL Device Graph] perfiles y se selecciona lo mismo [!UICONTROL Profile Merge Rule] para el predictivo [!UICONTROL segments]. En este caso, tanto a nivel de dispositivo como a nivel de dispositivo cruzado [!UICONTROL traits] se utilizará en la formación del modelo y en la ubicación del usuario en un elemento predictivo [!UICONTROL segment].

Sin embargo, si selecciona una [!UICONTROL Profile Merge Rule] basado únicamente en perfiles de dispositivo, ninguno de los dispositivos cruzados [!UICONTROL traits] será influyente y no contribuirá a colocar a los usuarios en una actividad predictiva [!UICONTROL segment]. Esto puede afectar negativamente a la precisión y el alcance del modelo.

Analice su caso de uso con cuidado y decida cuál [!UICONTROL trait] tipos de los que desea que el modelo aprenda y qué tipo de datos desea que utilice para la clasificación.

**¿Podría dejar de clasificarse a un usuario de la audiencia de destino que no forme parte de ningún rasgo o segmento de personalidad?**

Sí, en caso de que el usuario no tenga ningún rasgo en su perfil. En ese caso, el usuario obtendrá una puntuación de coincidencia de 0 en todos los rasgos o segmentos personales y, por lo tanto, no se clasificará en ninguno de los segmentos predictivos.

 

**¿Un usuario que ha sido clasificado en uno de los segmentos predictivos puede reubicarse en otro segmento de [!UICONTROL Predictive Audiences]?**

Sí. Como el algoritmo se forma a diario, aplica los cambios para cada una de las personalidades en términos de puntuación de rasgos. Si un usuario que forma parte de un segmento [!UICONTROL Predictive Audiences] está activo, los cambios en su puntuación de rasgos pueden modificar la clasificación en función de la actividad de los últimos 30 días.

 

**¿Puedo ver los rasgos que rigen la clasificación de audiencias?**

Sí, puede ver todos los rasgos influyentes de todas las líneas de base en la página de creación de informes del modelo. Consulte [Rasgos influyentes](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**¿Puedo cambiar el tiempo de vida (TTL) de los rasgos predictivos?**

El TTL de rasgo predictivo se establece en 0 (duración) y no se puede cambiar. [!UICONTROL Predictive Audiences] solo puede anular la segmentación de usuarios de segmentos predictivos cuando cumplen los requisitos para el segmento base o cuando se reclasifican en un segmento predictivo diferente.

Si es necesario, puede solucionar esta funcionalidad creando un nuevo segmento que contenga un rasgo predictivo y un rasgo de actividad con un TTL especificado.

 


**¿Qué le ocurre al modelo si edito uno de sus rasgos o segmentos de línea de base?**

El modelo evalúa los rasgos o segmentos una vez al día. La clasificación actualizada debería verse al día siguiente de su actualización.

 

**¿Puedo seleccionar las fuentes de datos de las que aprenderá el modelo?**

No, no se admite la selección de fuentes de datos. El algoritmo de [!UICONTROL Predictive Audiences] aprende de todos los rasgos de origen.
