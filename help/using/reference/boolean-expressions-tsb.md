---
description: En este artículo se explica cómo las herramientas de segmentos y rasgos del Audience Manager utilizan las expresiones booleanas AND, OR y NOT.
seo-description: En este artículo se explica cómo las herramientas de segmentos y rasgos del Audience Manager utilizan las expresiones booleanas AND, OR y NOT.
seo-title: Expresiones booleanas en el Generador de rasgos y segmentos
solution: Audience Manager
title: Expresiones booleanas en el Generador de rasgos y segmentos
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: Reference
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 4%

---

# Expresiones booleanas en el Generador de rasgos y segmentos{#boolean-expressions-in-trait-and-segment-builder}

En este artículo se explica cómo las herramientas de segmentos y rasgos del Audience Manager utilizan las expresiones booleanas AND, OR y NOT.

<!-- 

c_tb_boolean.xml

 -->

**Expresiones booleanas**

La lógica booleana es una rama de álgebra que utiliza algunas expresiones básicas (u operadores) para determinar si una instrucción es verdadera o falsa. Los operadores más comunes son [!UICONTROL AND], [!UICONTROL OR] y [!UICONTROL NOT]. Las combinaciones de estas expresiones le ayudan a hacer que las reglas de clasificación de rasgos o segmentos sean especialmente adecuadas para sus requisitos de datos. La siguiente ilustración muestra cómo funcionan las expresiones booleanas básicas.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>El operador [!UICONTROL NOT] utiliza una condición implícita &quot;y&quot; y a veces se escribe como [!UICONTROL AND NOT].

**Cómo utilizar expresiones booleanas en el generador de rasgos y segmentos**

Las reglas de clasificación de rasgos y segmentos se crean con expresiones booleanas. En la tabla siguiente se describen las prácticas recomendadas generales para crear criterios de clasificación con [!UICONTROL AND], [!UICONTROL OR] y [!UICONTROL NOT].

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Expresión </th> 
   <th colname="col2" class="entry"> Utilícelo para crear </th> 
   <th colname="col3" class="entry"> Para clasificar </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> Y</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de cualificación de audiencia estrechos y centrados. </p> </td> 
   <td colname="col3"> <p>Los usuarios <i>deben</i> pertenecer a todos los rasgos o segmentos especificados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> O</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de cualificación de audiencia amplios y menos centrados. </p> </td> 
   <td colname="col3"> <p>Los usuarios <i>pueden</i> pertenecer a cualquier rasgo o segmento especificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NO</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de cualificación de audiencia estrechos y centrados. </p> <p>Resulta útil cuando hay varias condiciones que hacen que definir los requisitos de cualificación de audiencia sea difícil o ineficiente. En ocasiones, es más fácil validar con requisitos que excluyen en lugar de incluir. </p> </td> 
   <td colname="col3"> <p>Los usuarios <i>no deben</i> pertenecer a un rasgo o segmento excluido. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Ejemplo de caso de uso**

El operador [!UICONTROL AND] resulta útil cuando se han enumerado fácilmente los requisitos de pertenencia a rasgos. Por ejemplo, supongamos que necesita crear una audiencia de &quot;compradores de cámaras caras&quot;. Con un modelo de píxeles, tendría que crear y colocar píxeles para las cámaras y un valor de precio numérico en la página. Por el contrario, con las características, puede aplicar operadores booleanos para manejar ambas condiciones (precio de las cámaras [!UICONTROL AND]). El resultado es una recopilación de datos eficiente con menos llamadas HTTP, lo que a su vez ayuda a preservar la experiencia del usuario en el sitio.

**[!UICONTROL OR]Ejemplo de caso de uso**

El operador [!UICONTROL OR] es útil cuando desea crear señales con requisitos de cualificación de audiencia amplios. Si tiene varios requisitos de clasificación de rasgos o segmentos, el operador [!UICONTROL OR] evaluará como verdadero cuando los visitantes del sitio exhiban *cualquier* de esas características. [!UICONTROL OR] puede ser más útil cuando desea crear rápidamente una amplia audiencia de visitantes del sitio calificados.

**[!UICONTROL AND NOT]Ejemplo de caso de uso**

El operador [!UICONTROL AND NOT] resulta útil cuando es más fácil definir una audiencia por *exclusión* que por *inclusión*. Por ejemplo, supongamos que tiene una venta y desea segmentar a los visitantes en clientes que solo vean artículos de precio completo. En lugar de crear una lista de señales para todos los artículos de precio completo o de venta que cumplen los requisitos, puede ser más fácil calificar a los visitantes si han visto *no* un artículo de precio de venta. Esto es administrativamente eficiente porque normalmente tiene menos artículos de precio de venta en comparación con los que se ofrecen a precio completo. Con un booleano [!UICONTROL NOT], los visitantes *no deben* mostrar la señal de venta para calificar para la pertenencia a una audiencia a precio completo. Por el contrario, [!UICONTROL AND NOT] es lo contrario del caso de uso [!UICONTROL AND] , que muestra cómo se determina la pertenencia a la audiencia mediante la inclusión (es decir, el visitante cumple los requisitos según 2 señales explícitamente declaradas).

>[!MORELIKETHIS]
>
>* [Uso de operadores de comparación en TraitBuilder](../features/traits/trait-comparison-operators.md)
>* [Orden de operaciones en expresiones de TraitBuilder](../features/traits/trait-operator-precedence.md)

