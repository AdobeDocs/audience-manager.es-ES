---
description: El Generador de segmentos le permite versión reglas de características para una segmento mediante un código editor. Haga clic en el pestaña Expresiones de segmento (Code Ver) del panel Características para acceder a esta función.
seo-description: Segment Builder lets you build trait rules for a segment using a code editor. Click the Segment Expressions (Code View) tab in the Traits panel to access this feature.
seo-title: Code Syntax Used in the Segment Expression Editor
solution: Audience Manager
title: Code Sintaxis utilizada en el editor de expresiones de segmento
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
feature: Segments
exl-id: 64fa6f03-cef9-4187-866f-28c54f45f72e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 4%

---

# Code Sintaxis utilizada en el editor de expresiones de segmento {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] Permite versión reglas de rasgos para una segmento mediante un código editor. Haga clic en la **[!UICONTROL Segment Expressions (Code View)]** pestaña del [!UICONTROL Traits] panel para acceder a esta función.

## Sintaxis de Code del Generador de expresiones

Puede agregar reglas de características a una segmento con código en lugar de usar funciones de arrastrar y soltar. Al codificar, reemplace los elementos en cursiva en el ejemplo por un valor o expresión real. El código base utiliza la siguiente sintaxis:

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>De forma predeterminada, [!DNL Boolean] [!UICONTROL OR] las condiciones se aplican a varias características *dentro de* una expresión.

### Unirse segmentos con operadores booleanos

Para versión grupos de segmentos, ajuste la función Frecuencia entre paréntesis y establezca la relación *entre* cada expresión con un [!DNL Boolean] operador ([!UICONTROL AND], [!UICONTROL OR], y [!UICONTROL NOT]).

### Parámetros

>[!NOTE]
>
>Todos los parámetros son necesarios a menos que se indique lo contrario.

| Nombre o Variable | Descripción |
|---|---|
| `FREQUENCY` | Un literal que debe preceder al expresión. |
| ` [``traitID`>`T]` | Una matriz de identificadores de rasgos seguida de la letra `T`. Separe las características múltiples con una coma. Por ejemplo, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *(Opcional)* Establece reglas de actualización sobre las características del segmento. La carta `D` indica lo reciente en días. |
| ` <Frequency Operator><Numeric Value>` | Establece Frecuencia reglas sobre las características del segmento. |

### Operadores de actualización y frecuencia permitidos

Establezca [los intervalos de Frecuencia y actualización](../../features/segments/recency-and-frequency.md) con un operador de comparación y un número entero. [!UICONTROL Segment Builder] Utiliza expresiones estándar gustar &lt; (less than), > (mayor que), == (igual), etc. Sin embargo, los tipos de operadores permitidos varían cuando se configura la actualización o la Frecuencia. En la tabla siguiente se enumeran los operadores de actualización o Frecuencia permitidos.

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Operadores actualización </th> 
   <th colname="col2" class="entry"> Operadores de frecuencia </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;= (mayor que/igual que) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;= (less than/equal to) </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;= (mayor que/igual que) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;= (less than/equal to) </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">== (igual a) </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Fecha de adquisición más frecuente y frecuencia.](../../features/segments/recency-and-frequency.md)
>* [Expresiones booleanas en el Generador de rasgos y segmentos](../../reference/boolean-expressions-tsb.md)
>* [Trabajo con operadores de comparación en TraitBuilder](../../features/traits/trait-comparison-operators.md)
>* [Orden de operaciones en expresiones TraitBuilder](../../features/traits/trait-operator-precedence.md)
