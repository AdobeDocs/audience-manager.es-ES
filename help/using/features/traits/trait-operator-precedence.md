---
description: El Generador de rasgos evalúa las expresiones según el orden de operaciones que se indican a continuación, de alta a baja prioridad. Los elementos de características definidos por los operadores de prioridad alta se evalúan primero, antes que otros operadores de prioridad. Esta sección clasifica cada operador según la prioridad, de alta a baja.
seo-description: El Generador de rasgos evalúa las expresiones según el orden de operaciones que se indican a continuación, de alta a baja prioridad. Los elementos de características definidos por los operadores de prioridad alta se evalúan primero, antes que otros operadores de prioridad. Esta sección clasifica cada operador según la prioridad, de alta a baja.
seo-title: Orden de las operaciones en el Generador de rasgos
solution: Audience Manager
title: Orden de las operaciones en el Generador de rasgos
uuid: df 325047-af 62-45 ad -9 ca 1-046 bfcbe 5341
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Order of Operations in Trait Builder {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] evalúa las expresiones según el orden de operaciones que se indica a continuación, de alta a baja prioridad. Los elementos de características definidos por los operadores de prioridad alta se evalúan primero, antes que otros operadores de prioridad. Esta sección clasifica cada operador según la prioridad, de alta a baja.

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
   <td colname="col3"> Menor que, mayor que, menor que/igual a, mayor que/igual a que se evalúa a continuación. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operadores de igualdad </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> Igual a, no es igual a se evalúa después de los operadores anteriores. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> AND</span> </td> 
   <td colname="col2"><span class="wintitle"> AND</span> </td> 
   <td colname="col3" morerows="1"> n.d. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> OR</span> </td> 
   <td colname="col2"><span class="wintitle"> O</span> </td> 
   <td colname="col3" morerows="1"> n.d. </td> 
  </tr> 
 </tbody>
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Uso de expresiones booleanas (AND, OR, NOT) en traitbuilder](../../reference/boolean-expressions-tsb.md)
>* [Uso de operadores de comparación en traitbuilder](../../features/traits/trait-comparison-operators.md)

