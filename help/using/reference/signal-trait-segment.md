---
description: Describe los componentes de un segmento de Audience Manager, las expresiones utilizadas para definir los criterios de calificación de audiencia y cómo se transmiten los datos en una llamada de evento.
seo-description: Describe los componentes de un segmento de Audience Manager, las expresiones utilizadas para definir los criterios de calificación de audiencia y cómo se transmiten los datos en una llamada de evento.
seo-title: Señales, rasgos y segmentos
solution: Audience Manager
title: Señales, rasgos y segmentos
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 4%

---


# [!UICONTROL Signals], [!UICONTROL Traits]y [!UICONTROL Segments] {#signals-traits-and-segments}

Describe los componentes de una llamada [!DNL Audience Manager][!UICONTROL segment], las expresiones utilizadas para definir los criterios de cualificación de la audiencia y cómo se transmiten los datos en una llamada de evento.

## Composición y propósito

[!DNL Audience Manager] los datos constan de reglas de cualificación [!UICONTROL signals], [!UICONTROL traits], [!UICONTROL segments]y relacionadas. Los elementos de datos y las reglas se combinan para crear [!UICONTROL segments]. [!UICONTROL Segments] organizar los visitantes del sitio en grupos relacionados. La siguiente tabla define los tres componentes principales de un [!DNL Audience Manager][!UICONTROL segment].

| Elemento | Consiste en | Ejemplo |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] son las unidades de datos más pequeñas de [!DNL Audience Manager] y se expresan como pares [](../reference/key-value-pairs-explained.md)clave-valor.<br><br><ul><li>La clave es una constante que define un conjunto de datos (por ejemplo, sexo, color y precio).</li><li>El valor es una variable relacionada con la constante (por ejemplo: hombre/mujer, verde, 100).</li></ul>Los operadores de comparación unen el par clave-valor y establecen la relación entre ellos. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinaciones de uno o más [!UICONTROL signals].<br><br> [!DNL Boolean] Las expresiones y los operadores de comparación permiten crear reglas [!UICONTROL trait] de clasificación. <br><br>Cree requisitos de cualificación precisos con combinaciones de [!UICONTROL traits] y [!UICONTROL trait] grupos. | En la opción disponible [!UICONTROL signals], puede crear una `High End Camera Browser` regla expresada como: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Usuarios que comparten un conjunto de atributos comunes y cumplen los requisitos para [!UICONTROL traits]. [!DNL Boolean] Las expresiones, junto con los requisitos de frecuencia y actualización, permiten crear reglas [!UICONTROL segment] de cualificación.<br><br> Cree requisitos de cualificación precisos con combinaciones de [!UICONTROL trait] y [!UICONTROL segment] reglas. | A partir de los valores disponibles [!UICONTROL traits] y [!UICONTROL signals], puede crear una [!UICONTROL segment] regla expresada como:`(product=camera AND type=digital SLR) OR (price>1000)` |

Utilice el diagrama siguiente para tener una nota mental de la relación entre [!UICONTROL signals], [!UICONTROL traits]y [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Generar[!UICONTROL Traits]y[!UICONTROL Segment]crear reglas con Visual Tools y los editores de código**

Los clientes administran [!UICONTROL traits] y [!UICONTROL segments] con herramientas visuales y editores de código en la interfaz de [!DNL Audience Manager] usuario. Las herramientas visuales permiten crear reglas mediante funciones de búsqueda, opciones emergentes, menús desplegables y funciones de arrastrar y soltar. Los editores de código proporcionan a los usuarios avanzados una manera de desarrollar mediante programación criterios de segmentación de audiencias.

**Llamadas de Evento para enviar datos a[!DNL Audience Manager]**

Una llamada de evento envía datos del sitio web a [!DNL Audience Manager]. La llamada contiene [!UICONTROL signal], [!UICONTROL trait]y [!UICONTROL segment] datos en una [!DNL HTTP] solicitud. El evento mismo es todo después de la parte `/event` de una [!DNL URL] cadena. Como se muestra en el ejemplo siguiente, este proceso requiere solamente una llamada de evento para pasar múltiples variables a [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmentos: propósito, composición y reglas](../features/segments/segments-purpose.md)

