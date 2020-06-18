---
description: Describe los componentes de un segmento de Audience Manager, las expresiones utilizadas para definir los criterios de calificación de audiencia y cómo se transmiten los datos en una llamada de evento.
seo-description: Describe los componentes de un segmento de Audience Manager, las expresiones utilizadas para definir los criterios de calificación de audiencia y cómo se transmiten los datos en una llamada de evento.
seo-title: Señales, características y segmentos
solution: Audience Manager
title: Señales, características y segmentos
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 1%

---


# Señales, características y segmentos{#signals-traits-and-segments}

Describe los componentes de un [!DNL Audience Manager] segmento, las expresiones utilizadas para definir los criterios de cualificación de la audiencia y cómo se transmiten los datos en una llamada de evento.

<!-- 

c_signal_trait_segment.xml

 -->

**Composición y propósito**

[!DNL Audience Manager] los datos constan de señales, características, segmentos y reglas de cualificación relacionadas. Los elementos de datos y las reglas se combinan para crear segmentos. Los segmentos organizan los visitantes del sitio en grupos relacionados. La siguiente tabla define los tres componentes principales de un [!DNL Audience Manager] segmento.

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
   <td colname="col2"> <p>Las señales son las unidades de datos más pequeñas del <span class="keyword"> Audience Manager</span> y se expresan como pares <a href="../reference/key-value-pairs-explained.md"> de</a>clave-valor. </p> 
    <ul id="ul_728347E325284B9FA0B4E05DE8CF4570"> 
     <li id="li_89574A3B4A734726AD43405AE6D85FF5">La clave es una constante que define un conjunto de datos (por ejemplo, sexo, color y precio). </li> 
     <li id="li_D35601B33EE24EC5857F45D9577254D4">El valor es una variable relacionada con la constante (por ejemplo: hombre/mujer, verde, 100). </li> 
    </ul> <p>Los operadores de comparación unen el par clave-valor y establecen la relación entre ellos. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A6D8D30A37C94437A7BF38736C6F8556"> 
     <li id="li_74C87C34FA254783AC0DEBBC69B35AC4"><code> product=camera</code> </li> 
     <li id="li_C1727B9136024E56B60374597A7DCA00"><code> price&gt;1000</code> </li> 
     <li id="li_B2E7798768EE444AB978F3F27B0BC0B5"><code> type=digital SLR</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Rasgo</b> </td> 
   <td colname="col2"> <p>Combinaciones de una o más señales. </p> <p>Las expresiones booleanas y los operadores de comparación permiten crear reglas de cualificación de características. </p> <p>Cree requisitos de cualificación precisos con combinaciones de características y grupos de características. </p> </td> 
   <td colname="col3"> <p>A partir de las señales disponibles, se puede crear una regla de "Explorador de cámara de gama alta" expresada como: </p> <p><code> product=camera AND price&gt;1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Segmento</b> </td> 
   <td colname="col2"> <p>Usuarios que comparten un conjunto de atributos comunes y califican para características relacionadas. </p> <p>Las expresiones booleanas, junto con los requisitos de frecuencia y actualización, permiten crear reglas de cualificación de segmentos. </p> <p>Cree requisitos de cualificación precisos con combinaciones de características y reglas de segmentos. </p> </td> 
   <td colname="col3"> <p>A partir de las características y señales disponibles, puede crear una regla de segmento expresada como: </p> <p><code> (product=camera AND type=digital SLR) OR (price&gt;1000)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Utilice el diagrama siguiente para tener una nota mental de la relación entre señales, características y segmentos.

![](assets/signals-traits-segments.png)

**Generar características y reglas de segmentos con Visual Tools y los editores de código**

Los clientes administran características y segmentos con herramientas visuales y editores de código en la interfaz de [!DNL Audience Manager] usuario. Las herramientas visuales permiten crear reglas mediante funciones de búsqueda, opciones emergentes, menús desplegables y funciones de arrastrar y soltar. Los editores de código proporcionan a los usuarios avanzados una manera de desarrollar mediante programación criterios de segmentación de audiencias.

**Llamadas de Evento para enviar datos al Audience Manager**

Una llamada de evento envía datos del sitio web a [!DNL Audience Manager]. La llamada contiene datos de señales, características y segmentos en una [!DNL HTTP] solicitud. El evento mismo es todo después de la parte `/event` de una [!DNL URL] cadena. Como se muestra en el ejemplo siguiente, este proceso requiere solamente una llamada de evento para pasar múltiples variables a [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmentos: Propósito, composición y reglas](../features/segments/segments-purpose.md)

