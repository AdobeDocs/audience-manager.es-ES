---
description: En el Generador de rasgos, el Generador de expresiones permite crear y probar reglas que establecen requisitos de cualificación de audiencia. Las reglas consisten en pares de clave-valor como "color = = blue" o "price > 100". Los operadores de comparación establecen la relación entre claves y valores. Las expresiones booleanas determinan la relación entre los grupos de reglas.
seo-description: En el Generador de rasgos, el Generador de expresiones permite crear y probar reglas que establecen requisitos de cualificación de audiencia. Las reglas consisten en pares de clave-valor como "color = = blue" o "price > 100". Los operadores de comparación establecen la relación entre claves y valores. Las expresiones booleanas determinan la relación entre los grupos de reglas.
seo-title: Administración de reglas de características
solution: Audience Manager
title: Administración de reglas de características
uuid: 827 d 4567-2 b 6 f -411 e-bd 5 c -9735 c 916291 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Managing Trait Rules {#managing-trait-rules}

In [!UICONTROL Trait Builder], the [!UICONTROL Expression Builder] lets you create and test rules that establish audience qualification requirements. Rules consist of key-value pairs such as `color == blue` or `price > 100`. Los operadores de comparación establecen la relación entre claves y valores. [!DNL Boolean] expresiones determinan la relación entre los grupos de reglas.

<!-- c_tb_rules.xml -->

## Características de reglas de señal principales descritas

![](assets/manage-trait-rules.png)

1. The **[!UICONTROL Expression Builder]** or **[!UICONTROL Code View]** tabs provide an overview of the rules in your trait. The **[!UICONTROL Expression Builder]** tab lets you create rules with fields and drop-down menus. The **[!UICONTROL Code View]** lets you create rules by manually writing those expressions as code. The illustration above shows a simple trait composed of a signal that evaluates data for a qualifying condition where a product key equals a specific value, in this case `color == "blue"`.

1. Los campos y controles de esta sección permiten crear señales a partir de pares clave-valor y establecer la relación entre ellos con un operador de comparación. Se requiere una clave, operador y valor.
1. The [!UICONTROL Data Explorer Options] allow you to backfill trait realizations for your signals.
   >[!NOTE]
   >
   >This option is only available for [!UICONTROL Data Explorer] customers. Póngase en contacto con su consultor de Adobe para obtener más detalles.
1. This section shows you an estimation of trait realizations for the past 7 days, for the signals defined in the [!UICONTROL Expression Builder], for backfilled and non-backfilled traits.
   >[!NOTE]
   >
   >This option is only available for [!UICONTROL Data Explorer] customers. Póngase en contacto con su consultor de Adobe para obtener más detalles.
1. The test fields let you validate combinations of signal rules or the [!DNL URL]s that you want to use when sending data to Audience Manager.

## Create a Trait Rule {#create-trait-rule}

Las reglas (o expresiones) constan de pares de clave-valor individuales. Los operadores de comparación establecen la relación entre pares clave-valor. To create a rule,provide a key, a value, select an operator, and click **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Complete the required fields in the **[!UICONTROL Basic Information]** section *before* creating trait rules.

1. Expand the **[!UICONTROL Trait Expression]** section and enter a key and value name. This creates a *`signal`*.
   >[!NOTE]
   >
   >Include the `c_` prefix (or any other naming convention) for key variable if your event calls send data to [!DNL Audience Manager] using that syntax.
1. Select a [comparison operator](../../features/traits/trait-comparison-operators.md) from the **[!UICONTROL Operator]** dropdown. El operador de comparación evalúa la relación entre los elementos en una señal.
   >[!NOTE]
   >
   >The [!DNL Boolean] [!UICONTROL OR] operator establishes the relationship between multiple signals *within* a group and cannot be changed.
1. Haga clic en **[!UICONTROL Add Rule]**. La regla guardada aparece en el espacio de trabajo de características encima de los campos de entrada de datos.

### Ejemplo {#example-trait-rule}

En el ejemplo siguiente, un usuario ha creado una nueva regla de características basada en la ID del producto. To build this rule, the user provided the key `productkey` linked with an equals operator ( `==`) to the value `2093`.
![](assets/tb_sample_rule1.png)

Clicking **[!UICONTROL Add Rule]** saves and moves the trait into the [!UICONTROL Expression Builder] workspace.

![](assets/tb_sample_rule2.png)

>[!MORE_ LIKE_ THIS]
>
>* [Crear un nuevo grupo de reglas](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Mover reglas entre grupos](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Eliminar una regla de características](../../features/traits/manage-trait-rules.md#delete-trait)


## Create a New Rule Group {#create-rule-group}

Este procedimiento describe cómo crear un nuevo grupo de reglas.

<!-- t_tb_new_rule_group.xml -->

La característica debe contener al menos dos reglas para poder crear un nuevo grupo de reglas.

1. Mueva el cursor sobre la regla que desee mover para resaltarla.
1. Pase el ratón sobre el borde de la regla resaltada.
Esto separa automáticamente la regla de su grupo actual y la mueve a un nuevo grupo.
   >[!NOTE]
   >
   >Vuelva a arrastrar una regla a su grupo original si lo mueve de forma unintencionada.
1. Select a [!DNL Boolean] operator ( [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) from the drop-down menu to set the relationship between the rule groups.

>[!MORE_ LIKE_ THIS]
>
>* [Crear una regla de características](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Mover reglas entre grupos](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Eliminar una regla de características](../../features/traits/manage-trait-rules.md#delete-trait)


## Move Rules Between Groups {#move-rules-between-groups}

Para mover una regla, haga clic y arrástrela a otro grupo.

>[!MORE_ LIKE_ THIS]
>
>* [Crear una regla de características](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Crear un nuevo grupo de reglas](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Eliminar una regla de características](../../features/traits/manage-trait-rules.md#delete-trait)


## Edit a Trait {#edit-trait}

Este procedimiento describe cómo editar un rasgo.

<!-- t_tb_edit.xml -->

1. In the [!UICONTROL Traits] dashboard, hover over the **[!UICONTROL Actions]** column for the trait you want to edit. Esto abre los iconos de administración de rasgos.
1. Haga clic en el lápiz para editar la característica.

   ![](assets/tb_edit_trait.png)

## Delete a Trait Rule {#delete-trait}

Este procedimiento describe cómo eliminar una regla de características.

<!-- t_tb_delete_rule.xml -->

1. In the [!UICONTROL Traits] dashboard, hover over the [!UICONTROL Actions] columns for the trait you want to edit and click the pencil icon. Esto abre los iconos de administración de rasgos.
1. Expand the [!UICONTROL Trait Expression] section.
1. Pase el ratón sobre la regla que desee eliminar y haga clic en el icono X. La regla se elimina inmediatamente.