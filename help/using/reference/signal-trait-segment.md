---
description: Describe los componentes de un segmento de Audience Manager, las expresiones utilizadas para definir los criterios de cualificación de audiencias y cómo se transmiten los datos en una llamada de evento.
landing-page-description: Describe los componentes de un segmento, las expresiones utilizadas para definir los criterios de cualificación de la audiencia y cómo se transmiten los datos.
seo-title: Señales, rasgos y segmentos
solution: Audience Manager
title: Señales, rasgos y segmentos
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: Reference
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 15%

---

# [!UICONTROL Signals],  [!UICONTROL Traits]y  [!UICONTROL Segments] {#signals-traits-and-segments}

Describe los componentes de un [!DNL Audience Manager] [!UICONTROL segment], las expresiones utilizadas para establecer los criterios de cualificación de audiencias y cómo se transmiten los datos en una llamada de evento.

## Composición y propósito

[!DNL Audience Manager] los datos constan de  [!UICONTROL signals],  [!UICONTROL traits],  [!UICONTROL segments] y reglas de clasificación relacionadas. Los elementos de datos y las reglas se combinan para crear [!UICONTROL segments]. [!UICONTROL Segments] organizar a los visitantes del sitio en grupos relacionados. La siguiente tabla define los tres componentes principales en un [!DNL Audience Manager] [!UICONTROL segment].

| Elemento | Consiste en | Ejemplo |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] son las unidades de datos más pequeñas de  [!DNL Audience Manager] y se expresan como pares  [clave-valor](../reference/key-value-pairs-explained.md).<br><br><ul><li>La clave es una constante que define un conjunto de datos (por ejemplo, sexo, color, precio).</li><li>El valor es una variable relacionada con la constante (por ejemplo, hombre/mujer, verde, 100).</li></ul>Los operadores de comparación se unen al par clave-valor y establecen la relación entre ellos. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinaciones de uno o más [!UICONTROL signals].<br><br> [!DNL Boolean] los operadores de expresiones y comparación permiten crear reglas de  [!UICONTROL trait] cualificación. <br><br>Cree requisitos de cualificación precisos con combinaciones de  [!UICONTROL traits] y  [!UICONTROL trait] grupos. | A partir del [!UICONTROL signals] disponible, puede crear una regla `High End Camera Browser` expresada como: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Usuarios que comparten un conjunto de atributos comunes y califican para [!UICONTROL traits] relacionados. [!DNL Boolean] , junto con los requisitos de actualización y frecuencia, permiten crear reglas de  [!UICONTROL segment] cualificación.<br><br> Cree requisitos de cualificación precisos con combinaciones de  [!UICONTROL trait] y  [!UICONTROL segment] reglas. | A partir de los [!UICONTROL traits] y [!UICONTROL signals] disponibles, puede crear una regla [!UICONTROL segment] expresada como:`(product=camera AND type=digital SLR) OR (price>1000)` |

Utilice el diagrama siguiente para tener una nota mental de la relación entre [!UICONTROL signals], [!UICONTROL traits] y [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Generar  [!UICONTROL Traits] y  [!UICONTROL Segment] reglas con herramientas visuales y editores de código**

Los clientes administran [!UICONTROL traits] y [!UICONTROL segments] con herramientas visuales y editores de código en la interfaz de usuario [!DNL Audience Manager]. Las herramientas visuales permiten crear reglas utilizando funciones de búsqueda, opciones emergentes, menús desplegables y funciones de arrastrar y soltar. Los editores de código proporcionan a los usuarios avanzados una forma de desarrollar mediante programación criterios de segmentación de audiencia.

**Llamadas de evento: enviar datos a[!DNL Audience Manager]**

Una llamada de evento envía datos del sitio web a [!DNL Audience Manager]. La llamada contiene datos [!UICONTROL signal], [!UICONTROL trait] y [!UICONTROL segment] en una solicitud [!DNL HTTP]. El propio evento es todo lo que hay después de la parte `/event` de una cadena [!DNL URL]. Como se muestra en el ejemplo siguiente, este proceso requiere una sola llamada de evento para pasar varias variables a [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmentos: propósito, composición y reglas](../features/segments/segments-purpose.md)

