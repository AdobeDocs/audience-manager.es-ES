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
source-wordcount: '528'
ht-degree: 3%

---

# Expresiones booleanas en el Generador de rasgos y segmentos{#boolean-expressions-in-trait-and-segment-builder}

En este artículo se explica cómo las herramientas de rasgos y segmentos de Audience Manager utilizan las expresiones booleanas AND, OR y NOT.

<!-- 

c_tb_boolean.xml

 -->

**Expresiones booleanas**

La lógica booleana es una rama de álgebra que utiliza algunas expresiones básicas (u operadores) para determinar si una instrucción es verdadera o falsa. Los operadores más comunes son [!UICONTROL AND], [!UICONTROL OR], y [!UICONTROL NOT]. Las combinaciones de estas expresiones le ayudan a hacer que las reglas de calificación de segmentos o rasgos centrados se adapten de forma exclusiva a sus requisitos de datos. La siguiente ilustración muestra cómo funcionan las expresiones booleanas básicas.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>El [!UICONTROL NOT] utiliza una condición &quot;and&quot; implícita y, a veces, se escribe como [!UICONTROL AND NOT].

**Cómo utilizar expresiones booleanas en el generador de rasgos y segmentos**

Las reglas de cualificación de rasgos y segmentos se crean con expresiones booleanas. La siguiente tabla describe las prácticas recomendadas generales para crear criterios de cualificación con [!UICONTROL AND], [!UICONTROL OR], y [!UICONTROL NOT].

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
   <td colname="col1"> <p><b><span class="wintitle"> Y</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de cualificación de audiencia específicos y restringidos. </p> </td> 
   <td colname="col3"> <p>Usuarios <i>debe</i> pertenecen a todos los rasgos o segmentos especificados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> O</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de cualificación de audiencia amplios y menos centrados. </p> </td> 
   <td colname="col3"> <p>Usuarios <i>lata</i> pertenecen a cualquier rasgo o segmento especificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NO</span></b> </p> </td> 
   <td colname="col2"> <p>Requisitos de cualificación de audiencia específicos y restringidos. </p> <p>Resulta útil cuando hay varias condiciones que hacen que la definición de requisitos de cualificación de audiencia sea difícil o ineficiente. En ocasiones, es más fácil validarlo con requisitos que excluyen en lugar de incluir. </p> </td> 
   <td colname="col3"> <p>Usuarios <i>no debe</i> pertenecen a un rasgo o segmento excluido. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Ejemplo de caso de uso**

El [!UICONTROL AND] es útil cuando se han enumerado fácilmente los requisitos de pertenencia a características. Por ejemplo, supongamos que necesita crear una audiencia de &quot;compradores de cámaras caros&quot;. Con un modelo de píxeles, tendría que crear y colocar píxeles para cámaras y un valor de precio numérico en su página. Por el contrario, con los rasgos puede aplicar operadores booleanos para gestionar ambas condiciones (cámaras) [!UICONTROL AND] precio). El resultado es una recopilación de datos eficaz con menos llamadas HTTP, lo que a su vez ayuda a preservar la experiencia del usuario en el sitio.

**[!UICONTROL OR]Ejemplo de caso de uso**

El [!UICONTROL OR] es útil cuando desea crear señales con requisitos amplios de cualificación de audiencia. Si tiene varios requisitos de clasificación de rasgos o segmentos, la variable [!UICONTROL OR] evaluará como verdadero cuando los visitantes del sitio muestren *cualquiera* de dichas características. [!UICONTROL OR] puede resultar muy útil cuando desea crear rápidamente una audiencia amplia de visitantes del sitio cualificados.

**[!UICONTROL AND NOT]Ejemplo de caso de uso**

El [!UICONTROL AND NOT] es útil cuando es más fácil definir una audiencia por *exclusión* en lugar de *inclusión*. Por ejemplo, supongamos que tiene una venta y desea segmentar a los visitantes en clientes que solo ven artículos con precio completo. En lugar de crear una lista de señales para todos los artículos aptos completos o con precio de venta, puede ser más fácil calificar a los visitantes si tienen *no* ha visto un artículo con precio de venta. Esto es eficiente desde el punto de vista administrativo, ya que normalmente tiene menos artículos a precio de venta en comparación con los que se ofrecen a precio completo. Con un booleano [!UICONTROL NOT], visitantes *no debe* exhiba la señal de venta para calificar para el abono a precio completo de la audiencia. Por el contrario, [!UICONTROL AND NOT] es lo contrario de [!UICONTROL AND] caso de uso, que mostraba cómo se determina la pertenencia a la audiencia mediante la inclusión (es decir, el visitante cumple los requisitos en función de dos señales explícitamente establecidas).

>[!MORELIKETHIS]
>
>* [Uso de operadores de comparación en el generador de rasgos](../features/traits/trait-comparison-operators.md)
>* [Orden de las operaciones en expresiones de TraitBuilder](../features/traits/trait-operator-precedence.md)

