---
description: En el Generador de rasgos, el Generador de expresiones permite crear y probar reglas que establecen requisitos de cualificación de audiencia. Las reglas constan de pares de clave-valor como "color == azul" o "precio > 100". Los operadores de comparación establecen la relación entre las claves y los valores. Las expresiones booleanas determinan la relación entre los grupos de reglas.
seo-description: En el Generador de rasgos, el Generador de expresiones permite crear y probar reglas que establecen requisitos de cualificación de audiencia. Las reglas constan de pares de clave-valor como "color == azul" o "precio > 100". Los operadores de comparación establecen la relación entre las claves y los valores. Las expresiones booleanas determinan la relación entre los grupos de reglas.
seo-title: Administración de reglas de características
solution: Audience Manager
title: Administración de reglas de características
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Administración de reglas de características {#managing-trait-rules}

En [!UICONTROL Trait Builder], [!UICONTROL Expression Builder] permite crear y probar reglas que establecen requisitos de cualificación de audiencia. Las reglas constan de pares de clave-valor como `color == blue` o `price > 100`. Los operadores de comparación establecen la relación entre las claves y los valores. [!DNL Boolean] las expresiones determinan la relación entre los grupos de reglas.

<!-- c_tb_rules.xml -->

## Características de las reglas de señal principales descritas

![](assets/manage-trait-rules.png)

1. Las **[!UICONTROL Expression Builder]** fichas o **[!UICONTROL Code View]** proporcionan información general sobre las reglas de su característica. La **[!UICONTROL Expression Builder]** ficha permite crear reglas con campos y menús desplegables. Permite **[!UICONTROL Code View]** crear reglas escribiendo manualmente esas expresiones como código. La ilustración anterior muestra una característica simple compuesta por una señal que evalúa los datos para una condición de cualificación en la que una clave de producto es igual a un valor específico, en este caso `color == "blue"`.

1. Los campos y controles de esta sección permiten crear señales a partir de pares clave-valor y establecer la relación entre ellos con un operador de comparación. Se requiere una clave, un operador y un valor.
1. El [!UICONTROL Data Explorer Options] permite rellenar las realizaciones de características para las señales.
   >[!NOTE]
   >
   >Esta opción solo está disponible para [!UICONTROL Data Explorer] los clientes. Póngase en contacto con su consultor de Adobe para obtener más información.
1. Esta sección muestra una estimación de las realizaciones de rasgos de los últimos 7 días, para las señales definidas en la [!UICONTROL Expression Builder], para las características rellenas y no rellenas.
   >[!NOTE]
   >
   >Esta opción solo está disponible para [!UICONTROL Data Explorer] los clientes. Póngase en contacto con su consultor de Adobe para obtener más información.
1. Los campos de prueba le permiten validar combinaciones de reglas de señal o [!DNL URL]s que desee utilizar al enviar datos a Audience Manager.

## Crear una regla de características {#create-trait-rule}

Las reglas (o expresiones) constan de pares individuales o grupos de pares de clave-valor. Los operadores de comparación establecen la relación entre pares de clave-valor. Para crear una regla, proporcione una clave, un valor, seleccione un operador y haga clic en **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Complete los campos obligatorios de la **[!UICONTROL Basic Information]** sección *antes* de crear reglas de características.

1. Expanda la **[!UICONTROL Trait Expression]** sección e introduzca una clave y un nombre de valor. Esto crea un *`signal`*.
   >[!NOTE]
   >
   >Incluya el `c_` prefijo (o cualquier otra convención de nombre) para la variable clave si las llamadas al evento envían datos a [!DNL Audience Manager] través de esa sintaxis.
1. Seleccione un operador [de](../../features/traits/trait-comparison-operators.md) comparación en la **[!UICONTROL Operator]** lista desplegable. El operador de comparación evalúa la relación entre los elementos de una señal.
   >[!NOTE]
   >
   >El [!DNL Boolean] operador establece la relación entre varias señales [!UICONTROL OR] dentro ** de un grupo y no se puede cambiar.
1. Haga clic en **[!UICONTROL Add Rule]**. La regla guardada aparece en el espacio de trabajo de características encima de los campos de entrada de datos.

### Ejemplo {#example-trait-rule}

En el ejemplo siguiente, un usuario ha creado una nueva regla de características basada en el ID de producto. Para generar esta regla, el usuario proporcionó la clave `productkey` vinculada con un operador igual ( `==`) al valor `2093`.
![](assets/tb_sample_rule1.png)

Al hacer clic en **[!UICONTROL Add Rule]** se guarda y se mueve la característica al espacio de trabajo [!UICONTROL Expression Builder] .

![](assets/tb_sample_rule2.png)

>[!MORE_LIKE_THIS]
>
>* [Crear un nuevo grupo de reglas](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Mover reglas entre grupos](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Eliminar una regla de características](../../features/traits/manage-trait-rules.md#delete-trait)


## Create a New Rule Group {#create-rule-group}

Este procedimiento describe cómo crear un nuevo grupo de reglas.

<!-- t_tb_new_rule_group.xml -->

La característica debe contener al menos dos reglas para poder crear un nuevo grupo de reglas.

1. Mueva el cursor sobre la regla que desee mover para resaltarla.
1. Pase el ratón sobre el borde de la regla resaltado.
Esto separa automáticamente la regla de su grupo actual y la mueve a un nuevo grupo.
   >[!NOTE]
   >
   >Arrastre una regla de nuevo a su grupo original si la mueve de forma involuntaria.
1. Seleccione un [!DNL Boolean] operador ( [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) en el menú desplegable para establecer la relación entre los grupos de reglas.

>[!MORE_LIKE_THIS]
>
>* [Crear una regla de características](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Mover reglas entre grupos](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Eliminar una regla de características](../../features/traits/manage-trait-rules.md#delete-trait)


## Mover reglas entre grupos {#move-rules-between-groups}

Para mover una regla, haga clic y arrástrela a otro grupo.

>[!MORE_LIKE_THIS]
>
>* [Crear una regla de características](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Crear un nuevo grupo de reglas](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Eliminar una regla de características](../../features/traits/manage-trait-rules.md#delete-trait)


## Editar una característica {#edit-trait}

Este procedimiento describe cómo editar una característica.

<!-- t_tb_edit.xml -->

1. En el [!UICONTROL Traits] tablero, coloque el puntero sobre la columna **[!UICONTROL Actions]** de la característica que desee editar. Esto muestra los iconos de administración de características.
1. Haga clic en el lápiz para editar la característica.

   ![](assets/tb_edit_trait.png)

## Eliminar una regla de características {#delete-trait}

Este procedimiento describe cómo eliminar una regla de características.

<!-- t_tb_delete_rule.xml -->

1. En el [!UICONTROL Traits] tablero, pase el ratón sobre las [!UICONTROL Actions] columnas de la característica que desee editar y haga clic en el icono del lápiz. Esto muestra los iconos de administración de características.
1. Expand the [!UICONTROL Trait Expression] section.
1. Pase el ratón sobre la regla que desee eliminar y haga clic en el icono X. La regla se elimina inmediatamente.