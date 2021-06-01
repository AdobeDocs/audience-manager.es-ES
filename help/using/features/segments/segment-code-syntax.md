---
description: El Generador de segmentos le permite generar reglas de características para un segmento mediante un editor de código. Haga clic en la ficha Expresiones de segmentos (Vista de código) del panel Características para acceder a esta función.
seo-description: El Generador de segmentos le permite generar reglas de características para un segmento mediante un editor de código. Haga clic en la ficha Expresiones de segmentos (Vista de código) del panel Características para acceder a esta función.
seo-title: Sintaxis del código utilizada en el Editor de Expresiones de segmentos
solution: Audience Manager
title: Sintaxis del código utilizada en el Editor de Expresiones de segmentos
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
feature: 'Segmentos '
exl-id: 64fa6f03-cef9-4187-866f-28c54f45f72e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 11%

---

# Sintaxis del código utilizada en el Editor de Expresiones de segmentos {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] permite crear reglas de características para un segmento mediante un editor de código. Haga clic en la pestaña **[!UICONTROL Segment Expressions (Code View)]** del panel [!UICONTROL Traits] para acceder a esta función.

## Sintaxis del código del generador de expresiones

Puede agregar reglas de características a un segmento con código en lugar de usar las funciones de arrastrar y soltar. Al codificar, reemplace los elementos en cursiva del ejemplo con una expresión o valor reales. El código base utiliza la siguiente sintaxis:

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>De forma predeterminada, las condiciones [!DNL Boolean] [!UICONTROL OR] se aplican a varios rasgos *dentro de* una expresión.

### Unir segmentos con operadores booleanos

Para crear grupos de segmentos, ajuste la función de frecuencia entre paréntesis y establezca la relación *entre* cada expresión con un operador [!DNL Boolean] ([!UICONTROL AND], [!UICONTROL OR] y [!UICONTROL NOT]).

### Parámetros

>[!NOTE]
>
>Todos los parámetros son obligatorios a menos que se indique lo contrario.

| Nombre o variable | Descripción |
|---|---|
| `FREQUENCY` | Un literal que debe preceder a la expresión. |
| ` [`&lt;`traitID`>`T]` | Matriz de ID de rasgos seguida de la letra `T`. Separe varias características con una coma. Por ejemplo, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *(Opcional)* Establece las reglas de actualización sobre las características del segmento. La letra `D` indica la actualización en días. |
| ` <Frequency Operator><Numeric Value>` | Establece las reglas de frecuencia en las características del segmento. |

### Operadores de actualización y frecuencia permitidos

Establezca intervalos de [actualización y frecuencia](../../features/segments/recency-and-frequency.md) con un operador de comparación y un número entero. [!UICONTROL Segment Builder] utiliza expresiones estándar como  &lt;> (buenas que), == (igual), etc. Sin embargo, los tipos de operadores permitidos varían cuando se establece la actualización o la frecuencia. En la tabla siguiente se enumeran los operadores de frecuencia y actualización permitidos.

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
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;= (bueno/igual que) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;&gt; </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;= (bueno/igual que) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;&gt; </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">== (igual a) </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Fecha de adquisición más frecuente y frecuencia.](../../features/segments/recency-and-frequency.md)
* [Expresiones booleanas en el Generador de rasgos y segmentos](../../reference/boolean-expressions-tsb.md)
* [Uso de operadores de comparación en TraitBuilder](../../features/traits/trait-comparison-operators.md)
* [Orden de operaciones en expresiones de TraitBuilder](../../features/traits/trait-operator-precedence.md)

