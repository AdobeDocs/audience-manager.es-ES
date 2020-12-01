---
description: El Generador de características evalúa las expresiones según el orden de operaciones que se indica a continuación, de prioridad alta a baja. Los elementos de características definidos por operadores de prioridad alta se evalúan primero, antes que otros operadores de prioridad. Esta sección clasifica cada operador según la prioridad, de alto a bajo.
seo-description: El Generador de características evalúa las expresiones según el orden de operaciones que se indica a continuación, de prioridad alta a baja. Los elementos de características definidos por operadores de prioridad alta se evalúan primero, antes que otros operadores de prioridad. Esta sección clasifica cada operador según la prioridad, de alto a bajo.
seo-title: Orden de las operaciones en el generador de rasgos
solution: Audience Manager
title: Orden de las operaciones en el generador de rasgos
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 13%

---


# Orden de las operaciones en el generador de rasgos {#order-of-operations-in-trait-builder}

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
   <td colname="col2"> &lt;&gt; &lt;&gt;= </td> 
   <td colname="col3"> A continuación se evalúan menos que, bueno que, menor o igual que, bueno o igual a. </td> 
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

>[!MORELIKETHIS]
>
>* [Uso de Expresiones booleanas (AND, OR, NOT) en TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Uso de operadores de comparación en TraitBuilder](../../features/traits/trait-comparison-operators.md)

