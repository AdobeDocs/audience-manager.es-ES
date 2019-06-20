---
description: Generador de segmentos permite crear reglas de características para un segmento mediante un editor de código. Haga clic en la ficha Expresiones de segmento (Vista de código) del panel Características para acceder a esta función.
seo-description: Generador de segmentos permite crear reglas de características para un segmento mediante un editor de código. Haga clic en la ficha Expresiones de segmento (Vista de código) del panel Características para acceder a esta función.
seo-title: Sintaxis de código utilizada en el Editor de expresiones de segmentos
solution: Audience Manager
title: Sintaxis de código utilizada en el Editor de expresiones de segmentos
uuid: 7 b 4 b 06 ca -7879-4501-8 ba 7-b 2 b 6467 b 8 a 3 b
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Code Syntax Used in the Segment Expression Editor {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] permite crear reglas de características para un segmento mediante un editor de código. Click the **[!UICONTROL Segment Expressions (Code View)]** tab in the [!UICONTROL Traits] panel to access this feature.

## Sintaxis del código del Generador de expresiones

Puede agregar reglas de características a un segmento con código en lugar de utilizar funciones de arrastrar y soltar. Al codificar, reemplace elementos en cursiva en el ejemplo con una expresión o valor real. El código base utiliza la siguiente sintaxis:

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>By default, [!DNL Boolean] [!UICONTROL OR] conditions apply to multiple traits *within* an expression.

### Unir segmentos con operadores booleanos

To build groups of segments, wrap the frequency function in parenthesis and set the relationship *between* each expression with a [!DNL Boolean] operator ([!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT]).

### Parámetros

>[!NOTE]
>
>Se requieren todos los parámetros a menos que se indique lo contrario.

| Nombre o variable | Descripción |
|---|---|
| `FREQUENCY` | Literal que debe preceder a la expresión. |
| ` [`&lt;`traitID`&gt;`T]` | An array of trait IDs followed by the letter `T`. Separe varias características con una coma. Por ejemplo, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *(Opcional)* Establece reglas de actualización en características del segmento. The letter `D` indicates recency in days. |
| ` <Frequency Operator><Numeric Value>` | Establece reglas de frecuencia en características del segmento. |

### Operadores de actualización y actualización permitidos

Set [recency and frequency](../../features/segments/recency-and-frequency.md) intervals with a comparison operator and an integer. [!UICONTROL Segment Builder] utiliza expresiones estándar como &lt; (menor que), &gt; (mayor que), = = (igual), etc. Sin embargo, los tipos de operadores permitidos varían al establecer la frecuencia o frecuencia. En la tabla siguiente se enumeran los operadores de frecuencia y actualización permitidos.

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Operadores de actualización </th> 
   <th colname="col2" class="entry"> Operadores de frecuencia </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt; = (mayor que/igual a) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt; = (menor que/igual a) </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt; = (mayor que/igual a) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt; = (menor que/igual a) </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">= = (igual a) </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Actualización y frecuencia](../../features/segments/recency-and-frequency.md)
>* [Expresiones booleanas en el Generador de segmentos y características](../../reference/boolean-expressions-tsb.md)
>* [Uso de operadores de comparación en traitbuilder](../../features/traits/trait-comparison-operators.md)
>* [Orden de las operaciones en expresiones traitbuilder](../../features/traits/trait-operator-precedence.md)

