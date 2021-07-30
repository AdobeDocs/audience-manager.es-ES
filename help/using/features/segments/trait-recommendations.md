---
description: Con Trait Recommendations, al crear o editar un segmento en Generador de segmentos, se obtienen recomendaciones sobre las características adicionales que puede incluir que son similares a las características de la regla de segmento. Añada las características recomendadas al segmento para aumentar la audiencia objetivo.
seo-description: Obtenga recomendaciones de características activas a medida que genera sus segmentos.
seo-title: Recomendaciones de rasgos
solution: Audience Manager
title: Recomendaciones de rasgos
feature: 'Segmentos '
exl-id: 7ef862a9-7354-49fb-9af0-925d827a5165
source-git-commit: 432b12c4d4fb567d1a0bcaa9d12baaac5e3ae0f7
workflow-type: tm+mt
source-wordcount: '1574'
ht-degree: 8%

---

# Recomendaciones de rasgos

Obtenga recomendaciones de características activas a medida que genera sus segmentos, a partir de sus propios rasgos de origen y fuentes de datos [!UICONTROL Audience Marketplace].

## Demostración en vídeo

Empiece viendo el vídeo [!UICONTROL Trait Recommendations] que aparece a continuación y continúe leyendo para obtener más información. La demostración de vídeo le muestra cómo trabajar con recomendaciones de sus propios rasgos de origen, así como con recomendaciones de rasgos de fuentes de datos [!UICONTROL Audience Marketplace] a las que *ya está suscrito*.

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

El siguiente vídeo describe el flujo de trabajo de [!UICONTROL Marketplace Recommendations] y le muestra cómo añadir características a los segmentos, en función de las recomendaciones de las fuentes de datos de [!UICONTROL Audience Marketplace]. Estas recomendaciones se basan en fuentes de datos a las que *no está suscrito*.

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## Información general

[!UICONTROL Trait Recommendations], con tecnología de  [!DNL Adobe Sensei], incorpora la ciencia de datos en los flujos de trabajo diarios del Audience Manager.
Con [!UICONTROL Trait Recommendations], cuando crea o edita un segmento en [Generador de segmentos](segment-builder.md), obtiene recomendaciones sobre características adicionales que puede incluir, que son similares a las características de la regla de segmento.

El Audience Manager muestra las recomendaciones de características tanto desde sus características de origen, en la sección **[!UICONTROL Recommendations]** como desde **[!UICONTROL Audience Marketplace]**, en la sección **[!UICONTROL Recommendations from Marketplace]**.

Añada las características recomendadas al segmento para aumentar la audiencia objetivo.

![Información general de Trait Recommendations](assets/trait-recommendations-overview-full.png)

**En pocas palabras:**

* El Audience Manager muestra los rasgos de origen en la sección [!UICONTROL Recommendations]. Las recomendaciones de Marketplace de fuentes públicas y privadas a las que no está suscrito se pueden ver en la sección [!UICONTROL Recommendations from Marketplace] . Haga clic en el nombre de la fuente para ir a [!UICONTROL Audience Marketplace] y suscribirse.
* El Audience Manager muestra un máximo de cincuenta características similares a la de la regla de segmento.
* Puede filtrar las fuentes de datos de las que no desee ver ninguna recomendación.
* Al calcular similitudes, el Audience Manager considera [UUIDs](../../reference/ids-in-aam.md) que cumplen los requisitos para el rasgo durante los últimos 30 días.
* Si ve el mensaje de error &quot;No se encontraron características similares. Los rasgos pueden ser demasiado nuevos.&quot;, esto significa que o bien no hubo actividad para ese rasgo en los últimos 30 días, o bien el Audience Manager aún no ha actualizado las recomendaciones para ese rasgo. Inténtelo de nuevo en 24 horas.

## Casos de uso

Con [!UICONTROL Trait Recommendations], puede mejorar los flujos de trabajo, según cómo utilice el Audience Manager:

* Como especialista en marketing, puede encontrar rápidamente audiencias interesadas en productos complementarios con la ayuda de características similares, de modo que pueda aumentar su alcance.
* Si usa Audience Manager como editor, con [!UICONTROL Trait Recommendations], puede comprender el comportamiento de la audiencia y generar mejores segmentos para las ventas de publicidad o la adquisición de usuarios.
* Como [!UICONTROL Audience Marketplace] comprador de datos, quiero descubrir datos relevantes de terceros sin navegar por un gran número de fuentes.
* Como proveedor de datos [!UICONTROL Audience Marketplace], quiero recomendar datos relevantes a los compradores para que pueda beneficiarse de suscripciones óptimas y relevantes.

## Diferencias entre Trait Recommendations y Modelos algorítmicos

### Modelos algorítmicos

[!UICONTROL Algorithmic Models] no solo encuentra los rasgos más influyentes, sino que también puntúa a los usuarios según esos rasgos y asigna a cada usuario una puntuación individual. Seguidamente, puede crear rasgos algorítmicos para segmentar los usuarios. Con los controles de precisión y alcance en [!UICONTROL Trait Builder], puede especificar a qué usuarios de todos los que tienen los rasgos influyentes desea dirigirse.

[!UICONTROL Algorithmic Models] permite seleccionar usuarios en diferentes niveles de precisión y probar en  [!UICONTROL Audience Lab] qué grupo de usuarios se convierte mejor. Consulte el caso de uso detallado en [Comparar modelos en Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

En [!UICONTROL Algorithmic Models], el modelo se ejecuta cada 8 días y actualiza los usuarios clasificados para rasgos algorítmicos.

### Recomendaciones de rasgos

[!UICONTROL Trait Recommendations] es una forma rápida de obtener perspectivas sobre otros rasgos similares a los que utiliza en un segmento.

Debe utilizar [!UICONTROL Trait Recommendations] cuando:

* Necesita perspectivas rápidas cuando crea un segmento.
* Utiliza los segmentos para campañas cortas o cuando quiere suprimir rápidamente la audiencia que convierte.
* Está intentando maximizar el alcance.

## Flujo de trabajo

Al crear o editar un segmento en [Generador de segmentos](segment-builder.md), puede explorar características similares a las de la regla de segmento. El flujo de trabajo del [Generador de segmentos](segment-builder.md) es muy similar para los segmentos nuevos y existentes:

### Nuevos segmentos

1. Vaya a **Audience Data > Segments** y haga clic en **Add New**.
1. En el cuadro desplegable **Características**, agregue al menos un rasgo a la regla de segmento.
1. Puede ver las características recomendadas de origen y las recomendaciones de características [!UICONTROL Audience Marketplace] de las fuentes a las que está suscrito, en la sección **[!UICONTROL Recommendations]**. La sección **[!UICONTROL Recommendations from Marketplace]** muestra las recomendaciones de características de fuentes a las que no está suscrito. Todas estas recomendaciones son similares a las características que agregó a la regla de segmento. Desplácese hacia abajo para ver todos los rasgos recomendados.
1. (Opcional) Para excluir los rasgos de origen recomendados de ciertas fuentes de datos, haga clic en el símbolo **X** de las fuentes de datos que desee excluir.

   >[!NOTE]
   >
   >Las fuentes de datos excluidas se muestran justo encima de la lista de características recomendadas. Haga clic **X** en el cuadro gris para eliminar las exclusiones y ver los resultados de las fuentes de datos respectivas de nuevo.
1. Para añadir características recomendadas a la regla de segmento, haga clic en el símbolo **+**.

>[!IMPORTANT]
>
>Al agregar características [!UICONTROL Marketplace] a un segmento, las características solo se utilizan para la estimación de segmentos, hasta que se suscriba a la fuente de datos correspondiente. Las características que provienen de fuentes de datos a las que no está suscrito se marcan con un icono de carro de compras en la lista de características. Haga clic en el nombre de la característica para ir a la página de fuente de datos y suscribirse a ella.
>
>![marketplace-not subscribed](assets/trait-recommendations-marketplace.png)
>
>Puede guardar un segmento con características de terceros solo después de suscribirse a las fuentes de datos correspondientes.

### Segmentos existentes

1. Vaya a **[!UICONTROL Audience Data]>[!UICONTROL Segments]**, seleccione el segmento que desee editar y haga clic en ![Editar](assets/edit-button.png).
1. Desplácese hacia abajo hasta el cuadro desplegable [!UICONTROL Traits].
1. Puede ver características recomendadas, que son similares a las características que ya aparecen en la regla de segmento. Desplácese hacia abajo para ver todos los rasgos recomendados.
1. (Opcional) Para excluir los rasgos recomendados de ciertas fuentes de datos, haga clic en el símbolo **X** de las fuentes de datos que desee excluir.

   >[!NOTE]
   >
   >Las fuentes de datos excluidas se muestran justo encima de la lista de características recomendadas. Haga clic **X** en el cuadro gris para eliminar las exclusiones y ver los resultados de las fuentes de datos respectivas de nuevo.
1. Para añadir características recomendadas a la regla de segmento, haga clic en el símbolo **+**.

Cuando crea o edita un segmento y agrega un rasgo a la regla de segmento, verá un máximo de cincuenta rasgos recomendados, similares al que ha agregado. Si la regla de segmento contiene más de un rasgo, el Audience Manager utiliza un método de rotación para mostrar la mejor coincidencia para cada rasgo, luego la segunda mejor coincidencia para cada rasgo, y así sucesivamente, para los cincuenta rasgos más grandes por población, en la regla de segmento.

![Tres rasgos base](assets/three-base-traits.png)

Por ejemplo, cuando hay tres características en la regla de segmento, como se muestra a continuación, las características recomendadas son:

1. Mejor coincidencia para el rasgo 3 (el rasgo con la población más grande);
1. Mejor coincidencia para el rasgo 1;
1. Mejor coincidencia para el rasgo 2;
1. Segunda mejor coincidencia para el rasgo 3;
1. Segunda mejor coincidencia para el rasgo 1, y así sucesivamente hasta que llegue a los cincuenta rasgos.

Para obtener recomendaciones para un rasgo específico, puede hacer clic en los rasgos en la regla de segmento (1) o en la vista de rasgos recomendados (2).

![base-traits-example](assets/three-base-traits-numbered.png)

Al hacer clic en un rasgo de origen, se abre una ventana emergente, tal como se muestra en la imagen siguiente. Si las características recomendadas no forman parte del segmento, puede agregarlas al segmento pulsando **+**.

![añadir al segmento](assets/add_to_segments.png)

>[!TIP]
>
>Las fuentes de datos excluidas de la página principal se tienen en cuenta al generar recomendaciones dentro de la ventana emergente de información de características. Y, si excluye las fuentes de datos en esta vista, las exclusiones se aplican a la página principal.

>[!NOTE]
>
>Los rasgos recomendados pueden ser sus rasgos de origen o rasgos de terceros de fuentes de datos a las que está suscrito en [!UICONTROL Audience Marketplace].

## Cómo funciona

Para producir recomendaciones de características, el Audience Manager calcula la similitud [Jaccard](https://en.wikipedia.org/wiki/Jaccard_index) entre el rasgo objetivo y todos los demás rasgos a los que tiene acceso su cuenta, incluidos los datos de terceros. A continuación, el Audience Manager muestra hasta cincuenta rasgos que tienen la mayor similitud.

## Puntuación de similitud de rasgos {#trait-similarity-score}

El Audience Manager calcula el [!UICONTROL Trait Similarity Score] entre dos características calculando la intersección y la unión en términos del número de [!UICONTROL UUID]s y luego divida los dos. Para dos rasgos A y B, el cálculo tiene este aspecto:

![jaccard-similarity](assets/jaccard_similarity.png)

Consulte también los dos ejemplos siguientes.

### Ejemplo 1: Puntuación de similitud de rasgos baja

Dados dos rasgos A y B, supongamos que cada uno de los rasgos tiene una población de 1000 000 [!UICONTROL UUID]s, 25 000 [!UICONTROL UUID]s, de los cuales se califican para ambos rasgos.
Si se utiliza la fórmula anterior, el resultado será: 25.000 / 1.975.000 = 0,012. Este es un [!UICONTROL Trait Similarity Score] bajo, los dos rasgos son muy diferentes.

![trait-recommendations-low-overlap](assets/Trait-Recommendations-Low-overlap.png)

### Ejemplo 2: Puntuación de similitud de rasgos

Si los mismos rasgos A y B tenían 400 000 [!UICONTROL UUID]s que cumplen los dos rasgos, el [!UICONTROL Trait Similarity Score] es mucho mayor:
400.000 / 1.600.000 = 0,25

![trait-recommendations-high-overlap](assets/Trait-Recommendations-High-overlap.png)

### Interpretación de la puntuación de similitud de rasgos

Utilice la siguiente tabla como guía general para similitud de características. Esta guía se basa en las puntuaciones de similitud observadas en la mayoría de los rasgos.

| [!UICONTROL Trait Similarity Score] | Importancia |
|---------|----------|
| 0.1 y superiores | Alta similitud entre características |
| 0,03 - 0,1 | Similitud media entre características |
| 0,01 - 0,03 | Baja similitud entre características |
| 0 - 0,01 | Similitud muy baja entre características |

## Control de acceso basado en roles (RBAC)

Para las empresas que utilizan [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), debe tener permiso para crear y editar segmentos para ver las características recomendadas. Las recomendaciones de características que ve son solo aquellas de fuentes de datos a las que tiene acceso mediante [!UICONTROL RBAC].

>[!IMPORTANT]
>
>Para agregar [!UICONTROL Marketplace Recommendations] a un segmento, los usuarios deben suscribirse primero a las fuentes de datos correspondientes. Solo los usuarios con privilegios de administrador pueden suscribirse a las fuentes de datos [!UICONTROL Audience Marketplace].

Obtenga más información sobre [!UICONTROL RBAC] controles [aquí](../administration/administration-overview.md).

## Limitaciones

* Actualmente, el Audience Manager no muestra características de carpeta como características recomendadas. Obtenga más información sobre los rasgos de carpeta [aquí](../traits/manage-folder-traits.md).
* Al mostrar Trait Recommendations, el Audience Manager no tiene en cuenta los operadores [!DNL Boolean] ([!DNL AND], [!DNL OR], [!DNL NOT]) en las reglas de segmentos.
