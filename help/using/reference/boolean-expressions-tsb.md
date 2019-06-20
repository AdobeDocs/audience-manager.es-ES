---
description: Este artículo explica cómo las herramientas de características y segmentos de Audience Manager usan las expresiones booleanas AND, OR y NOT.
seo-description: Este artículo explica cómo las herramientas de características y segmentos de Audience Manager usan las expresiones booleanas AND, OR y NOT.
seo-title: Expresiones booleanas en el Generador de segmentos y características
solution: Audience Manager
title: Expresiones booleanas en el Generador de segmentos y características
uuid: 14 f 02 d 3 f -4 c 84-41 fe-bc 91-b 34 f 0 d 49574 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Boolean Expressions in Trait and Segment Builder{#boolean-expressions-in-trait-and-segment-builder}

Este artículo explica cómo las herramientas de características y segmentos de Audience Manager usan las expresiones booleanas AND, OR y NOT.

<!-- 

c_tb_boolean.xml

 -->

**Expresiones booleanas**

La lógica booleana es una rama de algebra que utiliza unas pocas expresiones básicas (o operadores) para determinar si una instrucción es verdadera o falsa. The most common operators are [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT]. Las combinaciones de estas expresiones le ayudan a hacer que las reglas de calificación de segmentos o características específicas se ajusten exclusivamente a sus requisitos de datos. La siguiente ilustración muestra cómo funcionan las expresiones booleanas básicas.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>[!UICONTROL NOT] El operador utiliza una condición &quot;and&quot; implícita y a veces se escribe como [!UICONTROL AND NOT].

**Cómo utilizar expresiones booleanas en el Generador de segmentos y características**

Las reglas de cualificación de segmentos y características se crean con expresiones booleanas. The table below describes general best practices for creating qualification criteria with [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT].

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
   <td colname="col2"> <p>Requisitos limitados de cualificación de audiencia. </p> </td> 
   <td colname="col3"> <p>Users <i>must</i> belong to all specified traits or segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OR</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de cualificación de audiencia amplia y menos enfocada. </p> </td> 
   <td colname="col3"> <p>Users <i>can</i> belong to any specified traits or segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NO</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos limitados de cualificación de audiencia. </p> <p>Útil cuando existen varias condiciones que hacen que la definición de requisitos de cualificación de audiencia sea difícil o ineficiente. En ocasiones, es más fácil validar los requisitos que excluyen en lugar de incluir. </p> </td> 
   <td colname="col3"> <p>Users <i>must not</i> belong to an excluded trait or segment. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Ejemplo de caso de uso**

[!UICONTROL AND] El operador es útil cuando se han enumerado fácilmente requisitos de pertenencia a rasgos. Por ejemplo, supongamos que necesita crear una audiencia de «compradores costosos de cámara». »» Con un modelo de píxeles, tendría que crear y colocar píxeles para las cámaras y un valor numérico en la página. By contrast, with traits you can apply Boolean operators to handle both conditions (cameras [!UICONTROL AND] price). El resultado es una recopilación de datos eficaz con menos llamadas HTTP que, a su vez, ayudan a preservar la experiencia del usuario en el sitio.

**[!UICONTROL OR]Ejemplo de caso de uso**

[!UICONTROL OR] El operador es útil cuando se desea crear señales con requisitos amplios de cualificación de audiencia. If you have several trait or segment qualification requirements, the [!UICONTROL OR] operator will evaluate to true when your site visitors exhibit *any* of those characteristics. [!UICONTROL OR] puede resultar más útil cuando desee crear rápidamente una amplia audiencia de visitantes cualificados del sitio.

**[!UICONTROL AND NOT]Ejemplo de caso de uso**

[!UICONTROL AND NOT] El operador es útil cuando es más fácil definir una audiencia por *exclusión* en lugar *de inclusión*. Por ejemplo: supongamos que está teniendo una venta y desea segmentar a los visitantes en los clientes que solo vean artículos de precio completo. Rather than create a list of signals for all qualifying full or sale-price items, it may be easier to qualify visitors if they have *not* seen a sale price item. Esto es administrativamente eficaz porque generalmente tiene menos artículos de precio de venta en comparación con los ofrecidos a precio completo. With a Boolean [!UICONTROL NOT], visitors *must not* exhibit the sale signal to qualify for full-price audience membership. By contrast, [!UICONTROL AND NOT] is the opposite of the [!UICONTROL AND] use case, which showed how audience membership is determined by inclusion (i.e., the visitor qualified based on 2 explicitly stated signals).

>[!MORE_ LIKE_ THIS]
>
>* [Uso de operadores de comparación en traitbuilder](../features/traits/trait-comparison-operators.md)
>* [Orden de las operaciones en expresiones traitbuilder](../features/traits/trait-operator-precedence.md)

