---
description: Con Trait Recommendations, al crear o editar un segmento en Generador de segmentos, se obtienen recomendaciones sobre las características adicionales que puede incluir que son similares a las características de la regla de segmento. Añada las características recomendadas al segmento para aumentar la audiencia objetivo.
seo-description: Obtenga recomendaciones de características en directo a medida que genera sus segmentos.
seo-title: Trait Recommendations
solution: Audience Manager
title: Trait Recommendations
uuid: null
translation-type: tm+mt
source-git-commit: a67998b925002438b20fdde81f1abec4acbd5602

---


# Trait Recommendations

Obtenga recomendaciones de características en directo a medida que genera sus segmentos.

## Demostración en video

Comience viendo el [!UICONTROL Trait Recommendations] video de abajo y luego lea para obtener más información.

>[!VIDEO](https://video.tv.adobe.com/v/26228/?captions=spa)

En el siguiente vídeo se describe el flujo de trabajo para [!UICONTROL Marketplace Recommendations], que muestra cómo agregar recomendaciones de características a los segmentos, desde fuentes de datos en [!UICONTROL Audience Marketplace].

>[!VIDEO](https://video.tv.adobe.com/v/29363/?captions=spa)

## Información general

[!UICONTROL Trait Recommendations], con tecnología [!DNL Adobe Sensei], incorpora la ciencia de datos en los flujos de trabajo diarios de Audience Manager.
With [!UICONTROL Trait Recommendations], when you build or edit a segment in [Segment Builder](segment-builder.md), you get recommendations on additional traits you can include, that are similar to the traits in the segment rule.

Audience Manager muestra las recomendaciones de características tanto de sus características individuales, en la **[!UICONTROL Recommendations]** sección como de **[!UICONTROL Audience Marketplace]**, en la **[!UICONTROL Recommendations from Marketplace]** sección.

![Información general sobre las recomendaciones de características](assets/trait-recommendations-overview-full.png)

Añada las características recomendadas al segmento para aumentar la audiencia objetivo.

**En pocas palabras:**

* Audience Manager muestra las características individuales en la [!UICONTROL Recommendations] sección. Las recomendaciones del mercado de fuentes públicas y privadas a las que no está suscrito están visibles en la [!UICONTROL Recommendations from Marketplace] sección .
* Audience Manager muestra un máximo de cincuenta características similares a la de la regla de segmento.
* Puede filtrar las fuentes de datos de las que no desee ver ninguna recomendación.
* Al calcular las similitudes, Audience Manager considera los [UUID](../../reference/ids-in-aam.md) que cumplen los requisitos para la característica durante los últimos 30 días.
* Si ve el mensaje de error "No se encontraron características similares. Las características pueden ser demasiado nuevas.", esto significa que no hubo actividad para esa característica en los últimos 30 días o que Audience Manager aún no ha actualizado las recomendaciones para esa característica. Inténtelo de nuevo en 24 horas.

## Casos de uso

Con [!UICONTROL Trait Recommendations], puede mejorar los flujos de trabajo, según cómo utilice Audience Manager:

* Como especialista en mercadotecnia, puede encontrar rápidamente audiencias interesadas en productos complementarios con la ayuda de características similares, para aumentar su alcance.
* Si usa Audience Manager como editor, con [!UICONTROL Trait Recommendations]esto puede comprender el comportamiento de la audiencia y crear mejores segmentos para las ventas de publicidad o la adquisición de usuarios.

## Diferencias entre recomendaciones de características y modelos algorítmicos

### Modelos algorítmicos

[!UICONTROL Algorithmic Models] no sólo encuentra las características más influyentes, sino que también puntúa a los usuarios en función de esas características y asigna a cada usuario una puntuación individual. A continuación, puede crear características algorítmicas para dirigirse a los usuarios. Con los controles de precisión y alcance en la [!UICONTROL Trait Builder], puede especificar los usuarios entre todos los que tienen las características influyentes que desea definir como objetivo.

[!UICONTROL Algorithmic Models] le permite seleccionar usuarios en diferentes niveles de precisión y probar en [!UICONTROL Audience Lab] qué grupo de usuarios se convierte mejor. Consulte el caso de uso detallado en [Comparar modelos en Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

En [!UICONTROL Algorithmic Models], el modelo se ejecuta cada 8 días y actualiza los usuarios cualificados para características algorítmicas.

### Trait Recommendations

[!UICONTROL Trait Recommendations] es una forma rápida de obtener perspectivas sobre otras características similares a las que se utilizan en un segmento.

Debe usar [!UICONTROL Trait Recommendations] cuando:

* Necesita perspectivas rápidas al crear un segmento;
* Utiliza los segmentos para campañas cortas o cuando desea suprimir rápidamente a la audiencia que realiza la conversión;
* Está intentando maximizar el alcance.

## Flujo de trabajo

Al crear o editar un segmento en el Generador [de segmentos](segment-builder.md), puede explorar características similares a las de la regla de segmentos. El flujo de trabajo [del Generador](segment-builder.md) de segmentos es muy similar para los segmentos nuevos y existentes:

### Nuevos segmentos

1. Vaya a Datos de **audiencia &gt; Segmentos** y haga clic en **Agregar nuevo**.
2. En el cuadro desplegable **Características** , agregue al menos una característica a la regla de segmento.
3. Puede ver las características recomendadas de origen en la sección y las características recomendadas de terceros en la **[!UICONTROL Recommendations]** sección **[!UICONTROL Recommendations from Marketplace]** . Todas estas recomendaciones son similares a las características agregadas a la regla de segmento. Desplácese hacia abajo para ver todas las características recomendadas.
4. (Opcional) Para excluir las características de origen recomendadas de determinadas fuentes de datos, haga clic en el símbolo **X** de las fuentes de datos que desee excluir.
   > [!NOTE]
   >
   > Las fuentes de datos excluidas se muestran justo encima de la lista de características recomendadas. Haga clic en **X** en el cuadro gris para eliminar las exclusiones y ver los resultados de las fuentes de datos correspondientes de nuevo.
5. Para agregar características recomendadas a la regla de segmento, haga clic en el símbolo **+** .

> [!IMPORTANT]
> Al agregar [!UICONTROL Marketplace] características a un segmento, las características solo se utilizan para la estimación de segmentos, hasta que se suscriba a la fuente de datos correspondiente. Las características que provienen de fuentes de datos a las que no está suscrito se marcan con un icono de carro de compras en la lista de características. Haga clic en el nombre de la característica para ir a la página de fuentes de datos y suscribirse a ella.
> ![mercado sin suscripción](assets/trait-recommendations-marketplace.png)
> Puede guardar un segmento con características de terceros solo después de suscribirse a las fuentes de datos correspondientes.

### Segmentos existentes

1. Vaya a **[!UICONTROL Audience Data]&gt;[!UICONTROL Segments]**, seleccione el segmento que desee editar y haga clic en ![Editar](assets/edit-button.png).
1. Desplácese hacia abajo hasta el cuadro [!UICONTROL Traits] desplegable.
1. Puede ver las características recomendadas, que son similares a las características que ya aparecen en la regla de segmento. Desplácese hacia abajo para ver todas las características recomendadas.
1. (Opcional) Para excluir las características recomendadas de ciertas fuentes de datos, haga clic en el símbolo **X** de las fuentes de datos que desee excluir.
   > [!NOTE]
   >
   > Las fuentes de datos excluidas se muestran justo encima de la lista de características recomendadas. Haga clic en **X** en el cuadro gris para eliminar las exclusiones y ver los resultados de las fuentes de datos correspondientes de nuevo.
1. Para agregar características recomendadas a la regla de segmento, haga clic en el símbolo **+** .

Al crear o editar un segmento y agregar una característica a la regla de segmento, verá un máximo de cincuenta características recomendadas, similares a la que ha agregado. Si la regla de segmento contiene más de una característica, Audience Manager utiliza un método de rotación redonda para mostrar la mejor coincidencia para cada característica, la segunda mejor coincidencia para cada característica, etc., para las cincuenta características más grandes por población, en la regla de segmento.

![Tres características base](assets/three-base-traits.png)

Por ejemplo, cuando hay tres características en la regla de segmento, como se muestra a continuación, las características recomendadas son:

1. Mejor coincidencia para la característica 3 (la característica con la mayor población);
2. Mejor coincidencia para la característica 1;
3. Mejor coincidencia para la característica 2;
4. Segunda mejor coincidencia para la característica 3;
5. Segunda mejor coincidencia para el rasgo 1, y así sucesivamente hasta llegar a cincuenta rasgos.

Para obtener recomendaciones para una característica específica, puede hacer clic en las características en la regla de segmento (1) o en la vista de características recomendadas (2).

![base-traits-example](assets/three-base-traits-numbered.png)

Al hacer clic en una característica propia se abre una ventana emergente, como se muestra en la imagen de abajo. Si las características recomendadas no forman parte del segmento, puede agregarlas al segmento pulsando **+**.

![complemento al segmento](assets/add_to_segments.png)

> [!TIP]
>
>Las fuentes de datos excluidas de la página principal se consideran al generar recomendaciones dentro de la ventana emergente de información de características. Y, si excluye las fuentes de datos en esta vista, las exclusiones se aplican a la página principal.

> [!NOTE]
>
> Las características recomendadas pueden ser sus características de origen o de terceros a partir de fuentes de datos a las que esté suscrito en [!UICONTROL Audience Marketplace].

## Cómo funciona

Para generar recomendaciones de características, Audience Manager calcula la similitud [de](https://en.wikipedia.org/wiki/Jaccard_index) Jaccard entre la característica objetivo y cualquier otra característica a la que su cuenta tenga acceso, incluidos los datos de terceros. A continuación, Audience Manager muestra hasta cincuenta características que tienen la mayor similitud.

## Puntuación de similitud de características

Audience Manager calcula los [!UICONTROL Trait Similarity Score] dos rasgos calculando la intersección y la unión en términos del número de [!UICONTROL UUID]s y, a continuación, divide los dos. Para dos características A y B, el cálculo tiene este aspecto:

![similitud de jaccard](assets/jaccard_similarity.png)

Consulte también los dos ejemplos siguientes.

### Ejemplo 1: Puntuación de similitud de características bajas

Dadas las dos características A y B, digamos que cada una de las características tiene una población de 1,000,000 [!UICONTROL UUID]s, 25,000 [!UICONTROL UUID]s de las cuales califican para ambas características.
Si se utiliza la fórmula anterior, el resultado será: 25.000 / 1.975.000 = 0,012. Este es un bajo [!UICONTROL Trait Similarity Score], los dos rasgos son muy diferentes.

![trait-recommendations-low-superposición](assets/Trait-Recommendations-Low-overlap.png)

### Ejemplo 2: Puntuación de similitud de características

Si los mismos rasgos A y B tenían 400.000 [!UICONTRL ]UUID que cumplen los dos rasgos, el valor [!UICONTROL Trait Similarity Score] es mucho mayor:
400.000 / 1.600.000 = 0,25

![trait-recommendations-high-superposición](assets/Trait-Recommendations-High-overlap.png)

### Cómo interpretar la puntuación de similitud de características

Utilice la siguiente tabla como guía general para la similitud de características. Esta guía se basa en las puntuaciones de similitud observadas en la mayoría de las características.

| [!UICONTROL Trait Similarity Score] | Importancia |
---------|----------|
| 0.1 y posterior | Gran similitud entre características |
| 0.03 - 0.1 | Similitud media entre características |
| 0.01 - 0.03 | Baja similitud entre características |
| 0 - 0.01 | Muy baja similitud entre características |

## Control de acceso basado en roles (RBAC)

Para las empresas que utilizan [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), debe tener permiso para crear y editar segmentos para ver las características recomendadas. Y, las características recomendadas que ve son sólo las de los orígenes de datos a los que tiene acceso mediante [!UICONTROL RBAC]. Lea más sobre [!UICONTROL RBAC] los controles [aquí](../administration/administration-overview.md).

## Limitaciones

* Actualmente, Audience Manager no muestra las características de la carpeta como características recomendadas. Obtenga más información sobre las características de las carpetas [aquí](../traits/manage-folder-traits.md).
* Al mostrar Recomendaciones de características, Audience Manager no tiene en cuenta [!DNL Boolean] los operadores ([!DNL AND], [!DNL OR], [!DNL NOT]) en las reglas de segmentos.
