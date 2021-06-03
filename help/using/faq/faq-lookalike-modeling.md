---
description: El modelado de similitud le ayuda a descubrir audiencias nuevas y únicas mediante el análisis automatizado de datos. Este artículo proporciona respuestas a las preguntas más frecuentes.
seo-description: El modelado de similitud le ayuda a descubrir audiencias nuevas y únicas mediante el análisis automatizado de datos. Este artículo proporciona respuestas a las preguntas más frecuentes.
seo-title: Preguntas frecuentes sobre modelos de similitud
solution: Audience Manager
title: Preguntas frecuentes sobre modelos de similitud
feature: Modelos algorítmicos
source-git-commit: cf9368d4690b61066646054543cc60d390eea021
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---

# Preguntas frecuentes sobre modelos de similitud

## Información general {#overview}

Este artículo proporciona respuestas a las preguntas más frecuentes sobre [!UICONTROL Look-Alike Modeling].

## Preguntas {#questions}

**¿Por qué recibo un  [!UICONTROL Accuracy & Reach] gráfico plano?**

Un gráfico plano [!UICONTROL Accuracy & Reach] significa que casi todos los usuarios recibieron la misma puntuación por parte del modelo. Esto puede suceder cuando se incluye la característica de visitante del sitio en las fuentes de datos en las que se ejecutó el modelo. Para evitarlo, elimine el rasgo genérico de la entrada del modelo durante el paso de creación del modelo utilizando el campo [!UICONTROL Exclusions].

 

**¿Por qué algunas de mis características más influyentes tienen audiencias muy pequeñas?**

El algoritmo selecciona características que están altamente correlacionadas con el rasgo de línea de base. Por ejemplo, si un rasgo determinado se superpone en un 100% con el rasgo de línea de base, tendrá un peso muy alto, incluso si el número de usuarios de ese rasgo es pequeño.

 

**¿Por qué no se ha ejecutado o vuelto a ejecutar mi modelo?**

Los modelos que hayan producido resultados seguirán ejecutándose únicamente si ha creado al menos un rasgo algorítmico activo y lo ha asignado a un segmento activo y a un destino.

 

**¿Por qué mi modelo no produjo ningún resultado?**

Esto suele deberse a que no hay superposiciones significativas de características entre la población de la línea de base y la población en las fuentes de datos seleccionadas.

 

**¿Hay alguna recomendación sobre el rasgo de línea de base o el tamaño del segmento?**

Unos pocos miles de usuarios deberían ser suficientes para ejecutar el modelo en , dado que hay una superposición significativa de características entre la población de línea de base y la población en las fuentes de datos seleccionadas. [!UICONTROL Look-Alike Modeling] produce resultados más precisos, mientras mayor sea la línea base.

 

**¿Qué fuentes de datos de terceros debo elegir para mi modelo?**

Utilice fuentes de datos que tengan al menos cierta superposición con su rasgo o segmento de línea de base, pero que al mismo tiempo incorporen usuarios adicionales. También debe tener en cuenta el coste asociado a cada fuente de datos. Los modelos de precios y costos varían entre los proveedores de datos en [!UICONTROL Audience Marketplace].

 

**¿Costará utilizar datos de terceros para el modelado?**

Depende del modelo de precios de la fuente de datos seleccionada. Algunas fuentes permiten el modelado sin costo alguno, mientras que otras le cobran una tarifa. Consulte [Facturación para compradores de fuentes de datos](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md) para obtener más información.

 

**¿Cuántos modelos/rasgos puedo crear?**

Actualmente, puede crear hasta 20 modelos algorítmicos y 50 rasgos algorítmicos.

 

**¿Cuál es la frecuencia de actualización de la formación del modelo y la población de rasgos algorítmicos?**

El modelo se vuelve a entrenar una vez cada 8 días, junto con la actualización de la población de rasgos algorítmicos.