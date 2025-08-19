---
description: En este artículo se explica cómo las herramientas de rasgo Audience Manager y segmento usan las expresiones booleanas AND, OR y NOT.
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

En este artículo se explica cómo las herramientas de rasgo Audience Manager y segmento usan las expresiones booleanas AND, OR y NOT.

<!-- 

c_tb_boolean.xml

 -->

**Expresiones booleanas**

La lógica booleana es un Rama de álgebra que utiliza algunas expresiones básicas (u operadores) para determinar si una afirmación es verdadera o falsa. Los operadores más comunes son [!UICONTROL AND], [!UICONTROL OR], y [!UICONTROL NOT]. Las combinaciones de estas expresiones le ayudan a crear reglas de rasgos enfocados o segmento calificación que se adapten exclusivamente a sus requisitos de datos. En la siguiente ilustración se muestra cómo funcionan las expresiones booleanas básicas.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>El [!UICONTROL NOT] operador utiliza una condición &quot;y&quot; implícita y a veces se escribe como [!UICONTROL AND NOT].

**Cómo usar expresiones booleanas en el Generador de rasgos y segmentos**

Se versión reglas de calificación de rasgos y segmento con expresiones booleanas. En la tabla siguiente se describen las prácticas recomendadas generales para crear criterios de cualificación con [!UICONTROL AND], [!UICONTROL OR], y [!UICONTROL NOT].

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Expresión </th> 
   <th colname="col2" class="entry"> Úselo para crear </th> 
   <th colname="col3" class="entry"> Para calificar </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> Y</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de calificación de audiencia estrechos y enfocados. </p> </td> 
   <td colname="col3"> <p>Los usuarios <i>deben</i> pertenecer a todos los rasgos o segmentos especificados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> O</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de calificación de audiencia amplios, menos enfocados. </p> </td> 
   <td colname="col3"> <p>Los usuarios <i>pueden</i> pertenecer a cualquier rasgo o segmento especificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NO</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de calificación de audiencia estrechos y enfocados. </p> <p>Útil cuando existen múltiples condiciones que dificultan o ineficientes la definición de audiencia requisitos de cualificación. En ocasiones, es más fácil validar con respecto a los requisitos que excluyen en lugar de incluir. </p> </td> 
   <td colname="col3"> <p>Los usuarios <i>no</i> deben pertenecer a ningún rasgo o segmento excluido. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Ejemplo de caso de uso**

El [!UICONTROL AND] operador es útil cuando se han enumerado fácilmente los requisitos de la abono de características. Por ejemplo, supongamos que necesita crear un audiencia de &quot;compradores caros de cámaras&quot;. Con un modelo de píxeles, tendría que crear y colocar píxeles para cámaras y un valor de precio numérica en su Página. Por el contrario, con las características se pueden aplicar operadores booleanos para manejar ambas condiciones (precio de la cámara [!UICONTROL AND] ). El resultado es una recopilación de datos eficiente con menos llamadas HTTP, lo que, a su vez, ayuda a preservar el experiencia del usuario en su sitio.

**[!UICONTROL OR]Ejemplo de caso de uso**

El [!UICONTROL OR] operador es útil cuando se desea crear señales con amplios requisitos de audiencia cualificación. Si tiene varios requisitos de rasgos o segmento calificación, el [!UICONTROL OR] operador evaluará a verdadero cuando los visitantes de su sitio exhiban *alguna* de esas características. [!UICONTROL OR] puede ser más útil cuando desea crear rápidamente una amplia audiencia de visitantes calificados del sitio.

**[!UICONTROL AND NOT]Ejemplo de caso de uso**

El [!UICONTROL AND NOT] operador es útil cuando resulta más fácil definir un audiencia por exclusión *que* por *inclusión*. Por ejemplo, supongamos que está teniendo una venta y desea segmento visitantes en clientes que solo miran artículos de precio completo. En lugar de crear un lista de señales para todos los artículos completos o de precio de venta que califiquen, puede ser más fácil calificar a los visitantes si no *han* visto un artículo con precio de venta. Esto es administrativamente eficiente porque generalmente tiene menos artículos de precio de venta en comparación con los ofrecidos a precio completo. Con un booleano [!UICONTROL NOT], los visitantes *no* deben exhibir la señal de venta para calificar para el precio completo audiencia abono. Por el contrario, [!UICONTROL AND NOT] es lo opuesto al [!UICONTROL AND] caso de uso, que mostró cómo audiencia abono se determina por inclusión (es decir, el visitante calificado en función de 2 señales explícitamente establecidas).

>[!MORELIKETHIS]
>
>* [Trabajo con operadores de comparación en TraitBuilder](../features/traits/trait-comparison-operators.md)
>* [Orden de operaciones en expresiones TraitBuilder](../features/traits/trait-operator-precedence.md)
