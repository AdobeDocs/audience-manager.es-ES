---
description: Describe los componentes de un segmento de Audience Manager, las expresiones utilizadas para definir los criterios de cualificación de audiencias y cómo se transmiten los datos en una llamada de evento.
seo-description: Describe los componentes de un segmento de Audience Manager, las expresiones utilizadas para definir los criterios de cualificación de audiencias y cómo se transmiten los datos en una llamada de evento.
seo-title: Señales, rasgos y segmentos
solution: Audience Manager
title: Señales, rasgos y segmentos
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: reference
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 17%

---


# [!UICONTROL Signals],  [!UICONTROL Traits]y  [!UICONTROL Segments] {#signals-traits-and-segments}

Describe los componentes de [!DNL Audience Manager] [!UICONTROL segment], las expresiones utilizadas para establecer los criterios de calificación de audiencias y cómo se transmiten los datos en una llamada de evento.

## Composición y propósito

[!DNL Audience Manager] los datos constan de reglas de cualificación  [!UICONTROL signals],  [!UICONTROL traits],  [!UICONTROL segments] y relacionadas. Los elementos de datos y las reglas se combinan para crear [!UICONTROL segments]. [!UICONTROL Segments] organizar los visitantes del sitio en grupos relacionados. La siguiente tabla define los tres componentes principales en un [!DNL Audience Manager] [!UICONTROL segment].

| Elemento | Consiste en | Ejemplo |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] son las unidades de datos más pequeñas  [!DNL Audience Manager] y se expresan como pares [ de valor ](../reference/key-value-pairs-explained.md)clave.<br><br><ul><li>La clave es una constante que define un conjunto de datos (por ejemplo, sexo, color y precio).</li><li>El valor es una variable relacionada con la constante (por ejemplo: hombre/mujer, verde, 100).</li></ul>Los operadores de comparación unen el par clave-valor y establecen la relación entre ellos. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinaciones de uno o más [!UICONTROL signals].<br><br> [!DNL Boolean] Las expresiones y los operadores de comparación permiten crear reglas  [!UICONTROL trait] de cualificación. <br><br>Cree requisitos de cualificación precisos con combinaciones de  [!UICONTROL traits] y  [!UICONTROL trait] grupos. | A partir de la [!UICONTROL signals] disponible, puede crear una regla `High End Camera Browser` expresada como: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Usuarios que comparten un conjunto de atributos comunes y califican para [!UICONTROL traits] relacionados. [!DNL Boolean] Las expresiones, junto con los requisitos de frecuencia y actualización, permiten crear reglas  [!UICONTROL segment] de cualificación.<br><br> Cree requisitos de cualificación precisos con combinaciones de  [!UICONTROL trait] y  [!UICONTROL segment] reglas. | A partir de los [!UICONTROL traits] y [!UICONTROL signals] disponibles, puede crear una regla [!UICONTROL segment] expresada como:`(product=camera AND type=digital SLR) OR (price>1000)` |

Utilice el diagrama siguiente para tener una nota mental de la relación entre [!UICONTROL signals], [!UICONTROL traits] y [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Creación  [!UICONTROL Traits] y  [!UICONTROL Segment] reglas con Visual Tools y los editores de código**

Los clientes administran [!UICONTROL traits] y [!UICONTROL segments] con herramientas visuales y editores de código en la interfaz de usuario [!DNL Audience Manager]. Las herramientas visuales permiten crear reglas mediante funciones de búsqueda, opciones emergentes, menús desplegables y funciones de arrastrar y soltar. Los editores de código proporcionan a los usuarios avanzados una manera de desarrollar mediante programación criterios de segmentación de audiencias.

**Llamadas de evento para enviar datos a[!DNL Audience Manager]**

Una llamada de evento envía datos del sitio Web a [!DNL Audience Manager]. La llamada contiene [!UICONTROL signal], [!UICONTROL trait] y [!UICONTROL segment] datos en una solicitud [!DNL HTTP]. El propio evento es todo después de la parte `/event` de una cadena [!DNL URL]. Como se muestra en el ejemplo siguiente, este proceso requiere solamente una llamada de evento única para pasar múltiples variables a [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmentos: propósito, composición y reglas](../features/segments/segments-purpose.md)

