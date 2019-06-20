---
description: Las hojas de cálculo de creación y actualización aceptan un encabezado traitrule que permite aplicar varias reglas en una sola operación. Siga estas instrucciones para realizar solicitudes de reglas masivas.
seo-description: Las hojas de cálculo de creación y actualización aceptan un encabezado traitrule que permite aplicar varias reglas en una sola operación. Siga estas instrucciones para realizar solicitudes de reglas masivas.
seo-title: Crear o actualizar reglas de características y reglas de segmentos
solution: Audience Manager
title: Crear o actualizar reglas de características y reglas de segmentos
uuid: bdd 5 f 8 f 1-bb 83-4844-b 681-654 e 45 ace 3 e 1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create or Update Trait Rules and Segment Rules{#create-or-update-trait-rules-and-segment-rules}

Las hojas de cálculo de creación y actualización aceptan un encabezado traitrule que permite aplicar varias reglas en una sola operación. Siga estas instrucciones para realizar solicitudes de reglas masivas.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]*No* se admite [!DNL Audience Manager]en. Esta herramienta se proporciona para su comodidad y solo como cortesía. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Los permisos de grupo RBAC](../../features/administration/administration-overview.md) asignados en [!DNL Audience Manager] la interfaz de usuario se aceptan en [!UICONTROL Bulk Management Tools]la.

## Working with trait rules {#trait-rules}

En la hoja de cálculo, la columna de regla de características devuelve y acepta reglas que consisten de expresiones booleanas, operadores de comparación y expresiones regulares. You can create rules with trait or segment builder in [!DNL Audience Manager] and copy them to your worksheet. O bien, si está familiarizado con la sintaxis de la regla, puede escribir expresiones directamente en las hojas de cálculo.

## Rule builder example {#rule-builder-example}

Let&#39;s take a look at an example that demonstrates how to use [!UICONTROL Segment Builder] to create a rule you can to the bulk worksheet. Sin embargo, este no es un conjunto de instrucciones paso a paso para estas herramientas. En su lugar, vamos a comenzar con una regla simple que ya se ha creado. For instructions about how to use the rule builders see [Segment Builder](../../features/segments/segment-builder.md) and [Trait Builder](../../features/traits/about-trait-builder.md).

With the visual rule builder, we&#39;ve created a segment rule with 3 traits and a Boolean [!UICONTROL AND] operator.

![](assets/visualrule.png)

Click **[!UICONTROL Code View]** to get the text version of this rule.

>[!TIP]
>
>Click **[!UICONTROL Validate Expression]** to check your rule logic. Esto ayudará a evitar que se cargue una regla no válida.

![](assets/coderule.png)

Paste the rule into the [!UICONTROL Bulk Management Tools] worksheet and commit your changes to update segment rules in bulk.

![](assets/segmentrule.png)

## Creating your own rules {#create-rules}

You can write your own rules outside of [!UICONTROL Rule Builder]. Antes de comenzar, asegúrese de leer la documentación que cubre los operadores, la expresión y las variables requeridas. Le recomendamos que revise lo siguiente:

* [Uso de operadores de comparación en el Generador de rasgos](../../features/traits/trait-comparison-operators.md)
* [Orden de las operaciones](../../features/traits/trait-operator-precedence.md)
* [Requisitos de prefijo para variables clave](../../features/traits/trait-variable-prefixes.md)
* [Expresiones de muestra con operadores booleanos y de comparación](../../features/traits/trait-expression-samples.md)

