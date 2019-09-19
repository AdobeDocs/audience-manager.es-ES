---
description: El Generador de características evalúa las expresiones según el orden de operaciones que se indica a continuación, de prioridad alta a baja. Los elementos de características definidos por operadores de prioridad alta se evalúan primero, antes que otros operadores de prioridad. Esta sección clasifica cada operador según la prioridad, de alto a bajo.
seo-description: El Generador de características evalúa las expresiones según el orden de operaciones que se indica a continuación, de prioridad alta a baja. Los elementos de características definidos por operadores de prioridad alta se evalúan primero, antes que otros operadores de prioridad. Esta sección clasifica cada operador según la prioridad, de alto a bajo.
seo-title: Orden de las operaciones en el generador de características
solution: Audience Manager
title: Orden de las operaciones en el generador de características
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Orden de las operaciones en el generador de características {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] evalúa las expresiones según el orden de operaciones que se indica a continuación, de prioridad alta a baja. Los elementos de características definidos por operadores de prioridad alta se evalúan primero, antes que otros operadores de prioridad. Esta sección clasifica cada operador según la prioridad, de alto a bajo.

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prioridad del operador </th> 
   <th colname="col2" class="entry"> Símbolo </th> 
   <th colname="col3" class="entry"> Comentarios </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Paréntesis </td> 
   <td colname="col2"> ( ) </td> 
   <td colname="col3"> Las expresiones entre paréntesis siempre se evalúan primero y siguen el orden de prioridad. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operadores de comparación </td> 
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> A continuación se evalúan los valores menores que, mayores que, menores o iguales que, mayores o iguales a. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operadores de igualdad </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> Igual a, no igual a, se evalúan después de los operadores anteriores. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> AND</span> </td> 
   <td colname="col2"><span class="wintitle"> Y</span> </td> 
   <td colname="col3" morerows="1"> n.d. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Booleano <span class="wintitle"> OR</span> </td> 
   <td colname="col2"><span class="wintitle"> O</span> </td> 
   <td colname="col3" morerows="1"> n.d. </td> 
  </tr> 
 </tbody>
</table>

>[!MORE_LIKE_THIS]
>
>* [Uso de expresiones booleanas (AND, OR, NOT) en TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Uso de operadores de comparación en TraitBuilder](../../features/traits/trait-comparison-operators.md)

