---
description: Con Trait Recommendations, al crear o editar un segmento en Generador de segmentos, se obtienen recomendaciones sobre las características adicionales que puede incluir que son similares a las características de la regla de segmento. Añada las características recomendadas al segmento para aumentar la audiencia objetivo.
seo-description: Obtenga recomendaciones de rasgos en directo a medida que cree sus segmentos.
seo-title: Trait Recommendations
solution: Audience Manager
title: Trait Recommendations
uuid: null
translation-type: tm+mt
source-git-commit: e369038fbc83e28d10da24060699488faf783511

---


# Trait Recommendations

Obtenga recomendaciones de rasgos en directo a medida que cree sus segmentos.

## Información general

[!UICONTROL Trait Recommendations]equipado con [!DNL Adobe Sensei], incorpora la tecnología de datos en los flujos de trabajo diarios de Audience Manager.
With [!UICONTROL Trait Recommendations], when you build or edit a segment in [Segment Builder](segment-builder.md), you get recommendations on additional traits you can include, that are similar to the traits in the segment rule. Añada las características recomendadas al segmento para aumentar la audiencia objetivo.

![Información general sobre características de características](assets/trait-recommendations-overview.png)

**En forma nula:**

* Audience Manager muestra características individuales y características de terceros de las fuentes de datos suscritas actualmente como características recomendadas.
* Audience Manager muestra un máximo de cincuenta características similares a la de la regla de segmentos.
* Puede filtrar las fuentes de datos desde las cuales no desee ver ninguna recomendación.
* When calculating similarities, Audience Manager considers [UUIDs](../../reference/ids-in-aam.md) that qualified for the trait during the last 30 days.
* Si ve el mensaje de error "No se encontraron características similares". Las características pueden ser demasiado nuevas. ", esto significa que no había actividad para esa característica en los últimos 30 días, o que Audience Manager aún no ha actualizado las recomendaciones para esa característica. Inténtelo nuevamente en 24 horas.

## Casos de uso

With [!UICONTROL Trait Recommendations], you can improve your workflows, depending on how you use Audience Manager:

* Como especialista en mercadotecnia, puede encontrar rápidamente audiencias interesadas en productos complementarios con la ayuda de características similares para aumentar su alcance.
* If you use Audience Manager as a publisher, with [!UICONTROL Trait Recommendations], you can understand audience behavior and build better segments for ad sales or user acquisition.

## Diferencias entre los modelos algorítmicos y recomendaciones de rasgos

### Modelos algorítmicos

[!UICONTROL Algorithmic Models] no sólo encuentra las características más influyentes sino que también puntua a los usuarios basándose en dichas características y asigna a cada usuario una puntuación individual. A continuación, cree características algorítmicas para dirigirse a los usuarios. With accuracy and reach controls in the [!UICONTROL Trait Builder], you can specify which users amongst all those who have the influential traits you want to target.

[!UICONTROL Algorithmic Models] permite seleccionar usuarios en diferentes niveles de precisión y probar en [!UICONTROL Audience Lab] qué grupo de usuarios se convierten mejor. See the detailed use case in [Compare Models in Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

In [!UICONTROL Algorithmic Models], the model runs every 8 days and refreshes the users qualified for algorithmic traits.

### Trait Recommendations

[!UICONTROL Trait Recommendations] es una forma rápida de obtener perspectivas sobre otras características que son similares a las que utiliza en un segmento.

You should use [!UICONTROL Trait Recommendations] when:

* Necesita perspectivas rápidas al generar un segmento;
* Utiliza los segmentos para campañas cortas o para eliminar rápidamente la audiencia que se convierte;
* Está intentando maximizar el alcance.

## Flujo de trabajo

When building or editing a segment in [Segment Builder](segment-builder.md), you can explore traits similar to the traits in the segment rule. El flujo de trabajo del Generador de segmentos es muy similar a los segmentos nuevos y existentes:

### Nuevos segmentos

1. In **Audience Data &gt; Segments**, select **Add New**.
1. In the **Traits** drop-down box, add at least one trait to the segment rule.
1. Ahora puede ver características recomendadas que son similares a las características agregadas a la regla del segmento. Desplácese hacia abajo para ver todas las características recomendadas.
1. (Optional) To exclude recommended traits from certain data sources, click the **X** symbol for the data sources you want to exclude.
   > [!NOTE]
   > 
   >Las fuentes de datos excluidas se muestran justo encima de la lista de características recomendadas. Press **X** in the grey box to remove the exclusions and see results from the respective data sources again.
1. To add recommended traits to the segment rule, click the **+** symbol.

### Segmentos existentes

1. Go to **[!UICONTROL Audience Data]&gt;[!UICONTROL Segments]**, select the segment you want to edit and press ![Edit](assets/edit-button.png).
1. Scroll down to the [!UICONTROL Traits] drop-down box.
1. Puede ver características recomendadas, que son similares a las características que ya se encuentran en la regla de segmentos. Desplácese hacia abajo para ver todas las características recomendadas.
1. (Optional) To exclude recommended traits from certain data sources, click the **X** symbol for the data sources you want to exclude.
   > [!NOTE]
   > 
   >Las fuentes de datos excluidas se muestran justo encima de la lista de características recomendadas. Press **X** in the grey box to remove the exclusions and see results from the respective data sources again.
1. To add recommended traits to the segment rule, click the **+** symbol.

Cuando crea o edita un segmento y agrega un rasgo a la regla de segmento, verá un máximo de cincuenta características recomendadas, similar a la que agregó. Si la regla de segmento contiene más de un rasgo, Audience Manager utiliza un método round robin para mostrar la mejor coincidencia para cada característica, luego la segunda coincidencia mejor para cada característica, y así sucesivamente, para las cincuenta características más grandes de población, en la regla del segmento.

![Tres características base](assets/three-base-traits.png)

Por ejemplo, cuando hay tres características en la regla de segmentos, como se muestra a continuación, las características recomendadas son:

1. Mejor coincidencia para trait 3 (la característica con la población más grande);
2. Mejor coincidencia para trait 1;
3. Mejor coincidencia para trait 2;
4. Segunda coincidencia mejor para trait 3;
5. La segunda mejor coincidencia para trait 1, y así sucesivamente hasta que llegue a cincuenta características.

Para obtener recomendaciones para un rasgo específico, puede hacer clic en las características de la regla de segmento (1) o en la vista de características recomendada (2).

![](assets/three-base-traits-numbered.png)

Al hacer clic en una característica se abre una ventana emergente, como se muestra en la siguiente imagen. If the recommended traits are not part of the segment, you can add them to the segment by pressing **+**.

![](assets/add_to_segments.png)

> [!TIP]
>
>Las fuentes de datos excluidas de la página principal se consideran al generar recomendaciones dentro de la ventana emergente de información de rasgos. Y, si excluye fuentes de datos en esta vista, las exclusiones se aplican a la página principal.

> [!NOTE]
>
> Las características recomendadas pueden ser características de origen o características de terceros de fuentes a las que se suscriba.

## Cómo funciona

To produce trait recommendations, Audience Manager computes the [Jaccard similarity](https://en.wikipedia.org/wiki/Jaccard_index) between the target trait and every other trait that your account has access to, including third-party data. Audience Manager muestra hasta cincuenta características que tienen la mayor similitud.

## Puntuación de similitud de características

Audience Manager calculate the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL UUID]s and then divide the two. Para dos características A y B, el cálculo tiene este aspecto:

![](assets/jaccard_similarity.png)

Consulte también los dos ejemplos siguientes.

### Ejemplo 1 - Puntuación de similitud de rasgo baja

Given two traits A and B, let's say each of the traits has a population of 1,000,000 [!UICONTROL UUID]s, 25,000 [!UICONTROL UUID]s of which qualify for both traits.
Using the formula above, this will result in: 25,000 / 1,975,000 = 0.012. This is a low [!UICONTROL Trait Similarity Score], the two traits are very dissimilar.

![](assets/Trait-Recommendations-Low-overlap.png)

### Ejemplo 2 - Puntuación de similitud de características

If the same traits A and B had 400,000 [!UICONTRL UUID]s that qualify for both traits, the [!UICONTROL Trait Similarity Score] is much higher:
400,000 / 1,600,000 = 0.25

![](assets/Trait-Recommendations-High-overlap.png)

### Cómo interpretar el puntaje de similitudes de características

Utilice la tabla siguiente como guía aproximada de similitud de rasgos. Esta guía se basa en las puntuaciones de similitudes observadas en la mayoría de las características.

| [!UICONTROL Trait Similarity Score] | Relevancia |
---------|----------|
| 0.1 y posterior | Alta similitud entre características |
| 0.03 - 0.1 | Similitud media entre características |
| 0.01 - 0.03 | Similitud baja entre características |
| 0 - 0.01 | Similitud muy baja entre características |

## Control de acceso basado en roles (RBAC)

For companies using [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), you need to have permission to create and edit segments in order to see recommended traits. And, the recommended traits you see are only the ones from data sources that you have access to via [!UICONTROL RBAC]. Read more about [!UICONTROL RBAC] controls [here](../administration/administration-overview.md).

## Limitaciones

* Actualmente, Audience Manager no muestra características de carpeta como características recomendadas. Read more about folder traits [here](../traits/manage-folder-traits.md).
* When displaying Trait Recommendations, Audience Manager does not take into account [!DNL Boolean] operators ([!DNL AND], [!DNL OR], [!DNL NOT]) in segment rules.