---
description: El modelo de similitud le ayuda a descubrir nuevas audiencias únicas mediante el análisis automatizado de datos. Este artículo proporciona respuestas a las preguntas más frecuentes.
seo-description: Look-Alike Modeling helps you discover new, unique audiences through automated data analysis. This article provides answers to the most frequently asked questions.
seo-title: Look-Alike Modeling FAQ
solution: Audience Manager
title: Preguntas frecuentes sobre modelos de similitud
feature: Algorithmic Models
exl-id: c6e92db0-129f-489e-8cf0-600e0e09698b
source-git-commit: 37823ae54e106e32aa195a6b69e0f1ebfc322f09
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---

# Preguntas frecuentes sobre modelos de similitud

## Información general {#overview}

Este artículo proporciona respuestas a las preguntas más frecuentes acerca de [!UICONTROL Look-Alike Modeling].

## Preguntas {#questions}

**¿Por qué tengo un piso? [!UICONTROL Accuracy & Reach] ¿Gráfica?**

Un piso [!UICONTROL Accuracy & Reach] El gráfico significa que casi todos los usuarios recibieron la misma puntuación por parte del modelo. Esto puede suceder cuando se incluye el rasgo de visitante del sitio en las fuentes de datos en las que se ejecutó el modelo. Para evitarlo, quite el rasgo genérico de la entrada del modelo durante el paso de creación del modelo utilizando [!UICONTROL Exclusions] field.

 

**¿Por qué algunos de mis rasgos más influyentes tienen audiencias muy pequeñas?**

El algoritmo selecciona rasgos que están altamente correlacionados con el rasgo de línea de base. Por ejemplo, si un rasgo determinado tiene una superposición del 100 % con el rasgo de línea de base, tendrá un peso muy alto, incluso si el número de usuarios en ese rasgo es pequeño.

 

**¿Por qué no se ha ejecutado/vuelto a ejecutar mi modelo?**

Los modelos que hayan producido resultados seguirán ejecutándose solo si ha creado al menos un rasgo algorítmico activo y lo ha asignado a un segmento activo y a un destino.

 

**¿Por qué mi modelo no produjo ningún resultado?**

Esto suele deberse a que no hay superposiciones de características significativas entre la población de línea de base y la población de las fuentes de datos seleccionadas.

 

**¿Hay alguna recomendación sobre el rasgo de línea de base o el tamaño del segmento?**

Unos pocos miles de usuarios deberían ser suficientes para ejecutar el modelo, dado que hay una superposición de rasgos significativa entre la población de línea de base y la población en las fuentes de datos seleccionadas. [!UICONTROL Look-Alike Modeling] produce resultados más precisos, cuanto mayor es la línea de base.

 

**¿Qué fuentes de datos de terceros debo elegir para mi modelo?**

Utilice fuentes de datos que tengan al menos alguna superposición con el rasgo o segmento de línea de base, pero que, al mismo tiempo, traigan usuarios adicionales. También debe tener en cuenta el coste asociado a cada fuente de datos. Los modelos de costes y precios varían entre los proveedores de datos en [!UICONTROL Audience Marketplace].

 

**¿Es costoso utilizar datos de terceros para modelar?**

Depende del modelo de precios de la fuente de datos seleccionada. Algunas fuentes permiten el modelado sin costo alguno, mientras que otras le cobran una tarifa. Consulte [Facturación para compradores de fuentes de datos](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md) para obtener más información.

 

**¿Cuántos modelos o rasgos puedo crear?**

Actualmente, puede crear hasta 20 modelos algorítmicos y 50 rasgos algorítmicos.

 

**¿Cuál es la frecuencia de actualización del aprendizaje del modelo y la población de rasgos algorítmicos?**

El modelo se vuelve a entrenar una vez cada 8 días, junto con la actualización de la población de rasgos algorítmicos.
