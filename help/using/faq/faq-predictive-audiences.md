---
description: Predictive Audiences le ayuda a clasificar en tiempo real audiencias desconocidas como personalidades diferenciadas, mediante el uso de la ciencia de datos.
seo-description: Predictive Audiences le ayuda a clasificar en tiempo real audiencias desconocidas como personalidades diferenciadas, mediante el uso de la ciencia de datos.
seo-title: Preguntas frecuentes sobre Predictive Audiences
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 65%

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

1. Ninguno de los personajes seleccionados [!UICONTROL traits] / [!UICONTROL segments] tiene suficientes perfiles de usuario. Le recomendamos que elija su [!UICONTROL traits] o [!UICONTROL segments] para que cada persona tenga al menos unos cuantos cientos de perfiles de usuario.
1. Ninguno de los personajes seleccionados [!UICONTROL traits] / [!UICONTROL segments] tiene datos suficientes en sus perfiles de usuario (no hay suficientes características que analizar).
1. La característica o el segmento de audiencia de destinatario no tiene ningún usuario activo o integrado.
1. Los usuarios de la audiencia destinataria activos o incorporados en los últimos 30 días no tienen datos suficientes en sus perfiles de usuario (no tiene los rasgos suficientes para analizar).
1. El segmento de audiencia de destinatario utiliza un [!UICONTROL Profile Merge Rule] diferente del que eligió para el modelo.
1. Es posible que la fuente de datos de sus características de audiencia de destinatario no se incluya en el [!UICONTROL Profile Merge Rule] que eligió para el modelo.

Para obtener resultados óptimos, siga las directrices sugeridas en [Criterios de selección de personalidades](../features/algorithmic-models/predictive-audiences.md#selection-personas) y [Criterios de selección de la audiencia de destino](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**[!UICONTROL Error]¿Por qué mi modelo muestra el estado de ?**

No se pudo ejecutar el modelo. En esos casos, póngase en contacto con su [!DNL Adobe] representante.

 

**¿Cómo puedo cambiar el  [!UICONTROL Profile Merge Rule] de  [!UICONTROL Predictive Audiences] [!UICONTROL segment]?**

Para crear un nuevo modelo, seleccione las mismas funciones y audiencia de destinatario que el modelo anterior. Durante la creación del modelo, asigne un [!UICONTROL Profile Merge Rule] diferente.

>[!WARNING]
> Como alternativa, puede utilizar [Generador de segmentos](../features/segments/segment-builder.md) para crear manualmente un [!UICONTROL segment] con un predictivo [!UICONTROL trait] existente y asignarlo como [!UICONTROL Profile Merge Rule] de su elección.
> 
> Sin embargo, no recomendamos esta práctica, ya que la [!UICONTROL traits] predictiva hereda automáticamente el [!UICONTROL Profile Merge Rule] modelo al que pertenecen y se construye a partir de [!UICONTROL traits] influyentes que cumplen con el [!UICONTROL Profile Merge Rule] modelo.

 

**¿Qué  [!UICONTROL Profile Merge Rule] debería elegir?**

Al elegir [!UICONTROL Profile Merge Rule] para el modelo, analice detenidamente el caso de uso.

Supongamos que la audiencia de destinatario [!UICONTROL segment] utiliza un [!UICONTROL Profile Merge Rule] basado en perfiles autenticados + [!DNL Device Graph] y selecciona el mismo [!UICONTROL Profile Merge Rule] para el predictivo [!UICONTROL segments]. En este caso, tanto el nivel del dispositivo como el nivel entre dispositivos [!UICONTROL traits] se utilizarán para entrenar el modelo y para colocar al usuario en un [!UICONTROL segment] predictivo.

Sin embargo, si selecciona un [!UICONTROL Profile Merge Rule] basado solamente en perfiles de dispositivos, ninguno de los [!UICONTROL traits] dispositivos cruzados tendrá influencia y no contribuirá a la ubicación de los usuarios en un [!UICONTROL segment] predictivo. Esto puede afectar negativamente a la precisión y al alcance del modelo.

Analice detenidamente el caso de uso y decida de qué tipos [!UICONTROL trait] desea que el modelo aprenda y qué tipo de datos desea que el modelo utilice para la clasificación.

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