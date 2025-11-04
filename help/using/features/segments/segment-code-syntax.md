---
description: El Generador de segmentos le permite crear reglas de rasgos para un segmento mediante un editor de código. Haga clic en la pestaña Expresiones de segmentos (vista de código) del panel Características para acceder a esta función.
seo-description: Segment Builder lets you build trait rules for a segment using a code editor. Click the Segment Expressions (Code View) tab in the Traits panel to access this feature.
seo-title: Code Syntax Used in the Segment Expression Editor
solution: Audience Manager
title: Sintaxis del código utilizada en el Editor de expresiones de segmentos
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
feature: Segments
exl-id: 64fa6f03-cef9-4187-866f-28c54f45f72e
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 4%

---

# Sintaxis del código utilizada en el Editor de expresiones de segmentos {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] le permite generar reglas de rasgos para un segmento mediante un editor de código. Haga clic en la ficha **[!UICONTROL Segment Expressions (Code View)]** del panel [!UICONTROL Traits] para obtener acceso a esta característica.

## Sintaxis del código del generador de expresiones

Puede añadir reglas de rasgos a un segmento con código en lugar de utilizar las funciones de arrastrar y soltar. Al codificar, reemplace los elementos en cursiva del ejemplo por una expresión o un valor reales. El código base utiliza la siguiente sintaxis:

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>De manera predeterminada, las condiciones de [!DNL Boolean] [!UICONTROL OR] se aplican a varios rasgos *dentro de* una expresión.

### Unir segmentos con operadores booleanos

Para generar grupos de segmentos, ajuste la función de frecuencia entre paréntesis y establezca la relación *entre* cada expresión con un operador [!DNL Boolean] ([!UICONTROL AND], [!UICONTROL OR] y [!UICONTROL NOT]).

### Parámetros

>[!NOTE]
>
>Todos los parámetros son obligatorios a menos que se indique lo contrario.

| Nombre o variable | Descripción |
|---|---|
| `FREQUENCY` | Un literal que debe preceder a la expresión. |
| `[`&lt;`traitID`>`T]` | Una matriz de ID de rasgos seguida de la letra `T`. Separe varios rasgos con una coma. Por ejemplo, `[123T, 456T]`. |
| `<Recency Operator><Numeric Value>D` | *(Opcional)* Establece reglas de actualización en rasgos del segmento. La carta `D` indica la actualización en días. |
| `<Frequency Operator><Numeric Value>` | Establece reglas de frecuencia sobre las características del segmento. |

### Operadores de actualización y frecuencia permitidos

Establezca [intervalos de actualización y frecuencia](../../features/segments/recency-and-frequency.md) con un operador de comparación y un entero. [!UICONTROL Segment Builder] utiliza expresiones estándar como &lt; (menor que), > (mayor que), == (igual), etc. Sin embargo, los tipos de operadores permitidos varían cuando se establece la actualización o la frecuencia. En la tabla siguiente se enumeran los operadores de actualización/frecuencia permitidos.

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
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;= (mayor o igual que) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;= (menor/igual que) </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;= (mayor o igual que) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;= (menor/igual que) </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">== (igual a) </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Fecha de adquisición más frecuente y frecuencia.](../../features/segments/recency-and-frequency.md)
>* [Expresiones booleanas en el Generador de rasgos y segmentos](../../reference/boolean-expressions-tsb.md)
>* [Trabajando con operadores de comparación en TraitBuilder](../../features/traits/trait-comparison-operators.md)
>* [Orden de operaciones en expresiones de TraitBuilder](../../features/traits/trait-operator-precedence.md)
