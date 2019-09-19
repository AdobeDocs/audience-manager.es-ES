---
description: Las hojas de cálculo para crear y actualizar aceptan un encabezado traitRule que permite aplicar varias reglas en una sola operación. Siga estas instrucciones para realizar solicitudes de reglas masivas.
seo-description: Las hojas de cálculo para crear y actualizar aceptan un encabezado traitRule que permite aplicar varias reglas en una sola operación. Siga estas instrucciones para realizar solicitudes de reglas masivas.
seo-title: Crear o actualizar reglas de características y reglas de segmentos
solution: Audience Manager
title: Crear o actualizar reglas de características y reglas de segmentos
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Crear o actualizar reglas de características y reglas de segmentos{#create-or-update-trait-rules-and-segment-rules}

Las hojas de cálculo para crear y actualizar aceptan un encabezado traitRule que permite aplicar varias reglas en una sola operación. Siga estas instrucciones para realizar solicitudes de reglas masivas.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>Los [!UICONTROL Bulk Management Tools] no *son* compatibles con [!DNL Audience Manager]. Esta herramienta se proporciona por conveniencia y sólo por cortesía. Para los cambios masivos, se recomienda trabajar con las API [de](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager en su lugar. [Los permisos](../../features/administration/administration-overview.md) de grupo RBAC asignados en la [!DNL Audience Manager] interfaz de usuario se respetan en la [!UICONTROL Bulk Management Tools].

## Uso de reglas de características {#trait-rules}

En la hoja de cálculo, la columna de regla de características devuelve y acepta reglas que constan de expresiones booleanas, operadores de comparación y expresiones regulares. Puede crear reglas con el generador de rasgos o segmentos [!DNL Audience Manager] y copiarlas en la hoja de cálculo. O bien, si está familiarizado con la sintaxis de la regla, puede escribir expresiones directamente en las hojas de cálculo.

## Ejemplo del generador de reglas {#rule-builder-example}

Veamos un ejemplo que muestra cómo se utiliza [!UICONTROL Segment Builder] para crear una regla que se puede usar en la hoja de cálculo masiva. Sin embargo, no es un conjunto de instrucciones paso a paso para esas herramientas. En cambio, vamos a empezar con una regla simple que ya ha sido creada. Para obtener instrucciones sobre cómo utilizar los generadores de reglas, consulte Generador [de segmentos](../../features/segments/segment-builder.md) y Generador de [características](../../features/traits/about-trait-builder.md).

Con el creador de reglas visuales, hemos creado una regla de segmentos con 3 características y un [!UICONTROL AND] operador booleano.

![](assets/visualrule.png)

Haga clic **[!UICONTROL Code View]** para obtener la versión de texto de esta regla.

>[!TIP]
>
>Haga clic en **[!UICONTROL Validate Expression]** para comprobar la lógica de la regla. Esto ayudará a evitar que cargue una regla no válida.

![](assets/coderule.png)

Pegue la regla en la hoja de cálculo y confirme los cambios para actualizar las reglas de segmentos de forma masiva. [!UICONTROL Bulk Management Tools]

![](assets/segmentrule.png)

## Creación de sus propias reglas {#create-rules}

Puedes escribir tus propias reglas fuera de [!UICONTROL Rule Builder]. Antes de empezar, asegúrese de leer la documentación que cubre aspectos como operadores, expresiones y variables requeridas. Le recomendamos que revise lo siguiente:

* [Uso De Operadores De Comparación En El Generador De Características](../../features/traits/trait-comparison-operators.md)
* [Orden de las operaciones](../../features/traits/trait-operator-precedence.md)
* [Requisitos de prefijo para variables clave](../../features/traits/trait-variable-prefixes.md)
* [Expresiones de muestra con operadores booleanos y de comparación](../../features/traits/trait-expression-samples.md)

