---
description: Obtenga información acerca de los componentes de un segmento y las expresiones utilizadas para definir los criterios de cualificación de audiencia. También encontrará información sobre cómo se transmiten los datos.
landing-page-description: Obtenga información acerca de los componentes de un segmento y las expresiones utilizadas para definir los criterios de cualificación de audiencia. También encontrará información sobre cómo se transmiten los datos.
short-description: Learn about the components of a segment and the expressions used to set audience qualification criteria. Also find information about how data is transmitted.
seo-title: Signals, Traits, and Segments
solution: Audience Manager
title: Señales, rasgos y segmentos
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: Reference
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 16%

---

# [!UICONTROL Signals], [!UICONTROL Traits]y [!UICONTROL Segments] {#signals-traits-and-segments}

Describe los componentes de un [!DNL Audience Manager] [!UICONTROL segment], las expresiones utilizadas para establecer los criterios de cualificación de audiencia y cómo se transmiten los datos en una llamada de evento.

## Composición y propósito

[!DNL Audience Manager] Los datos constan de [!UICONTROL signals], [!UICONTROL traits], [!UICONTROL segments]y reglas de cualificación relacionadas. Los elementos de datos y las reglas se combinan para crear [!UICONTROL segments]. [!UICONTROL Segments] organizar a los visitantes del sitio en grupos relacionados. En la tabla siguiente se definen los tres componentes principales de una [!DNL Audience Manager] [!UICONTROL segment].

| Elemento | Consiste en | Ejemplo |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] son las unidades de datos más pequeñas de [!DNL Audience Manager] y se expresan como [pares clave-valor](../reference/key-value-pairs-explained.md).<br><br><ul><li>La clave es una constante que define un conjunto de datos (por ejemplo, sexo, color, precio).</li><li>El valor es una variable relacionada con la constante (por ejemplo, hombre/mujer, verde, 100).</li></ul>Los operadores de comparación se unen al par clave-valor y establecen la relación entre ellos. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinaciones de una o más [!UICONTROL signals].<br><br> [!DNL Boolean] las expresiones y los operadores de comparación le permiten crear [!UICONTROL trait] reglas de clasificación. <br><br>Crear requisitos de cualificación precisos con combinaciones de [!UICONTROL traits] y [!UICONTROL trait] grupos. | Desde la [!UICONTROL signals], puede crear un `High End Camera Browser` regla expresada como: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Usuarios que comparten un conjunto de atributos comunes y cumplen los requisitos para [!UICONTROL traits]. [!DNL Boolean] las expresiones, junto con los requisitos de actualización y frecuencia, permiten crear [!UICONTROL segment] reglas de clasificación.<br><br> Crear requisitos de cualificación precisos con combinaciones de [!UICONTROL trait] y [!UICONTROL segment] reglas. | Desde la [!UICONTROL traits] y [!UICONTROL signals], puede crear un [!UICONTROL segment] regla expresada como:`(product=camera AND type=digital SLR) OR (price>1000)` |

Utilice el diagrama siguiente para tener una nota mental de la relación entre [!UICONTROL signals], [!UICONTROL traits]y [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Generar [!UICONTROL Traits] y [!UICONTROL Segment] Reglas con herramientas visuales y editores de código**

Administración de clientes [!UICONTROL traits] y [!UICONTROL segments] con herramientas visuales y editores de código en la variable [!DNL Audience Manager] interfaz de usuario. Las herramientas visuales permiten crear reglas utilizando funciones de búsqueda, opciones emergentes, menús desplegables y funciones de arrastrar y soltar. Los editores de código proporcionan a los usuarios avanzados una forma de desarrollar mediante programación criterios de segmentación de audiencia.

**Llamadas de evento: enviar datos a[!DNL Audience Manager]**

Una llamada de evento envía datos desde el sitio web a [!DNL Audience Manager]. La llamada contiene [!UICONTROL signal], [!UICONTROL trait]y [!UICONTROL segment] datos en un [!DNL HTTP] solicitud. El evento en sí es todo después de la `/event` parte de una [!DNL URL] cadena. Como se muestra en el ejemplo siguiente, este proceso requiere una sola llamada de evento para pasar varias variables a [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmentos: propósito, composición y reglas](../features/segments/segments-purpose.md)

