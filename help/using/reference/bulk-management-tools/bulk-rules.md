---
description: Las hojas de cálculo de creación y actualización aceptan un encabezado traitRule que permite aplicar varias reglas en una sola operación. Siga estas instrucciones para realizar solicitudes de reglas masivas.
seo-description: The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.
seo-title: Create or Update Trait Rules and Segment Rules
solution: Audience Manager
title: Creación o actualización de reglas de rasgos y reglas de segmentos
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
TQID: https://experienceleague.adobe.com/7vkYd55lKv1PCjRqX-OxK1A-VIjgH3O9Tx0AnbZvRWA
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 345
ht-degree: 1%

---

# Creación o actualización de reglas de rasgos y reglas de segmentos{#create-or-update-trait-rules-and-segment-rules}

Las hojas de cálculo de creación y actualización aceptan un encabezado traitRule que permite aplicar varias reglas en una sola operación. Siga estas instrucciones para realizar solicitudes de reglas masivas.

>[!IMPORTANT]
>
>Las herramientas de administración masiva no son una oferta de Adobe oficialmente compatible. La resolución de problemas y la asistencia técnica a través del Servicio de atención al cliente se gestionarán caso por caso.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[Los permisos de grupo RBAC](../../features/administration/administration-overview.md) asignados en la interfaz de usuario de [!DNL Audience Manager] se respetan en [!UICONTROL Bulk Management Tools].

## Uso de reglas de rasgos {#trait-rules}

En la hoja de cálculo, la columna de regla de rasgos devuelve y acepta reglas compuestas de expresiones booleanas, operadores de comparación y expresiones regulares. Puede crear reglas con el generador de rasgos o segmentos en [!DNL Audience Manager] y copiarlas en la hoja de cálculo. O bien, si está familiarizado con la sintaxis de reglas, puede escribir expresiones directamente en las hojas de cálculo.

## Ejemplo del generador de reglas {#rule-builder-example}

Veamos un ejemplo que muestra cómo utilizar [!UICONTROL Segment Builder] para crear una regla que se pueda agregar a la hoja de cálculo masiva. Sin embargo, no se trata de un conjunto de instrucciones paso a paso para esas herramientas. En su lugar, vamos a empezar con una regla simple que ya se ha creado. Para obtener instrucciones sobre cómo usar los generadores de reglas, consulte [Generador de segmentos](../../features/segments/segment-builder.md) y [Generador de rasgos](../../features/traits/about-trait-builder.md).

Con el generador de reglas visual, hemos creado una regla de segmento con 3 características y un operador booleano [!UICONTROL AND].

![](assets/visualrule.png)

Haga clic en **[!UICONTROL Code View]** para obtener la versión de texto de esta regla.

>[!TIP]
>
>Haga clic en **[!UICONTROL Validate Expression]** para comprobar la lógica de la regla. Esto ayudará a evitar que cargue una regla no válida.

![](assets/coderule.png)

Pegue la regla en la hoja de cálculo [!UICONTROL Bulk Management Tools] y confirme los cambios para actualizar las reglas de segmentos de forma masiva.

![](assets/segmentrule.png)

## Creación de sus propias reglas {#create-rules}

Puede escribir sus propias reglas fuera de [!UICONTROL Rule Builder]. Antes de empezar, asegúrese de leer la documentación que cubre aspectos como los operadores, las expresiones y las variables requeridas. Le recomendamos que revise lo siguiente:

* [Trabajando Con Operadores De Comparación En El Generador De Características](../../features/traits/trait-comparison-operators.md)
* [Orden de operaciones](../../features/traits/trait-operator-precedence.md)
* [Requisitos de prefijo para variables clave](../../features/traits/trait-variable-prefixes.md)
* [Expresiones de muestra con operadores booleanos y de comparación](../../features/traits/trait-expression-samples.md)
