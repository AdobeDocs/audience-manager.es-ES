---
description: Las hojas de cálculo para crear y actualizar aceptan un encabezado traitRule que permite aplicar varias reglas en una sola operación. Siga estas instrucciones para realizar solicitudes de regla masivas.
seo-description: The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.
seo-title: Create or Update Trait Rules and Segment Rules
solution: Audience Manager
title: Crear o actualizar reglas de rasgos y reglas de segmentos
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 1%

---

# Crear o actualizar reglas de rasgos y reglas de segmentos{#create-or-update-trait-rules-and-segment-rules}

Las hojas de cálculo para crear y actualizar aceptan un encabezado traitRule que permite aplicar varias reglas en una sola operación. Siga estas instrucciones para realizar solicitudes de regla masivas.

>[!IMPORTANT]
>
>Los Herramientas de administración masiva no son una oferta Adobe Systems que se admita oficialmente. La solución de problemas y el soporte a través del Servicio de atención al cliente se manejarán caso por caso.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[Los permisos](../../features/administration/administration-overview.md) RBAC grupo asignados en el [!DNL Audience Manager] IU se respetan en el [!UICONTROL Bulk Management Tools].

## Trabajo con reglas de rasgos {#trait-rules}

En la hoja de cálculo, la columna de regla de características devuelve y acepta reglas que constan de expresiones booleanas, operadores de comparación y expresiones regulares. Puede crear reglas con generador de rasgos o segmento [!DNL Audience Manager] y copiarlas en la hoja de cálculo. O bien, si está familiarizado con regla sintaxis, puede escribir expresiones directamente en las hojas de cálculo.

## Ejemplo de generador de reglas {#rule-builder-example}

Veamos un ejemplo que muestra cómo crear [!UICONTROL Segment Builder] un regla puede en la hoja de cálculo masiva. Sin embargo, este no es un conjunto de instrucciones paso a paso para esas herramientas. En su lugar, vamos a inicio con un regla simple que ya se ha creado. Para obtener instrucciones sobre cómo utilizar los generadores de regla, consulte [Generador](../../features/segments/segment-builder.md) de segmentos y [Generador](../../features/traits/about-trait-builder.md) de rasgos.

Con el generador de regla visual, hemos creado un regla segmento con 3 características y un operador booleano [!UICONTROL AND] .

![](assets/visualrule.png)

Haga clic **[!UICONTROL Code View]** para obtener la versión de texto de este regla.

>[!TIP]
>
>Haga clic **[!UICONTROL Validate Expression]** para comprobar la lógica regla. Esto evitará que cargue un no válido regla.

![](assets/coderule.png)

Pegar la regla a la hoja de [!UICONTROL Bulk Management Tools] cálculo y confirme los cambios para actualizar las reglas de segmento de forma masiva.

![](assets/segmentrule.png)

## Creación de sus propias reglas {#create-rules}

Puede escribir sus propias reglas fuera de [!UICONTROL Rule Builder]. Antes de inicio, asegúrese de leer la documentación que cubre aspectos gustar operadores, expresión y variables requeridas. Le recomendamos que revise lo siguiente:

* [Trabajar con operadores de comparación en el generador de rasgos](../../features/traits/trait-comparison-operators.md)
* [Orden de las operaciones](../../features/traits/trait-operator-precedence.md)
* [Requisitos de prefijo para variables clave](../../features/traits/trait-variable-prefixes.md)
* [Expresiones de muestra con operadores booleanos y de comparación](../../features/traits/trait-expression-samples.md)
