---
description: En este artículo se explica cómo las herramientas de segmentos y características del Audience Manager utilizan las expresiones booleanas AND, OR y NOT.
seo-description: En este artículo se explica cómo las herramientas de segmentos y características del Audience Manager utilizan las expresiones booleanas AND, OR y NOT.
seo-title: Expresiones booleanas en el Generador de características y segmentos
solution: Audience Manager
title: Expresiones booleanas en el Generador de características y segmentos
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 0%

---


# Expresiones booleanas en el Generador de características y segmentos{#boolean-expressions-in-trait-and-segment-builder}

En este artículo se explica cómo las herramientas de segmentos y características del Audience Manager utilizan las expresiones booleanas AND, OR y NOT.

<!-- 

c_tb_boolean.xml

 -->

**Expresiones booleanas**

La lógica booleana es una rama de álgebra que utiliza algunas expresiones básicas (o operadores) para determinar si una afirmación es verdadera o falsa. Los operadores más comunes son [!UICONTROL AND], [!UICONTROL OR]y [!UICONTROL NOT]. Las combinaciones de estas expresiones le ayudan a hacer que las reglas de cualificación de segmentos o características específicas se adapten de forma exclusiva a sus requisitos de datos. La siguiente ilustración muestra cómo funcionan las expresiones booleanas básicas.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>El [!UICONTROL NOT] operador utiliza una condición implícita &quot;y&quot; y a veces se escribe como [!UICONTROL AND NOT].

**Cómo utilizar Expresiones booleanas en el Generador de características y segmentos**

Puede crear reglas de clasificación de rasgos y segmentos con expresiones booleanas. En la tabla siguiente se describen las prácticas recomendadas generales para crear criterios de cualificación con [!UICONTROL AND], [!UICONTROL OR]y [!UICONTROL NOT].

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Expresión </th> 
   <th colname="col2" class="entry"> Utilícelo para crear </th> 
   <th colname="col3" class="entry"> Para calificar </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> Y</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de cualificación de audiencia estrechos y centrados. </p> </td> 
   <td colname="col3"> <p>Los usuarios <i>deben</i> pertenecer a todas las características o segmentos especificados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> O</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de cualificación de audiencia amplios y menos centrados. </p> </td> 
   <td colname="col3"> <p>Los usuarios <i>pueden</i> pertenecer a cualquier característica o segmento especificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NO</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de cualificación de audiencia estrechos y centrados. </p> <p>Resulta útil cuando hay varias condiciones que dificultan o hacen ineficiente la definición de los requisitos de cualificación de audiencias. En ocasiones, es más fácil realizar validaciones con requisitos que excluyen en lugar de incluir. </p> </td> 
   <td colname="col3"> <p>Los usuarios no <i>deben</i> pertenecer a un rasgo o segmento excluido. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Ejemplo de caso de uso **

El [!UICONTROL AND] operador resulta útil cuando se han enumerado fácilmente los requisitos de pertenencia a rasgos. Por ejemplo: supongamos que necesita crear una audiencia de &quot;compradores de cámaras costosas&quot;. Con un modelo de píxeles, tendría que crear y colocar píxeles para las cámaras y un valor de precio numérico en la página. Por el contrario, con las características, puede aplicar operadores booleanos para manejar ambas condiciones (precio de las cámaras [!UICONTROL AND] ). El resultado es una recopilación de datos eficiente con menos llamadas HTTP, lo que a su vez ayuda a preservar la experiencia del usuario en el sitio.

**[!UICONTROL OR]Ejemplo de caso de uso **

El [!UICONTROL OR] operador resulta útil cuando se desea crear señales con requisitos de cualificación de audiencia amplios. Si tiene varios requisitos de calificación de rasgos o segmentos, el [!UICONTROL OR] operador evaluará como verdadero cuando los visitantes del sitio exhiban *cualquiera* de esas características. [!UICONTROL OR] puede resultar muy útil cuando desee crear rápidamente una amplia audiencia de visitantes calificados del sitio.

**[!UICONTROL AND NOT]Ejemplo de caso de uso **

El [!UICONTROL AND NOT] operador resulta útil cuando es más fácil definir una audiencia por *exclusión* que por *inclusión*. Por ejemplo: supongamos que tiene una venta y desea segmentar visitantes en clientes que solo vean artículos a precio completo. En lugar de crear una lista de señales para todos los artículos de precio completo o de venta que cumplen los requisitos, puede ser más fácil calificar visitantes si *no han* visto un artículo de precio de venta. Esto es administrativamente eficiente porque normalmente tiene menos artículos de precio de venta que los ofrecidos a precio completo. Con un booleano [!UICONTROL NOT], los visitantes no *deben* mostrar la señal de venta para poder optar a la suscripción a audiencia a precio completo. Por el contrario, [!UICONTROL AND NOT] es lo contrario del caso de [!UICONTROL AND] uso, que muestra cómo la pertenencia a la audiencia se determina mediante la inclusión (es decir, el visitante se califica sobre la base de 2 señales explícitamente declaradas).

>[!MORELIKETHIS]
>
>* [Uso de operadores de comparación en TraitBuilder](../features/traits/trait-comparison-operators.md)
>* [Orden de las operaciones en Expresiones de TraitBuilder](../features/traits/trait-operator-precedence.md)

