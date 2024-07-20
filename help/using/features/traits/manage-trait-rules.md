---
description: En el Generador de rasgos, el Generador de expresiones le permite crear y probar reglas que establecen requisitos de cualificación de audiencias. Las reglas constan de pares de clave-valor como "color == azul" o "price &gt; 100". Los operadores de comparación establecen la relación entre claves y valores. Las expresiones booleanas determinan la relación entre los grupos de reglas.
seo-description: In Trait Builder, the Expression Builder lets you create and test rules that establish audience qualification requirements. Rules consist of key-value pairs such as "color == blue" or "price &gt; 100". Comparison operators establish the relationship between keys and values. Boolean expressions determine the relationship between rule groups.
seo-title: Managing Trait Rules
solution: Audience Manager
title: Administración de reglas de rasgos
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: Traits
exl-id: 4561b19a-bbb5-41ec-ac79-ab3e2ab75548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 0%

---

# Administración de reglas de rasgos {#managing-trait-rules}

En [!UICONTROL Trait Builder], [!UICONTROL Expression Builder] le permite crear y probar reglas que establecen requisitos de cualificación de audiencia. Las reglas constan de pares de clave-valor como `color == blue` o `price > 100`. Los operadores de comparación establecen la relación entre claves y valores. Las expresiones [!DNL Boolean] determinan la relación entre los grupos de reglas.

<!-- c_tb_rules.xml -->

## Características de las reglas de señal principales descritas

![](assets/manage-trait-rules.png)

1. Las fichas **[!UICONTROL Expression Builder]** o **[!UICONTROL Code View]** proporcionan una descripción general de las reglas de su rasgo. La pestaña **[!UICONTROL Expression Builder]** le permite crear reglas con campos y menús desplegables. **[!UICONTROL Code View]** le permite crear reglas escribiendo manualmente esas expresiones como código. La ilustración anterior muestra un rasgo simple compuesto por una señal que evalúa los datos para una condición correspondiente en la que una clave de producto es igual a un valor específico, en este caso `color == "blue"`.

1. Los campos y controles de esta sección permiten crear señales a partir de pares clave-valor y establecer la relación entre ellos con un operador de comparación. Se requieren una clave, un operador y un valor.
1. [!UICONTROL Data Explorer Options] le permite rellenar las realizaciones de características para sus señales.

   >[!NOTE]
   >
   >Esta opción solo está disponible para [!UICONTROL Data Explorer] clientes. Póngase en contacto con su consultor de Adobe para obtener más información.

1. Esta sección muestra una estimación de las realizaciones de características de los últimos 7 días, para las señales definidas en [!UICONTROL Expression Builder], para las características rellenadas y no rellenadas.

   >[!NOTE]
   >
   >Esta opción solo está disponible para [!UICONTROL Data Explorer] clientes. Póngase en contacto con su consultor de Adobe para obtener más información.

1. Los campos de prueba permiten validar combinaciones de reglas de señal para los [!DNL URL] que desea utilizar al enviar datos al Audience Manager.

## Crear una regla de rasgos {#create-trait-rule}

Las reglas (o expresiones) constan de pares de clave-valor individuales o grupos de ellos. Los operadores de comparación establecen la relación entre pares clave-valor. Para crear una regla, proporcione una clave y un valor, seleccione un operador y haga clic en **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Complete los campos obligatorios de la sección **[!UICONTROL Basic Information]** *antes de* crear reglas de rasgos.

1. Expanda la sección **[!UICONTROL Trait Expression]** e introduzca un nombre de clave y valor. Esto crea un *`signal`*.

   >[!NOTE]
   >
   >Incluya el prefijo `c_` (o cualquier otra convención de nomenclatura) para la variable clave si las llamadas de evento envían datos a [!DNL Audience Manager] mediante esa sintaxis.

1. Seleccione un [operador de comparación](../../features/traits/trait-comparison-operators.md) de la lista desplegable **[!UICONTROL Operator]**. El operador de comparación evalúa la relación entre los elementos de una señal.

   >[!NOTE]
   >
   >El operador [!DNL Boolean] [!UICONTROL OR] establece la relación entre varias señales *dentro de* un grupo y no se pueden cambiar.

1. Haga clic en **[!UICONTROL Add Rule]**. La regla guardada aparece en el espacio de trabajo de características encima de los campos de entrada de datos.

### Ejemplo {#example-trait-rule}

En el ejemplo siguiente, un usuario ha creado una nueva regla de rasgos basada en el ID del producto. Para generar esta regla, el usuario proporcionó la clave `productkey` vinculada con un operador igual (`==`) al valor `2093`.

![](assets/tb_sample_rule1.png)

Al hacer clic en **[!UICONTROL Add Rule]**, se guarda y se mueve el rasgo al espacio de trabajo [!UICONTROL Expression Builder].

![](assets/tb_sample_rule2.png)

## Crear un nuevo grupo de reglas {#create-rule-group}

Este procedimiento describe cómo crear un nuevo grupo de reglas.

<!-- t_tb_new_rule_group.xml -->

El rasgo debe contener al menos dos reglas para poder crear un nuevo grupo de reglas.

1. Mueva el cursor sobre la regla que desee mover para resaltarla.
1. Pase el ratón sobre el borde de regla resaltado.

   Esto separa automáticamente la regla de su grupo actual y la mueve a un nuevo grupo.

   >[!NOTE]
   >
   >Vuelva a arrastrar una regla a su grupo original si la mueve de forma involuntaria.

1. Seleccione un operador [!DNL Boolean] ([!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) en el menú desplegable para establecer la relación entre los grupos de reglas.

## Mover reglas entre grupos {#move-rules-between-groups}

Para mover una regla, haga clic en y arrástrela a otro grupo.

## Editar una característica {#edit-trait}

Este procedimiento describe cómo editar un rasgo.

<!-- t_tb_edit.xml -->

1. En el panel [!UICONTROL Traits], pase el ratón sobre la columna **[!UICONTROL Actions]** para ver la característica que desea editar. Esto abre los iconos de administración de características.
1. Haga clic en el lápiz para editar la característica.

   ![](assets/tb_edit_trait.png)

## Eliminar una regla de rasgos {#delete-trait}

Este procedimiento describe cómo eliminar una regla de rasgos.

<!-- t_tb_delete_rule.xml -->

1. En el panel [!UICONTROL Traits], pase el ratón sobre las [!UICONTROL Actions] columnas de la característica que desea editar y haga clic en el icono de lápiz. Esto abre los iconos de administración de características.
1. Expanda la sección [!UICONTROL Trait Expression].
1. Pase el ratón sobre la regla que quiera eliminar y haga clic en el icono X. La regla se elimina inmediatamente.

>[!MORELIKETHIS]
>
>* [Crear nuevo grupo de reglas](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Mover reglas entre grupos](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Crear una regla de rasgos](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Eliminar una regla de rasgos](../../features/traits/manage-trait-rules.md#delete-trait)
>* [Mover reglas entre grupos](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
