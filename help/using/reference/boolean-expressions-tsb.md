---
description: En este artículo se explica cómo las herramientas de rasgos y segmentos de Audience Manager utilizan las expresiones booleanas AND, OR y NOT.
seo-description: This article explains how the Audience Manager trait and segment tools use the Boolean expressions AND, OR, and NOT.
seo-title: Boolean Expressions in Trait and Segment Builder
solution: Audience Manager
title: Expresiones booleanas en el Generador de rasgos y segmentos
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: Reference
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 0%

---

# Expresiones booleanas en el Generador de rasgos y segmentos{#boolean-expressions-in-trait-and-segment-builder}

En este artículo se explica cómo las herramientas de rasgos y segmentos de Audience Manager utilizan las expresiones booleanas AND, OR y NOT.

<!-- 

c_tb_boolean.xml

 -->

**Expresiones booleanas**

La lógica booleana es una rama de álgebra que utiliza algunas expresiones básicas (u operadores) para determinar si una instrucción es verdadera o falsa. Los operadores más comunes son [!UICONTROL AND], [!UICONTROL OR] y [!UICONTROL NOT]. Las combinaciones de estas expresiones le ayudan a hacer que las reglas de calificación de segmentos o rasgos centrados se adapten de forma exclusiva a sus requisitos de datos. La siguiente ilustración muestra cómo funcionan las expresiones booleanas básicas.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>El operador [!UICONTROL NOT] usa una condición &quot;and&quot; implícita y a veces se escribe como [!UICONTROL AND NOT].

**Cómo usar expresiones booleanas en el generador de rasgos y segmentos**

Las reglas de cualificación de rasgos y segmentos se crean con expresiones booleanas. En la tabla siguiente se describen las prácticas recomendadas generales para crear criterios de calificación con [!UICONTROL AND], [!UICONTROL OR] y [!UICONTROL NOT].

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Expresión </th> 
   <th colname="col2" class="entry"> Úselo para crear. </th> 
   <th colname="col3" class="entry"> Para calificar </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> Y </span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de cualificación de audiencia específicos y restringidos. </p> </td> 
   <td colname="col3"> <p>Los usuarios <i>deben</i> pertenecer a todos los rasgos o segmentos especificados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> O </span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de cualificación de audiencia amplios y menos centrados. </p> </td> 
   <td colname="col3"> <p>Los usuarios <i>pueden</i> pertenecer a cualquier rasgo o segmento especificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NO </span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de cualificación de audiencia específicos y restringidos. </p> <p>Resulta útil cuando hay varias condiciones que hacen que la definición de requisitos de cualificación de audiencia sea difícil o ineficiente. En ocasiones, es más fácil validarlo con requisitos que excluyen en lugar de incluir. </p> </td> 
   <td colname="col3"> <p>Los usuarios <i>no deben</i> pertenecer a un rasgo o segmento excluido. </p> </td> 
  </tr> 
 </tbody> 
</table>

Ejemplo de caso de uso **[!UICONTROL AND]**

El operador [!UICONTROL AND] es útil cuando se han enumerado fácilmente los requisitos de pertenencia a características. Por ejemplo, supongamos que necesita crear una audiencia de &quot;compradores de cámaras caros&quot;. Con un modelo de píxeles, tendría que crear y colocar píxeles para cámaras y un valor de precio numérico en su página. Por el contrario, con las características puede aplicar operadores booleanos para controlar ambas condiciones (precio de cámaras [!UICONTROL AND]). El resultado es una recopilación de datos eficaz con menos llamadas HTTP, lo que a su vez ayuda a preservar la experiencia del usuario en el sitio.

Ejemplo de caso de uso **[!UICONTROL OR]**

El operador [!UICONTROL OR] es útil cuando desea crear señales con requisitos amplios de cualificación de audiencia. Si tiene varios requisitos de clasificación de rasgos o segmentos, el operador [!UICONTROL OR] evaluará como verdadero cuando los visitantes del sitio muestren *cualquiera* de esas características. [!UICONTROL OR] puede ser muy útil cuando desea crear rápidamente una audiencia amplia de visitantes del sitio calificados.

Ejemplo de caso de uso **[!UICONTROL AND NOT]**

El operador [!UICONTROL AND NOT] es útil cuando es más fácil definir una audiencia por *exclusión* que por *inclusión*. Por ejemplo, supongamos que tiene una venta y desea segmentar a los visitantes en clientes que solo ven artículos con precio completo. En lugar de crear una lista de señales para todos los artículos con precio total o precio de venta que cumplen los requisitos, puede ser más fácil calificar a los visitantes si *no* ha visto un artículo con precio de venta. Esto es eficiente desde el punto de vista administrativo, ya que normalmente tiene menos artículos a precio de venta en comparación con los que se ofrecen a precio completo. Con un valor booleano [!UICONTROL NOT], los visitantes *no deben* mostrar la señal de venta para poder pertenecer a la audiencia a precio completo. Por el contrario, [!UICONTROL AND NOT] es lo contrario al caso de uso [!UICONTROL AND], que mostró cómo la pertenencia a la audiencia está determinada por la inclusión (es decir, el visitante se calificó en función de 2 señales explícitamente establecidas).

>[!MORELIKETHIS]
>
>* [Trabajando con operadores de comparación en TraitBuilder](../features/traits/trait-comparison-operators.md)
>* [Orden de operaciones en expresiones de TraitBuilder](../features/traits/trait-operator-precedence.md)
