---
description: Ejemplos a los que puede hacer referencia para crear expresiones en el editor de código del Generador de Expresiones.
seo-description: Ejemplos a los que puede hacer referencia para crear expresiones en el editor de código del Generador de Expresiones.
seo-title: Expresiones de muestra con operadores booleanos y de comparación
solution: Audience Manager
title: Expresiones de muestra con operadores booleanos y de comparación
uuid: ee74c376-2099-4816-8694-43f58845a0ac
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 12%

---


# Expresiones de muestra con operadores booleanos y de comparación {#sample-expressions-with-boolean-and-comparison-operators}

Ejemplos a los que puede hacer referencia para crear expresiones en el editor de código [!UICONTROL Expression Builder].

## Información general de ejemplos de código {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

Cree sus propias reglas de características con el editor de código [!UICONTROL Expression Builder]. Los siguientes ejemplos pueden ayudarle a empezar. Algunos ejemplos muestran la variable *`key`* con `c_` como prefijo para identificarla como una variable definida por el usuario. Incluya el prefijo `c_` (o cualquier otra convención de nombres) para la variable *`key`* si las llamadas de evento envían datos a [!DNL Audience Manager] mediante esa sintaxis.

## Expresiones booleanas {#boolean-expressions}

### Ejemplo AND

La regla establece requisitos de calificación de rasgos mediante operadores booleanos [!UICONTROL AND].

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

### Ejemplo OR

Esta regla establece requisitos de calificación de características mediante operadores [!DNL Boolean] [!UICONTROL OR] y [!UICONTROL AND].

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

## Ejemplo de rango con Bueno que es igual a, menor que

Esta regla establece requisitos de cualificación de características mediante un intervalo.

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