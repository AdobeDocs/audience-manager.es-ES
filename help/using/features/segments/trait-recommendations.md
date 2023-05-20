---
description: Con Trait Recommendations, al crear o editar un segmento en Generador de segmentos, se obtienen recomendaciones sobre las características adicionales que puede incluir que son similares a las características de la regla de segmento. Añada las características recomendadas al segmento para aumentar la audiencia objetivo.
seo-description: Get live trait recommendations as you build your segments.
seo-title: Trait Recommendations
solution: Audience Manager
title: Recomendaciones de rasgos
feature: Segments
exl-id: 7ef862a9-7354-49fb-9af0-925d827a5165
source-git-commit: 432b12c4d4fb567d1a0bcaa9d12baaac5e3ae0f7
workflow-type: tm+mt
source-wordcount: '1562'
ht-degree: 8%

---

# Recomendaciones de rasgos

Obtenga recomendaciones de características activas a medida que crea sus segmentos, a partir de sus propias características de origen, y [!UICONTROL Audience Marketplace] fuentes de datos.

## Demostración en vídeo

Comience por ver la [!UICONTROL Trait Recommendations] A continuación, siga leyendo para obtener más información. La demostración de vídeo le muestra cómo trabajar con recomendaciones de sus propias características de origen, así como con recomendaciones de características de [!UICONTROL Audience Marketplace] fuentes de datos que *ya está suscrito a*.

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

El siguiente vídeo describe el flujo de trabajo de [!UICONTROL Marketplace Recommendations], mostrándole cómo añadir características a los segmentos, en función de las recomendaciones de fuentes de datos en [!UICONTROL Audience Marketplace]. Estas recomendaciones se basan en fuentes de datos que *no está suscrito a*.

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## Información general

[!UICONTROL Trait Recommendations], con tecnología [!DNL Adobe Sensei], incorpora la ciencia de datos en los flujos de trabajo diarios del Audience Manager.
Con [!UICONTROL Trait Recommendations], cuando genere o edite un segmento en [Generador de segmentos](segment-builder.md)Además, obtiene recomendaciones sobre características adicionales que puede incluir, que son similares a las características de la regla de segmento.

El Audience Manager le muestra recomendaciones de rasgos tanto de sus rasgos de origen, como de **[!UICONTROL Recommendations]** y de **[!UICONTROL Audience Marketplace]**, en el **[!UICONTROL Recommendations from Marketplace]** sección.

Añada las características recomendadas al segmento para aumentar la audiencia objetivo.

![Información general sobre Trait Recommendations](assets/trait-recommendations-overview-full.png)

**En pocas palabras:**

* El Audience Manager muestra rasgos de origen en [!UICONTROL Recommendations] sección. Las recomendaciones de Marketplace de fuentes públicas y privadas a las que no está suscrito son visibles en [!UICONTROL Recommendations from Marketplace] sección. Pulse el nombre de la fuente para ir a [!UICONTROL Audience Marketplace] y suscribirse.
* El Audience Manager muestra un máximo de cincuenta rasgos similares al de la regla del segmento.
* Puede filtrar las fuentes de datos de las que no desea ver ninguna recomendación.
* Al calcular las similitudes, el Audience Manager considera lo siguiente [UUID](../../reference/ids-in-aam.md) que cumplen los requisitos para el rasgo durante los últimos 30 días.
* Si ve el mensaje de error &quot;No se han encontrado rasgos similares. Rasgos puede ser demasiado nuevo&quot;. Esto significa que, o bien no ha habido actividad para ese rasgo en los últimos 30 días o el Audience Manager aún no ha actualizado las recomendaciones para ese rasgo. Inténtelo de nuevo en 24 horas.

## Casos de uso

Con [!UICONTROL Trait Recommendations], puede mejorar los flujos de trabajo en función de cómo utilice Audience Manager:

* Como experto en marketing, puede encontrar rápidamente audiencias interesadas en productos complementarios con la ayuda de características similares, para que pueda aumentar su alcance.
* Si usa Audience Manager como editor, con [!UICONTROL Trait Recommendations]Además, puede comprender el comportamiento de la audiencia y generar mejores segmentos para las ventas de publicidad o la adquisición de usuarios.
* Como un [!UICONTROL Audience Marketplace] comprador de datos, quiero descubrir datos de terceros relevantes sin navegar a través de un gran número de fuentes.
* Como un [!UICONTROL Audience Marketplace] proveedor de datos, quiero recomendar datos relevantes a los compradores para que pueda beneficiarse de suscripciones óptimas y relevantes.

## Diferencias entre modelos algorítmicos y Recommendations de rasgos

### Modelos algorítmicos

[!UICONTROL Algorithmic Models] no solo encuentra los rasgos más influyentes, sino que también puntúa a los usuarios según esos rasgos y asigna a cada usuario una puntuación individual. Seguidamente, puede crear rasgos algorítmicos para segmentar los usuarios. Con controles de precisión y alcance en la [!UICONTROL Trait Builder], puede especificar a qué usuarios quiere dirigirse de entre todos los que tienen los rasgos influyentes.

[!UICONTROL Algorithmic Models] permite seleccionar usuarios en diferentes niveles de precisión y realizar pruebas en [!UICONTROL Audience Lab] qué grupo de usuarios se convierte mejor. Consulte el caso de uso detallado en [Comparar modelos en Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

Entrada [!UICONTROL Algorithmic Models], el modelo se ejecuta cada 8 días y actualiza los usuarios clasificados para rasgos algorítmicos.

### Recomendaciones de rasgos

[!UICONTROL Trait Recommendations] es una forma rápida de obtener perspectivas sobre otros rasgos similares a los que utiliza en un segmento.

Debe utilizar [!UICONTROL Trait Recommendations] cuando:

* Necesita perspectivas rápidas cuando crea un segmento.
* Utiliza los segmentos para campañas cortas o cuando quiere suprimir rápidamente la audiencia que convierte.
* Está intentando maximizar el alcance.

## Flujo de trabajo

Al crear o editar un segmento en [Generador de segmentos](segment-builder.md), puede explorar características similares a las de la regla del segmento. El [Generador de segmentos](segment-builder.md) el flujo de trabajo es muy similar para los segmentos nuevos y existentes:

### Nuevos segmentos

1. Ir a **Datos de audiencia > Segmentos** y haga clic en **Añadir nuevo**.
1. En el **Características** , añada al menos una característica a la regla de segmento.
1. Puede ver las características recomendadas de origen y [!UICONTROL Audience Marketplace] recomendaciones de características de fuentes a las que está suscrito, en la **[!UICONTROL Recommendations]** sección. El **[!UICONTROL Recommendations from Marketplace]** Esta sección muestra las recomendaciones de características de fuentes a las que no está suscrito. Todas estas recomendaciones son similares a los rasgos agregados a la regla de segmento. Desplácese hacia abajo para ver todos los rasgos recomendados.
1. (Opcional) Para excluir los rasgos de origen recomendados de ciertas fuentes de datos, haga clic en **X** símbolo para las fuentes de datos que desea excluir.

   >[!NOTE]
   >
   >Las fuentes de datos excluidas se muestran justo encima de la lista de características recomendadas. Clic **X** en el cuadro gris para eliminar las exclusiones y volver a ver los resultados de las fuentes de datos correspondientes.
1. Para añadir características recomendadas a la regla de segmento, haga clic en **+** símbolo.

>[!IMPORTANT]
>
>Al añadir [!UICONTROL Marketplace] rasgos de un segmento, los rasgos solo se utilizan para la estimación de segmentos, hasta que se suscriba a la fuente de datos correspondiente. Las características de fuentes de datos a las que no está suscrito se marcan con un icono del carro de compras en la lista de características. Haga clic en el nombre del rasgo para ir a la página de fuente de datos y suscribirse a ella.
>
>![marketplace-not-subscribed](assets/trait-recommendations-marketplace.png)
>
>Solo puede guardar segmentos con características de terceros una vez que se haya suscrito a las fuentes de datos correspondientes.

### Segmentos existentes

1. Ir a **[!UICONTROL Audience Data]>[!UICONTROL Segments]**, seleccione el segmento que desee editar y haga clic en ![Editar](assets/edit-button.png).
1. Desplácese hacia abajo hasta el [!UICONTROL Traits] cuadro desplegable.
1. Puede ver características recomendadas, que son similares a las características que ya se encuentran en la regla de segmento. Desplácese hacia abajo para ver todos los rasgos recomendados.
1. (Opcional) Para excluir los rasgos recomendados de ciertas fuentes de datos, haga clic en **X** símbolo para las fuentes de datos que desea excluir.

   >[!NOTE]
   >
   >Las fuentes de datos excluidas se muestran justo encima de la lista de características recomendadas. Clic **X** en el cuadro gris para eliminar las exclusiones y volver a ver los resultados de las fuentes de datos correspondientes.
1. Para añadir características recomendadas a la regla de segmento, haga clic en **+** símbolo.

Cuando crea o edita un segmento y agrega una característica a la regla del segmento, ve un máximo de cincuenta características recomendadas, similares a la que ha agregado. Si la regla del segmento contiene más de un rasgo, Audience Manager utiliza un método de round robin para mostrar la mejor coincidencia para cada rasgo, la segunda mejor coincidencia para cada rasgo y así sucesivamente, para los cincuenta rasgos más grandes por población, en la regla del segmento.

![Tres rasgos básicos](assets/three-base-traits.png)

Por ejemplo, cuando hay tres rasgos en la regla del segmento, como se muestra a continuación, los rasgos recomendados son:

1. Mejor coincidencia para el rasgo 3 (el rasgo con la población más grande);
1. Mejor coincidencia para el rasgo 1;
1. Mejor coincidencia para el rasgo 2;
1. Segunda mejor coincidencia para el rasgo 3;
1. La segunda mejor coincidencia para el rasgo 1, y así sucesivamente hasta que llegue a cincuenta rasgos.

Para obtener recomendaciones para un rasgo específico, puede hacer clic en los rasgos en la regla del segmento (1) o en la vista de rasgos recomendados (2).

![base-traits-example](assets/three-base-traits-numbered.png)

Al hacer clic en una característica de origen, se abre una ventana emergente, como se muestra en la siguiente imagen. Si los rasgos recomendados no forman parte del segmento, puede añadirlos al segmento pulsando **+**.

![añadir a segmento](assets/add_to_segments.png)

>[!TIP]
>
>Las fuentes de datos excluidas de la página principal se tienen en cuenta al generar recomendaciones en la ventana emergente de información de características. Y, si excluye las fuentes de datos en esta vista, las exclusiones se aplican a la página principal.

>[!NOTE]
>
>Las características recomendadas pueden ser características de origen o de terceros de fuentes de datos a las que está suscrito en [!UICONTROL Audience Marketplace].

## Cómo funciona

Para generar recomendaciones de rasgos, el Audience Manager calcula el [Similitud de Jaccard](https://en.wikipedia.org/wiki/Jaccard_index) entre el rasgo objetivo y todos los demás rasgos a los que su cuenta tiene acceso, incluidos los datos de terceros. A continuación, el Audience Manager muestra hasta cincuenta rasgos que tienen la similitud más alta.

## Puntuación de similitud de rasgos {#trait-similarity-score}

Audience Manager calcula el [!UICONTROL Trait Similarity Score] entre dos rasgos calculando la intersección y la unión en términos del número de [!UICONTROL UUID]s y luego divide los dos. Para dos rasgos A y B, el cálculo tiene este aspecto:

![jaccard-similarity](assets/jaccard_similarity.png)

Véanse también los dos ejemplos siguientes.

### Ejemplo 1: Puntuación de similitud de rasgo baja

Dados dos rasgos A y B, supongamos que cada uno de los rasgos tiene una población de 1 000 000 [!UICONTROL UUID]s, 25.000 [!UICONTROL UUID]de los cuales cumplen los requisitos para ambos rasgos.
Utilizando la fórmula anterior, esto resultará en: 25 000 / 1 975 000 = 0,012. Esto es bajo [!UICONTROL Trait Similarity Score]Sin embargo, los dos rasgos son muy diferentes.

![recomendación de rasgos-baja-superposición](assets/Trait-Recommendations-Low-overlap.png)

### Ejemplo 2: Puntuación de similitud de rasgos

Si los mismos rasgos A y B tenían 400.000 [!UICONTROL UUID]Para que cumplan los requisitos de ambos rasgos, la variable [!UICONTROL Trait Similarity Score] es mucho más alto: 400 000 / 1 600 000 = 0,25

![rasgos-recomendaciones-alto-solapamiento](assets/Trait-Recommendations-High-overlap.png)

### Interpretación de la puntuación de similitud de rasgos

Utilice la siguiente tabla como guía aproximada para comprobar la similitud de rasgos. Esta guía se basa en las puntuaciones de similitud observadas en la mayoría de los rasgos.

| [!UICONTROL Trait Similarity Score] | Importancia |
|---------|----------|
| 0.1 y superior | Alta similitud entre rasgos |
| 0.03 - 0.1 | Semejanza media entre rasgos |
| 0.01 - 0.03 | Baja similitud entre rasgos |
| 0 - 0.01 | Muy baja similitud entre rasgos |

## Control de acceso basado en roles (RBAC)

Para empresas que utilizan [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), debe tener permiso para crear y editar segmentos para ver las características recomendadas. Las recomendaciones de rasgos que ve solo son las de las fuentes de datos a las que tiene acceso a través de [!UICONTROL RBAC].

>[!IMPORTANT]
>
>Para agregar [!UICONTROL Marketplace Recommendations] Para acceder a un segmento, los usuarios deben suscribirse primero a las fuentes de datos correspondientes. Solo los usuarios con privilegios de administrador pueden suscribirse a [!UICONTROL Audience Marketplace] fuentes de datos.

Más información sobre [!UICONTROL RBAC] controles [aquí](../administration/administration-overview.md).

## Limitaciones

* Actualmente, Audience Manager no muestra las características de carpeta como características recomendadas. Más información sobre las características de carpeta [aquí](../traits/manage-folder-traits.md).
* Al mostrar la característica Recommendations, el Audience Manager no tiene en cuenta lo siguiente [!DNL Boolean] operadores ([!DNL AND], [!DNL OR], [!DNL NOT]) en las reglas de segmentos.
