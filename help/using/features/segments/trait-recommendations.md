---
description: Con Trait Recommendations, al crear o editar un segmento en Generador de segmentos, se obtienen recomendaciones sobre las características adicionales que puede incluir que son similares a las características de la regla de segmento. Añada las características recomendadas al segmento para aumentar la audiencia objetivo.
seo-description: Obtenga recomendaciones de rasgos en directo a medida que cree sus segmentos.
seo-title: Trait Recommendations
solution: Audience Manager
title: Trait Recommendations
uuid: null
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# Trait Recommendations

Obtenga recomendaciones de rasgos en directo a medida que cree sus segmentos.

## Demostración de vídeo

Comience por ver el vídeo de Recomendaciones de características y luego lea para obtener más información.

>[!VIDEO](https://video.tv.adobe.com/v/26228/?captions=spa)

## Información general

[!UICONTROL Trait Recommendations]equipado con [!DNL Adobe Sensei], incorpora la tecnología de datos en los flujos de trabajo diarios de Audience Manager.
With [!UICONTROL Trait Recommendations], when you build or edit a segment in [Segment Builder](segment-builder.md), you get recommendations on additional traits you can include, that are similar to the traits in the segment rule. Añada las características recomendadas al segmento para aumentar la audiencia objetivo.

![Información general sobre características de características](assets/trait-recommendations-overview.png)

**En forma nula:**

* Audience Manager muestra características individuales y características de terceros de las fuentes de datos suscritas actualmente como características recomendadas.
* Audience Manager muestra un máximo de cincuenta características similares a la de la regla de segmentos.
* Puede filtrar las fuentes de datos desde las cuales no desee ver ninguna recomendación.
* Al calcular similitudes, Audience Manager considera [los UUID](../../reference/ids-in-aam.md) que cumplen los requisitos de la característica durante los últimos 30 días.
* Si ve el mensaje de error "No se encontraron características similares". Las características pueden ser demasiado nuevas. ", esto significa que no había actividad para esa característica en los últimos 30 días, o que Audience Manager aún no ha actualizado las recomendaciones para esa característica. Inténtelo nuevamente en 24 horas.

## Casos de uso

Con [!UICONTROL Trait Recommendations], puede mejorar los flujos de trabajo según cómo utilice Audience Manager:

* Como especialista en mercadotecnia, puede encontrar rápidamente audiencias interesadas en productos complementarios con la ayuda de características similares para aumentar su alcance.
* Si usa Audience Manager como editor, puede [!UICONTROL Trait Recommendations]comprender el comportamiento de la audiencia y generar mejores segmentos para ventas publicitarias o adquisición de usuarios.

## Diferencias entre los modelos algorítmicos y recomendaciones de rasgos

### Modelos algorítmicos

[!UICONTROL Algorithmic Models] no sólo encuentra las características más influyentes sino que también puntua a los usuarios basándose en dichas características y asigna a cada usuario una puntuación individual. A continuación, cree características algorítmicas para dirigirse a los usuarios. Con los controles de precisión y alcance en [!UICONTROL Trait Builder], puede especificar qué usuarios entre todos los que tienen las características influyentes que desee segmentar.

[!UICONTROL Algorithmic Models] permite seleccionar usuarios en diferentes niveles de precisión y probar en [!UICONTROL Audience Lab] qué grupo de usuarios se convierten mejor. Consulte el caso de uso detallado en [Comparar modelos en Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

En [!UICONTROL Algorithmic Models], el modelo se ejecuta cada 8 días y actualiza los usuarios cualificados para características algorítmicas.

### Trait Recommendations

[!UICONTROL Trait Recommendations] es una forma rápida de obtener perspectivas sobre otras características que son similares a las que utiliza en un segmento.

Debe utilizar [!UICONTROL Trait Recommendations] cuando:

* Necesita perspectivas rápidas al generar un segmento;
* Utiliza los segmentos para campañas cortas o para eliminar rápidamente la audiencia que se convierte;
* Está intentando maximizar el alcance.

## Flujo de trabajo

Al crear o editar un segmento en el Generador [](segment-builder.md)de segmentos, puede explorar características similares a las características de la regla del segmento. El flujo de trabajo del Generador de segmentos es muy similar a los segmentos nuevos y existentes:

### Nuevos segmentos

1. En **Datos de audiencia &gt; Segmentos**, seleccione **Agregar nuevo**.
2. En la casilla desplegable **Características** , agregue al menos un rasgo a la regla del segmento.
3. Ahora puede ver características recomendadas que son similares a las características agregadas a la regla del segmento. Desplácese hacia abajo para ver todas las características recomendadas.
4. (Opcional) Para excluir las características recomendadas de ciertas fuentes de datos, haga clic en el símbolo **X** de las fuentes de datos que desee excluir.
   > [!NOTE]
   > 
   >Las fuentes de datos excluidas se muestran justo encima de la lista de características recomendadas. Pulse **X** en el cuadro gris para eliminar las exclusiones y ver de nuevo los resultados de las fuentes de datos correspondientes.
5. Para agregar características recomendadas a la regla de segmento, haga clic en el símbolo **+** .

### Segmentos existentes

1. Vaya **[!UICONTROL Audience Data]a &gt;[!UICONTROL Segments]**, seleccione el segmento que desee editar y pulse ![Editar](assets/edit-button.png).
1. Desplácese hacia abajo hasta el [!UICONTROL Traits] cuadro desplegable.
1. Puede ver características recomendadas, que son similares a las características que ya se encuentran en la regla de segmentos. Desplácese hacia abajo para ver todas las características recomendadas.
1. (Opcional) Para excluir las características recomendadas de ciertas fuentes de datos, haga clic en el símbolo **X** de las fuentes de datos que desee excluir.
   > [!NOTE]
   > 
   >Las fuentes de datos excluidas se muestran justo encima de la lista de características recomendadas. Pulse **X** en el cuadro gris para eliminar las exclusiones y ver de nuevo los resultados de las fuentes de datos correspondientes.
1. Para agregar características recomendadas a la regla de segmento, haga clic en el símbolo **+** .

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

Al hacer clic en una característica se abre una ventana emergente, como se muestra en la siguiente imagen. Si las características recomendadas no forman parte del segmento, puede agregarlas al segmento pulsando **+**.

![](assets/add_to_segments.png)

> [!TIP]
>
>Las fuentes de datos excluidas de la página principal se consideran al generar recomendaciones dentro de la ventana emergente de información de rasgos. Y, si excluye fuentes de datos en esta vista, las exclusiones se aplican a la página principal.

> [!NOTE]
>
> Las características recomendadas pueden ser características de origen o características de terceros de fuentes a las que se suscriba.

## Cómo funciona

Para producir recomendaciones de rasgos, Audience Manager calcula la [similitud de la tarjeta](https://en.wikipedia.org/wiki/Jaccard_index) entre el rasgo de destino y cualquier otra característica a la que tenga acceso su cuenta, incluidos los datos de terceros. Audience Manager muestra hasta cincuenta características que tienen la mayor similitud.

## Puntuación de similitud de características

Audience Manager calcula la [!UICONTROL Trait Similarity Score] entre dos características calculando la intersección y la unión en términos del número [!UICONTROL UUID]de s y dividiendo los dos. Para dos características A y B, el cálculo tiene este aspecto:

![](assets/jaccard_similarity.png)

Consulte también los dos ejemplos siguientes.

### Ejemplo 1 - Puntuación de similitud de rasgo baja

Dado dos características A y B, supongamos que cada una de las características tiene una población de 1000.000 [!UICONTROL UUID], 25.000 [!UICONTROL UUID]de las cuales cumplen ambas con ambas características.
Con la fórmula anterior, esto resultará en: 25.000/1.975.000 = 0,012. Esta es una baja [!UICONTROL Trait Similarity Score], las dos características son muy parecidas.

![](assets/Trait-Recommendations-Low-overlap.png)

### Ejemplo 2 - Puntuación de similitud de características

Si las mismas características A y B tenían 400 000 [!UICONTRL UUID]que cumplen ambas características, es [!UICONTROL Trait Similarity Score] mucho más alta:
400.000/1,600.000 = 0,25

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

Para las empresas que utilizan [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), debe tener permiso para crear y editar segmentos para ver características recomendadas. Y las características recomendadas que ve son sólo las de fuentes de datos a las que [!UICONTROL RBAC]tiene acceso. Obtenga más información sobre [!UICONTROL RBAC] los controles [aquí](../administration/administration-overview.md).

## Limitaciones

* Actualmente, Audience Manager no muestra características de carpeta como características recomendadas. Obtenga más información sobre características de carpetas [aquí](../traits/manage-folder-traits.md).
* Al mostrar Recomendaciones de características, Audience Manager no toma en cuenta [!DNL Boolean] los operadores ([!DNL AND], [!DNL OR][!DNL NOT]) en las reglas de segmentos.