---
description: El Generador de rasgos evalúa las expresiones según el orden de operaciones que se indica a continuación, de alta a baja prioridad. Los elementos de rasgos definidos por operadores de alta prioridad se evalúan primero, antes que otros operadores de prioridad. Esta sección clasifica cada operador según su prioridad, de alta a baja.
seo-description: Trait Builder evaluates expressions according to the order-of-operations listed below, from high to low precedence. Trait elements defined by high-precedence operators are evaluated first, before other precedence operators. This section ranks each operator according to precedence, from high to low.
seo-title: Order of Operations in Trait Builder
solution: Audience Manager
title: Orden de las operaciones en el generador de rasgos
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
feature: Traits
exl-id: 90700479-4a8e-4a07-81ef-2e9d8a1d9f15
TQID: https://experienceleague.adobe.com/Jfmytv1c-4Uc8q2UGVU5Lgx-iOZ-yk2sSzc8iRviBAs
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 161
ht-degree: 3%

---

# Orden de las operaciones en el generador de rasgos {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] evalúa las expresiones según el orden de operaciones que se indica a continuación, de prioridad alta a baja. Los elementos de rasgos definidos por operadores de alta prioridad se evalúan primero, antes que otros operadores de prioridad. Esta sección clasifica cada operador según su prioridad, de alta a baja.

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prioridad de operador </th> 
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
   <td colname="col3"> A continuación, se evalúan menor que, mayor que, menor que/igual a, mayor que/igual a. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operadores de igualdad </td> 
   <td colname="col2"> ¡==!= </td> 
   <td colname="col3"> Igual a, no igual a se evalúan después de los operadores anteriores. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Booleano <span class="wintitle"> Y </span> </td> 
   <td colname="col2"><span class="wintitle"> Y </span> </td> 
   <td colname="col3" morerows="1"> n.d. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Booleano <span class="wintitle"> O </span> </td> 
   <td colname="col2"><span class="wintitle"> O </span> </td> 
   <td colname="col3" morerows="1"> n.d. </td> 
  </tr> 
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Trabajo con expresiones booleanas (AND, OR, NOT) en TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Trabajando con operadores de comparación en TraitBuilder](../../features/traits/trait-comparison-operators.md)
