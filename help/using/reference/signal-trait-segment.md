---
description: Obtenga información acerca de los componentes de un segmento y las expresiones utilizadas para definir los criterios de cualificación de audiencia. También encontrará información sobre cómo se transmiten los datos.
landing-page-description: Obtenga información acerca de los componentes de un segmento y las expresiones utilizadas para definir los criterios de cualificación de audiencia. También encontrará información sobre cómo se transmiten los datos.
short-description: Obtenga información acerca de los componentes de un segmento y las expresiones utilizadas para definir los criterios de cualificación de audiencia. También encontrará información sobre cómo se transmiten los datos.
seo-title: Signals, Traits, and Segments
solution: Audience Manager
title: Señales, rasgos y segmentos
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: Reference
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 21%

---

# [!UICONTROL Signals], [!UICONTROL Traits] y [!UICONTROL Segments] {#signals-traits-and-segments}

Describe los componentes de un [!DNL Audience Manager] [!UICONTROL segment], las expresiones utilizadas para establecer los criterios de cualificación de audiencia y cómo se transmiten los datos en una llamada de evento.

## Composición y propósito

Los datos de [!DNL Audience Manager] constan de [!UICONTROL signals], [!UICONTROL traits], [!UICONTROL segments] y reglas de calificación relacionadas. Los elementos de datos y las reglas se combinan para crear [!UICONTROL segments]. [!UICONTROL Segments] organizan a los visitantes del sitio en grupos relacionados. En la tabla siguiente se definen los tres componentes principales de un(a) [!DNL Audience Manager] [!UICONTROL segment].

| Elemento | Consta de | Ejemplo |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] son las unidades de datos más pequeñas de [!DNL Audience Manager] y se expresan como [pares clave-valor](../reference/key-value-pairs-explained.md).<br><br><ul><li>La clave es una constante que define un conjunto de datos (por ejemplo, sexo, color, precio).</li><li>El valor es una variable relacionada con la constante (por ejemplo, hombre/mujer, verde, 100).</li></ul>Los operadores de comparación se unen al par clave-valor y establecen la relación entre ellos. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinaciones de uno o más [!UICONTROL signals].<br><br> Las expresiones [!DNL Boolean] y los operadores de comparación le permiten crear [!UICONTROL trait] reglas de calificación. <br><br>Cree requisitos de calificación precisos con combinaciones de [!UICONTROL traits] y [!UICONTROL trait] grupos. | De los [!UICONTROL signals] disponibles, podría crear una regla de `High End Camera Browser` expresada como: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Usuarios que comparten un conjunto de atributos comunes y cumplen los requisitos de [!UICONTROL traits] relacionados. Las expresiones [!DNL Boolean], junto con los requisitos de actualización y frecuencia, le permiten crear [!UICONTROL segment] reglas de calificación.<br><br>: cree requisitos de calificación precisos con combinaciones de reglas de [!UICONTROL trait] y [!UICONTROL segment]. | De los [!UICONTROL traits] y [!UICONTROL signals] disponibles, puede crear una regla de [!UICONTROL segment] expresada como:`(product=camera AND type=digital SLR) OR (price>1000)` |

Utilice el diagrama siguiente para mantener una nota mental de la relación entre [!UICONTROL signals], [!UICONTROL traits] y [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Generar reglas [!UICONTROL Traits] y [!UICONTROL Segment] con herramientas visuales y editores de código**

Los clientes administran [!UICONTROL traits] y [!UICONTROL segments] con herramientas visuales y editores de código en la interfaz de usuario [!DNL Audience Manager]. Las herramientas visuales le permiten crear reglas utilizando funciones de búsqueda, opciones emergentes, menús desplegables y la funcionalidad de arrastrar y soltar. Los editores de código proporcionan a los usuarios avanzados una forma de desarrollar mediante programación criterios de segmentación de audiencia.

**Las llamadas de evento envían datos a[!DNL Audience Manager]**

Una llamada de evento envía datos del sitio web a [!DNL Audience Manager]. La llamada contiene datos de [!UICONTROL signal], [!UICONTROL trait] y [!UICONTROL segment] en una solicitud de [!DNL HTTP]. El evento en sí es todo después de la parte `/event` de una cadena [!DNL URL]. Como se muestra en el ejemplo siguiente, este proceso requiere una sola llamada de evento para pasar varias variables a [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmentos: propósito, composición y reglas](../features/segments/segments-purpose.md)
