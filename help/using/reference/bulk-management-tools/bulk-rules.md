---
description: Las hojas de cálculo de creación y actualización aceptan un encabezado traitRule que permite aplicar varias reglas en una sola operación. Siga estas instrucciones para realizar solicitudes de reglas masivas.
seo-description: Las hojas de cálculo de creación y actualización aceptan un encabezado traitRule que permite aplicar varias reglas en una sola operación. Siga estas instrucciones para realizar solicitudes de reglas masivas.
seo-title: Crear o actualizar normas de rasgos y normas de segmentos
solution: Audience Manager
title: Crear o actualizar normas de rasgos y normas de segmentos
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 10%

---

# Crear o actualizar normas de rasgos y normas de segmentos{#create-or-update-trait-rules-and-segment-rules}

Las hojas de cálculo de creación y actualización aceptan un encabezado traitRule que permite aplicar varias reglas en una sola operación. Siga estas instrucciones para realizar solicitudes de reglas masivas.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[Los ](../../features/administration/administration-overview.md) permisos de grupo RBAC asignados en la  [!DNL Audience Manager] interfaz de usuario se respetan en  [!UICONTROL Bulk Management Tools].

## Trabajo con reglas de rasgos {#trait-rules}

En la hoja de cálculo, la columna de regla de rasgos devuelve y acepta reglas compuestas por expresiones booleanas, operadores de comparación y expresiones regulares. Puede crear reglas con el generador de rasgos o segmentos en [!DNL Audience Manager] y copiarlas en la hoja de cálculo. O bien, si está familiarizado con la sintaxis de la regla, puede escribir expresiones directamente en las hojas de cálculo.

## Ejemplo del Generador de reglas {#rule-builder-example}

Veamos un ejemplo que muestra cómo usar [!UICONTROL Segment Builder] para crear una regla que puede usar en la hoja de cálculo masiva. Sin embargo, no se trata de un conjunto de instrucciones paso a paso para esas herramientas. En su lugar, vamos a empezar con una regla simple que ya ha sido creada. Para obtener instrucciones sobre cómo utilizar los generadores de reglas, consulte [Generador de segmentos](../../features/segments/segment-builder.md) y [Generador de rasgos](../../features/traits/about-trait-builder.md).

Con el generador de reglas visual, hemos creado una regla de segmento con 3 características y un operador booleano [!UICONTROL AND].

![](assets/visualrule.png)

Haga clic en **[!UICONTROL Code View]** para obtener la versión de texto de esta regla.

>[!TIP]
>
>Haga clic en **[!UICONTROL Validate Expression]** para comprobar la lógica de regla. Esto ayudará a evitar que cargue una regla no válida.

![](assets/coderule.png)

Pegue la regla en la hoja de cálculo [!UICONTROL Bulk Management Tools] y confirme los cambios para actualizar las reglas de segmentos de forma masiva.

![](assets/segmentrule.png)

## Creación de sus propias reglas {#create-rules}

Puede escribir sus propias reglas fuera de [!UICONTROL Rule Builder]. Antes de comenzar, asegúrese de leer la documentación que cubre aspectos como operadores, expresiones y variables requeridas. Le recomendamos que revise lo siguiente:

* [Uso De Operadores De Comparación En El Generador De Características](../../features/traits/trait-comparison-operators.md)
* [Orden de las operaciones](../../features/traits/trait-operator-precedence.md)
* [Requisitos de prefijo para variables clave](../../features/traits/trait-variable-prefixes.md)
* [Expresiones de muestra con operadores booleanos y de comparación](../../features/traits/trait-expression-samples.md)
