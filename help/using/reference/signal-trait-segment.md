---
description: Describe los componentes de un segmento de Audience Manager, las expresiones utilizadas para definir criterios de cualificación de audiencia y cómo se transmiten los datos en una llamada de evento.
seo-description: Describe los componentes de un segmento de Audience Manager, las expresiones utilizadas para definir criterios de cualificación de audiencia y cómo se transmiten los datos en una llamada de evento.
seo-title: Señales, características y segmentos
solution: Audience Manager
title: Señales, características y segmentos
uuid: 485 fcc 5 c-b 289-463 b-a 610-0 d 727 df 90 f 3 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Signals, Traits, and Segments{#signals-traits-and-segments}

Describe los componentes de un segmento de Audience Manager, las expresiones utilizadas para definir criterios de cualificación de audiencia y cómo se transmiten los datos en una llamada de evento.

<!-- 

c_signal_trait_segment.xml

 -->

**Composición y propósito**

[!DNL Audience Manager] consiste en señales, características, segmentos y reglas de cualificación relacionadas. Los elementos de datos y las reglas se combinan para crear segmentos. Los segmentos organizan a los visitantes del sitio en grupos relacionados. The following table defines the three principal components in an [!DNL Audience Manager] segment.

<table id="table_E8373A01C3414C42B4983A59BF0F0669"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Consiste en </th> 
   <th colname="col3" class="entry"> Ejemplo </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Señal</b> </td> 
   <td colname="col2"> <p>Signals are the smallest data units in <span class="keyword"> Audience Manager</span> and are expressed as <a href="../reference/key-value-pairs-explained.md"> key-value pairs</a>. </p> 
    <ul id="ul_728347E325284B9FA0B4E05DE8CF4570"> 
     <li id="li_89574A3B4A734726AD43405AE6D85FF5">La clave es una constante que define un conjunto de datos (por ejemplo, sexo, color, precio). </li> 
     <li id="li_D35601B33EE24EC5857F45D9577254D4">El valor es una variable relacionada con la constante (por ejemplo, hombre/mujer, verde, 100). </li> 
    </ul> <p>Los operadores de comparación se unen al par clave-valor y establecen la relación entre ellos. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A6D8D30A37C94437A7BF38736C6F8556"> 
     <li id="li_74C87C34FA254783AC0DEBBC69B35AC4"><code> product = camera</code> </li> 
     <li id="li_C1727B9136024E56B60374597A7DCA00"><code> precio &gt; 1000</code> </li> 
     <li id="li_B2E7798768EE444AB978F3F27B0BC0B5"><code> type = digital SLR</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Rasgo</b> </td> 
   <td colname="col2"> <p>Combinaciones de una o varias señales. </p> <p>Las expresiones booleanas y los operadores de comparación permiten crear reglas de cualificación de rasgos. </p> <p>Cree requisitos de cualificación precisos con combinaciones de características y grupos de características. </p> </td> 
   <td colname="col3"> <p>A partir de las señales disponibles, puede crear una regla "Navegador de cámara de extremo alto" expresada como: </p> <p><code> product = camera AND price &gt; 1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Segmento</b> </td> 
   <td colname="col2"> <p>Usuarios que comparten un conjunto de atributos comunes y cumplen los requisitos de características relacionadas. </p> <p>Las expresiones booleanas, junto con los requisitos de actualización/frecuencia, permiten crear reglas de cualificación de segmentos. </p> <p>Cree requisitos de cualificación precisos con combinaciones de reglas de características y segmentos. </p> </td> 
   <td colname="col3"> <p>A partir de las características y señales disponibles, puede crear una regla de segmento expresada como: </p> <p><code> (product = camera AND type = digital SLR) OR (price &gt; 1000)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Utilice el diagrama siguiente para mantener una nota mental de la relación entre señales, características y segmentos.

![](assets/signals-traits-segments.png)

**Generar características y reglas de segmentos con herramientas visuales y editores de código**

Clients manage traits and segments with visual tools and code editors in the [!DNL Audience Manager] user interface. Las herramientas visuales permiten crear reglas mediante funciones de búsqueda, opciones emergentes, menús desplegables y funcionalidad de arrastrar y soltar. Los editores de código proporcionan a los usuarios avanzados una manera de desarrollar mediante programación criterios de segmentación de audiencia.

**Llamadas de evento Enviar datos a Audience Manager**

An event call sends data from your website to [!DNL Audience Manager]. La llamada contiene datos de señales, características y segmentos en una solicitud HTTP. The event itself is everything after the `/event` part of a URL string. As shown in the example below, this process requires only a single event call to pass in multiple variables to [!DNL Audience Manager].

```
https://<domain>/event?product=camera&price>100
```

>[!MORE_ LIKE_ THIS]
>
>* [Segmentos: Finalidad, composición y reglas](../features/segments/segments-purpose.md)

