---
description: Con Trait Recommendations, al crear o editar un segmento en Generador de segmentos, se obtienen recomendaciones sobre las características adicionales que puede incluir que son similares a las características de la regla de segmento. Añada las características recomendadas al segmento para aumentar la audiencia objetivo.
seo-description: Obtenga recomendaciones de características en directo a medida que genera sus segmentos.
seo-title: Recomendaciones de rasgos
solution: Audience Manager
title: Recomendaciones de rasgos
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1573'
ht-degree: 8%

---


# Recomendaciones de rasgos

Obtenga recomendaciones de características en directo a medida que genera sus segmentos, a partir de sus propias características de origen y [!UICONTROL Audience Marketplace] fuentes de datos.

## Demostración en video

Inicio viendo el video [!UICONTROL Trait Recommendations] a continuación, lea para obtener más información. La demostración de vídeo muestra cómo trabajar con recomendaciones de sus propias características personales, así como recomendaciones de características de fuentes de datos [!UICONTROL Audience Marketplace] a las que *ya está suscrito.*

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

El siguiente vídeo describe el flujo de trabajo de [!UICONTROL Marketplace Recommendations] y le muestra cómo agregar características a los segmentos, según las recomendaciones de fuentes de datos de [!UICONTROL Audience Marketplace]. Estas recomendaciones se basan en fuentes de datos a las que *no está suscrito*.

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## Información general

[!UICONTROL Trait Recommendations], con tecnología  [!DNL Adobe Sensei], incorpora la ciencia de datos a sus flujos de trabajo diarios Audience Manager.
Con [!UICONTROL Trait Recommendations], cuando genera o edita un segmento en [Generador de segmentos](segment-builder.md), obtiene recomendaciones sobre características adicionales que puede incluir, que son similares a las características de la regla de segmentos.

El Audience Manager muestra las recomendaciones de rasgos tanto desde las características individuales, en la sección **[!UICONTROL Recommendations]**, como desde **[!UICONTROL Audience Marketplace]**, en la sección **[!UICONTROL Recommendations from Marketplace]**.

Añada las características recomendadas al segmento para aumentar la audiencia objetivo.

![Información general sobre rasgos de Recommendations](assets/trait-recommendations-overview-full.png)

**En pocas palabras:**

* El Audience Manager muestra las características de origen en la sección [!UICONTROL Recommendations]. Las recomendaciones del mercado de fuentes públicas y privadas a las que no está suscrito están visibles en la sección [!UICONTROL Recommendations from Marketplace]. Haga clic en el nombre de la fuente para ir a [!UICONTROL Audience Marketplace] y suscribirse.
* El Audience Manager muestra un máximo de cincuenta características similares a la de la regla de segmento.
* Puede filtrar las fuentes de datos de las que no desee ver ninguna recomendación.
* Al calcular similitudes, el Audience Manager considera [UUID](../../reference/ids-in-aam.md) que cumplen los requisitos para la característica durante los últimos 30 días.
* Si ve el mensaje de error &quot;No se encontraron características similares. Las características pueden ser demasiado nuevas.&quot;, esto significa que o bien no hubo actividad para esa característica en los últimos 30 días, o bien el Audience Manager aún no ha actualizado las recomendaciones para esa característica. Inténtelo de nuevo en 24 horas.

## Casos de uso

Con [!UICONTROL Trait Recommendations], puede mejorar sus flujos de trabajo, dependiendo de cómo use el Audience Manager:

* Como especialista en mercadotecnia, puede encontrar rápidamente audiencias interesadas en productos complementarios con la ayuda de características similares, para aumentar su alcance.
* Si usa Audience Manager como editor, con [!UICONTROL Trait Recommendations] puede comprender el comportamiento de la audiencia y generar mejores segmentos para las ventas de publicidad o la adquisición de usuarios.
* Como comprador de datos [!UICONTROL Audience Marketplace], quiero descubrir datos relevantes de terceros sin explorar un gran número de fuentes.
* Como proveedor de datos [!UICONTROL Audience Marketplace], deseo recomendar datos relevantes a los compradores para que pueda beneficiarse de suscripciones óptimas y relevantes.

## Diferencias entre la característica Recommendations y los modelos algorítmicos

### Modelos algorítmicos

[!UICONTROL Algorithmic Models] no sólo encuentra las características más influyentes, sino que también puntúa a los usuarios en función de esas características y asigna a cada usuario una puntuación individual. Seguidamente, puede crear rasgos algorítmicos para segmentar los usuarios. Con los controles de precisión y alcance de [!UICONTROL Trait Builder], puede especificar qué usuarios de entre todos los que tienen las características influyentes que desea destinatario.

[!UICONTROL Algorithmic Models] le permite seleccionar usuarios en diferentes niveles de precisión y probar en  [!UICONTROL Audience Lab] qué grupo de usuarios se convierte mejor. Consulte el caso de uso detallado en [Comparar modelos en Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

En [!UICONTROL Algorithmic Models], el modelo se ejecuta cada 8 días y actualiza los usuarios calificados para características algorítmicas.

### Recomendaciones de rasgos

[!UICONTROL Trait Recommendations] es una forma rápida de obtener perspectivas sobre otras características similares a las que se utilizan en un segmento.

Debe utilizar [!UICONTROL Trait Recommendations] cuando:

* Necesita perspectivas rápidas cuando crea un segmento.
* Utiliza los segmentos para campañas cortas o cuando quiere suprimir rápidamente la audiencia que convierte.
* Está intentando maximizar el alcance.

## Flujo de trabajo

Al crear o editar un segmento en [Generador de segmentos](segment-builder.md), puede explorar características similares a las características de la regla de segmentos. El flujo de trabajo [Generador de segmentos](segment-builder.md) es muy similar para los segmentos nuevos y existentes:

### Nuevos segmentos

1. Vaya a **Datos de Audiencia > Segmentos** y haga clic en **Añadir nuevo**.
1. En el cuadro desplegable **Características**, agregue al menos una característica a la regla de segmento.
1. Puede ver las características recomendadas de origen y las [!UICONTROL Audience Marketplace] recomendaciones de características de las fuentes a las que está suscrito, en la sección **[!UICONTROL Recommendations]**. La sección **[!UICONTROL Recommendations from Marketplace]** muestra las recomendaciones de características de las fuentes a las que no está suscrito. Todas estas recomendaciones son similares a las características agregadas a la regla de segmento. Desplácese hacia abajo para ver todas las características recomendadas.
1. (Opcional) Para excluir las características de origen recomendadas de ciertas fuentes de datos, haga clic en el símbolo **X** de las fuentes de datos que desee excluir.

   >[!NOTE]
   >
   >Las fuentes de datos excluidas se muestran justo encima de la lista de las características recomendadas. Haga clic en **X** en el cuadro gris para eliminar las exclusiones y ver los resultados de las fuentes de datos respectivas de nuevo.
1. Para agregar características recomendadas a la regla de segmento, haga clic en el símbolo **+**.

>[!IMPORTANT]
>
>Al agregar características [!UICONTROL Marketplace] a un segmento, las características solo se utilizan para la estimación de segmentos, hasta que se suscriba a la fuente de datos correspondiente. Las características que provienen de fuentes de datos a las que no está suscrito se marcan con un icono de carro de compras en la lista de características. Haga clic en el nombre de la característica para ir a la página de fuentes de datos y suscribirse a ella.
>
>![mercado sin suscripción](assets/trait-recommendations-marketplace.png)
>
>Puede guardar un segmento con características de terceros solo después de suscribirse a las fuentes de datos correspondientes.

### Segmentos existentes

1. Vaya a **[!UICONTROL Audience Data]>[!UICONTROL Segments]**, seleccione el segmento que desee editar y haga clic en ![Editar](assets/edit-button.png).
1. Desplácese hacia abajo hasta el cuadro desplegable [!UICONTROL Traits].
1. Puede ver las características recomendadas, que son similares a las características que ya aparecen en la regla de segmento. Desplácese hacia abajo para ver todas las características recomendadas.
1. (Opcional) Para excluir las características recomendadas de ciertas fuentes de datos, haga clic en el símbolo **X** de las fuentes de datos que desee excluir.

   >[!NOTE]
   >
   >Las fuentes de datos excluidas se muestran justo encima de la lista de las características recomendadas. Haga clic en **X** en el cuadro gris para eliminar las exclusiones y ver los resultados de las fuentes de datos respectivas de nuevo.
1. Para agregar características recomendadas a la regla de segmento, haga clic en el símbolo **+**.

Cuando crea o edita un segmento y agrega una característica a la regla de segmento, verá un máximo de cincuenta características recomendadas, similares a la que ha agregado. Si la regla de segmento contiene más de una característica, el Audience Manager utiliza un método de rotación redonda para mostrar la mejor coincidencia para cada característica, luego la segunda mejor coincidencia para cada característica, y así sucesivamente, para las cincuenta características más grandes por población, en la regla de segmento.

![Tres características base](assets/three-base-traits.png)

Por ejemplo, cuando hay tres características en la regla de segmento, como se muestra a continuación, las características recomendadas son:

1. Mejor coincidencia para la característica 3 (la característica con la mayor población);
1. Mejor coincidencia para la característica 1;
1. Mejor coincidencia para la característica 2;
1. Segunda mejor coincidencia para la característica 3;
1. Segunda mejor coincidencia para el rasgo 1, y así sucesivamente hasta llegar a cincuenta rasgos.

Para obtener recomendaciones para una característica específica, puede hacer clic en las características en la regla de segmento (1) o en la vista de características recomendadas (2).

![base-traits-example](assets/three-base-traits-numbered.png)

Al hacer clic en una característica propia se abre una ventana emergente, como se muestra en la imagen de abajo. Si las características recomendadas no forman parte del segmento, puede agregarlas al segmento pulsando **+**.

![complemento al segmento](assets/add_to_segments.png)

>[!TIP]
>
>Las fuentes de datos excluidas de la página principal se tienen en cuenta al generar recomendaciones dentro de la ventana emergente de información de características. Y, si excluye las fuentes de datos de esta vista, las exclusiones se aplican a la página principal.

>[!NOTE]
>
>Las características recomendadas pueden ser sus características de origen o de terceros a partir de fuentes de datos a las que esté suscrito en [!UICONTROL Audience Marketplace].

## Cómo funciona

Para generar recomendaciones de características, el Audience Manager calcula la similitud [Jaccard](https://en.wikipedia.org/wiki/Jaccard_index) entre la característica de destinatario y cualquier otra característica a la que su cuenta tenga acceso, incluidos los datos de terceros. A continuación, el Audience Manager muestra hasta cincuenta características que tienen la mayor similitud.

## Puntuación de similitud de características {#trait-similarity-score}

El Audience Manager calcula el [!UICONTROL Trait Similarity Score] entre dos características calculando la intersección y la unión en términos del número de [!UICONTROL UUID]s y luego divide los dos. Para dos características A y B, el cálculo tiene este aspecto:

![similitud de jaccard](assets/jaccard_similarity.png)

Consulte también los dos ejemplos siguientes.

### Ejemplo 1: Puntuación de similitud de características bajas

Dadas las dos características A y B, digamos que cada una de las características tiene una población de 1.000.000 [!UICONTROL UUID]s, 25.000 [!UICONTROL UUID]s de los cuales califican para ambas características.
Si se utiliza la fórmula anterior, el resultado será: 25.000 / 1.975.000 = 0,012. Es un valor bajo [!UICONTROL Trait Similarity Score], las dos características son muy diferentes.

![trait-recommendations-low-superposición](assets/Trait-Recommendations-Low-overlap.png)

### Ejemplo 2: Puntuación de similitud de características

Si los mismos rasgos A y B tenían 400.000 [!UICONTROL UUID]s que cumplen los requisitos para ambas características, el [!UICONTROL Trait Similarity Score] es mucho mayor:
400.000 / 1.600.000 = 0,25

![trait-recommendations-high-superposición](assets/Trait-Recommendations-High-overlap.png)

### Cómo interpretar la puntuación de similitud de características

Utilice la siguiente tabla como guía general para la similitud de características. Esta guía se basa en las puntuaciones de similitud observadas en la mayoría de las características.

| [!UICONTROL Trait Similarity Score] | Importancia |
---------|----------|
| 0.1 y posterior | Gran similitud entre características |
| 0,03 - 0,1 | Similitud media entre características |
| 0,01 - 0,03 | Mínima similitud entre características |
| 0 - 0,01 | Muy baja similitud entre características |

## Control de acceso basado en roles (RBAC)

Para las compañías que utilizan [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), debe tener permiso para crear y editar segmentos para ver las características recomendadas. Las recomendaciones de características que ve son sólo las de los orígenes de datos a los que tiene acceso mediante [!UICONTROL RBAC].

>[!IMPORTANT]
>
>Para agregar [!UICONTROL Marketplace Recommendations] a un segmento, los usuarios deben suscribirse primero a las fuentes de datos correspondientes. Solo los usuarios con privilegios de administrador pueden suscribirse a [!UICONTROL Audience Marketplace] fuentes de datos.

Lea más acerca de los [!UICONTROL RBAC] controles [aquí](../administration/administration-overview.md).

## Limitaciones

* Actualmente, el Audience Manager no muestra las características de la carpeta como características recomendadas. Obtenga más información sobre las características de carpeta [aquí](../traits/manage-folder-traits.md).
* Al mostrar Recommendations de características, el Audience Manager no tiene en cuenta los operadores [!DNL Boolean] ([!DNL AND], [!DNL OR], [!DNL NOT]) en las reglas de segmentos.
