---
description: En el Generador de rasgos, el Generador de expresiones permite crear y probar reglas que establecen requisitos de cualificación de audiencias. Las reglas constan de pares de clave-valor como "color == azul" o "precio &gt; 100". Los operadores de comparación establecen la relación entre claves y valores. Las expresiones booleanas determinan la relación entre los grupos de reglas.
seo-description: En el Generador de rasgos, el Generador de expresiones permite crear y probar reglas que establecen requisitos de cualificación de audiencias. Las reglas constan de pares de clave-valor como "color == azul" o "precio &gt; 100". Los operadores de comparación establecen la relación entre claves y valores. Las expresiones booleanas determinan la relación entre los grupos de reglas.
seo-title: Administración de normas de rasgos
solution: Audience Manager
title: Administración de normas de rasgos
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: 'Rasgos '
exl-id: 4561b19a-bbb5-41ec-ac79-ab3e2ab75548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 1%

---

# Administración de normas de rasgos {#managing-trait-rules}

En [!UICONTROL Trait Builder], el [!UICONTROL Expression Builder] permite crear y probar reglas que establecen requisitos de cualificación de audiencia. Las reglas constan de pares de clave-valor como `color == blue` o `price > 100`. Los operadores de comparación establecen la relación entre claves y valores. [!DNL Boolean] las expresiones determinan la relación entre los grupos de reglas.

<!-- c_tb_rules.xml -->

## Características de las reglas de señal principales descritas

![](assets/manage-trait-rules.png)

1. Las pestañas **[!UICONTROL Expression Builder]** o **[!UICONTROL Code View]** proporcionan una visión general de las reglas de su rasgo. La pestaña **[!UICONTROL Expression Builder]** permite crear reglas con campos y menús desplegables. El **[!UICONTROL Code View]** permite crear reglas escribiendo manualmente esas expresiones como código. La ilustración anterior muestra un rasgo simple compuesto por una señal que evalúa los datos para una condición de calificación en la que una clave de producto es igual a un valor específico, en este caso `color == "blue"`.

1. Los campos y controles de esta sección permiten crear señales a partir de pares clave-valor y establecer la relación entre ellos con un operador de comparación. Se requiere una clave, un operador y un valor.
1. El [!UICONTROL Data Explorer Options] permite rellenar las realizaciones de características para las señales.

   >[!NOTE]
   >
   >Esta opción solo está disponible para clientes [!UICONTROL Data Explorer] . Póngase en contacto con el consultor de Adobe para obtener más información.

1. Esta sección muestra una estimación de las realizaciones de características de los últimos 7 días, para las señales definidas en [!UICONTROL Expression Builder], para los rasgos rellenados y no rellenados.

   >[!NOTE]
   >
   >Esta opción solo está disponible para clientes [!UICONTROL Data Explorer] . Póngase en contacto con el consultor de Adobe para obtener más información.

1. Los campos de prueba permiten validar combinaciones de reglas de señal o los [!DNL URL]s que desea utilizar al enviar datos al Audience Manager.

## Crear una regla de rasgos {#create-trait-rule}

Las reglas (o expresiones) constan de pares individuales o grupos de pares clave-valor. Los operadores de comparación establecen la relación entre pares clave-valor. Para crear una regla, proporcione una clave, un valor, seleccione un operador y haga clic en **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Complete los campos requeridos de la sección **[!UICONTROL Basic Information]** *antes de* crear reglas de características.

1. Expanda la sección **[!UICONTROL Trait Expression]** e introduzca una clave y un nombre de valor. Esto crea un *`signal`*.

   >[!NOTE]
   >
   >Incluya el prefijo `c_` (o cualquier otra convención de nomenclatura) para la variable clave si las llamadas de evento envían datos a [!DNL Audience Manager] mediante esa sintaxis.

1. Seleccione un [comparison operator](../../features/traits/trait-comparison-operators.md) en la lista desplegable **[!UICONTROL Operator]**. El operador de comparación evalúa la relación entre los elementos de una señal.

   >[!NOTE]
   >
   >El operador [!DNL Boolean] [!UICONTROL OR] establece la relación entre varias señales *dentro de* un grupo y no se puede cambiar.

1. Haga clic **[!UICONTROL Add Rule]**. La regla guardada aparece en el espacio de trabajo de características encima de los campos de entrada de datos.

### Ejemplo {#example-trait-rule}

En el siguiente ejemplo, un usuario ha creado una nueva regla de rasgos basada en el ID del producto. Para crear esta regla, el usuario proporcionó la clave `productkey` vinculada con un operador igual ( `==`) al valor `2093`.

![](assets/tb_sample_rule1.png)

Al hacer clic en **[!UICONTROL Add Rule]** se guarda y se mueve el rasgo al espacio de trabajo [!UICONTROL Expression Builder].

![](assets/tb_sample_rule2.png)

## Crear un nuevo grupo de reglas {#create-rule-group}

Este procedimiento describe cómo crear un nuevo grupo de reglas.

<!-- t_tb_new_rule_group.xml -->

El rasgo debe contener al menos dos reglas para poder crear un nuevo grupo de reglas.

1. Mueva el cursor sobre la regla que desee mover para resaltarla.
1. Pase el ratón sobre el borde de la regla resaltado.

   Esto separa automáticamente la regla de su grupo actual y la mueve a un grupo nuevo.

   >[!NOTE]
   >
   >Arrastre una regla de nuevo al grupo original si la mueve de forma involuntaria.

1. Seleccione un operador [!DNL Boolean] ([!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) en el menú desplegable para establecer la relación entre los grupos de reglas.

## Mover reglas entre grupos {#move-rules-between-groups}

Para mover una regla, haga clic en y arrástrela a otro grupo.

## Editar un rasgo {#edit-trait}

Este procedimiento describe cómo editar un rasgo.

<!-- t_tb_edit.xml -->

1. En el tablero [!UICONTROL Traits], pase el ratón sobre la columna **[!UICONTROL Actions]** del rasgo que desea editar. Esto muestra los iconos de administración de características.
1. Haga clic en el lápiz para editar el rasgo.

   ![](assets/tb_edit_trait.png)

## Eliminar una regla de rasgos {#delete-trait}

Este procedimiento describe cómo eliminar una regla de rasgos.

<!-- t_tb_delete_rule.xml -->

1. En el tablero [!UICONTROL Traits], pase el ratón sobre las columnas [!UICONTROL Actions] de la característica que desee editar y haga clic en el icono de lápiz. Esto muestra los iconos de administración de características.
1. Expanda la sección [!UICONTROL Trait Expression] .
1. Pase el ratón sobre la regla que quiera eliminar y haga clic en el icono X . La regla se elimina inmediatamente.

>[!MORELIKETHIS]
>
>* [Crear un nuevo grupo de reglas](../../features/traits/manage-trait-rules.md#create-rule-group)
* [Mover reglas entre grupos](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
* [Crear una regla de rasgos](../../features/traits/manage-trait-rules.md#create-trait-rule)
* [Eliminar una regla de rasgos](../../features/traits/manage-trait-rules.md#delete-trait)
* [Mover reglas entre grupos](../../features/traits/manage-trait-rules.md#move-rules-between-groups)

