---
description: Ejemplos que puede consultar para crear expresiones en el editor de código del Generador de expresiones.
seo-description: Ejemplos que puede consultar para crear expresiones en el editor de código del Generador de expresiones.
seo-title: Expresiones de muestra con operadores booleanos y de comparación
solution: Audience Manager
title: Expresiones de muestra con operadores booleanos y de comparación
uuid: ee 74 c 376-2099-4816-8694-43 f 58845 a 0 ac
translation-type: tm+mt
source-git-commit: 92b75773d2bbe2f635d84bd5bffe625d2023b6cf

---


# Sample Expressions With Boolean and Comparison Operators {#sample-expressions-with-boolean-and-comparison-operators}

Examples you can refer to for creating expressions in the [!UICONTROL Expression Builder] code editor.

## Code Samples Overview {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

Create your own trait rules with the [!UICONTROL Expression Builder] code editor. Los siguientes ejemplos pueden ayudarle a empezar. Some of the examples preface the *`key`* variable with `c_` to identify it as a user-defined variable. Include the `c_` prefix (or any other naming convention) for *`key`* variable if your event calls send data to [!DNL Audience Manager] using that syntax.

## Boolean Expressions {#boolean-expressions}

### Ejemplo Y

The rule establishes trait qualification requirements using Boolean [!UICONTROL AND] operators.

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Código de muestra </th> 
   <th colname="col2" class="entry"> Para cumplir los requisitos, un visitante debe </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_ make = = "A") AND (c_ model = = "B") AND (c_ search = = "1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">Busque una marca y modelo específicos. </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">Busque el producto desde una página de resultados de búsqueda (search = "1" o "true"). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Ejemplo O

This rule establishes trait qualification requirements using [!DNL Boolean] [!UICONTROL OR] and [!UICONTROL AND] operators.

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Código de muestra </th> 
   <th colname="col2" class="entry"> Para cumplir los requisitos, un visitante debe </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a = = "1" OR b = = "1") AND (c = = "new")</code> </td> 
   <td colname="col2"> Meet the conditions set by variables <code><i>a </i></code> or <code><i>b </i></code> and <code><i>c </i></code>. </td> 
  </tr> 
 </tbody> 
</table>

## Ejemplo de intervalo con mayor que, menor que, igual a

Esta regla establece los requisitos de cualificación de características usando un intervalo.

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Código de muestra </th> 
   <th colname="col2" class="entry"> Para cumplir los requisitos, un visitante debe </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(precio &gt; = 1,00 Y precio &lt; = 100,00)</code> </td> 
   <td colname="col2"> Cumpla cualquier condición de precio entre 1,00 y 100,00. </td> 
  </tr> 
 </tbody> 
</table>