---
description: Ejemplos a los que puede hacer referencia para crear expresiones en el editor de código del generador de expresiones.
seo-description: Examples you can refer to for creating expressions in the Expression Builder code editor.
seo-title: Sample Expressions With Boolean and Comparison Operators
solution: Audience Manager
title: Expresiones de muestra con operadores booleanos y de comparación
uuid: ee74c376-2099-4816-8694-43f58845a0ac
feature: Traits
exl-id: 68041d61-7942-4c2f-9e78-f2b2f803ef59
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 10%

---

# Expresiones de muestra con operadores booleanos y de comparación {#sample-expressions-with-boolean-and-comparison-operators}

Ejemplos a los que puede hacer referencia para crear expresiones en [!UICONTROL Expression Builder] editor de código.

## Información general sobre ejemplos de código {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

Cree sus propias reglas de rasgos con [!UICONTROL Expression Builder] editor de código. Los siguientes ejemplos pueden ayudarle a empezar. Algunos de los ejemplos preceden al *`key`* variable con `c_` para identificarla como una variable definida por el usuario. Incluya el `c_` prefijo (o cualquier otra convención de nomenclatura) para *`key`* si las llamadas de evento envían datos a [!DNL Audience Manager] usando esa sintaxis.

## Expresiones booleanas {#boolean-expressions}

### Ejemplo de Y

La regla establece los requisitos de clasificación de rasgos mediante booleano [!UICONTROL AND] operadores.

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Código de muestra </th> 
   <th colname="col2" class="entry"> Para cumplir los requisitos, un visitante debe </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_make=="A") AND (c_model=="B") AND (c_search=="1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">Busque una marca y un modelo específicos. </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">Busque el producto desde una página de resultados de búsqueda (búsqueda = "1" o "true"). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Ejemplo de OR

Esta regla establece los requisitos de clasificación de rasgos mediante [!DNL Boolean] [!UICONTROL OR] y [!UICONTROL AND] operadores.

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Código de muestra </th> 
   <th colname="col2" class="entry"> Para cumplir los requisitos, un visitante debe </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a== "1" OR b=="1") AND (c=="new")</code> </td> 
   <td colname="col2"> Cumplir las condiciones establecidas por las variables <code><i>a </i></code> o <code><i>b </i></code> y <code><i>c </i></code>. </td> 
  </tr> 
 </tbody> 
</table>

## Ejemplo de rango con Bueno que, menor que, igual a

Esta regla establece los requisitos de clasificación de rasgos mediante un rango.

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Código de muestra </th> 
   <th colname="col2" class="entry"> Para cumplir los requisitos, un visitante debe </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(price &gt;= 1.00 AND price &lt;= 100.00)</code> </td> 
   <td colname="col2"> Cumplir cualquier condición de precio entre 1.00 y 100.00. </td> 
  </tr> 
 </tbody> 
</table>
