---
description: La página de detalles de un rasgo individual proporciona información general sobre el nombre del rasgo, el ID, las métricas de rendimiento, las expresiones que definen el rasgo, los segmentos a los que pertenece y el registro de auditoría de rasgos. Para ver estos detalles, vaya a Datos de audiencia > Rasgos y haga clic en el nombre del rasgo con el que desea trabajar.
seo-description: The details page for an individual trait provides overview of information like the trait name, ID, performance metrics, expressions that define the trait, segments it belongs to, and the trait audit log. To vew these details, go to Audience Data > Traits and click the name of the trait you want to work with.
seo-title: Trait Details Page
solution: Audience Manager
title: Página Detalles de rasgos
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: desglose de tipo de identidad, desglose de identidad, informes de identidad de audiencia, entre dispositivos, ID de varios dispositivos, ID de dispositivo
feature: Traits
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 0%

---

# [!UICONTROL Trait] Página de detalles {#trait-details-page}

La página de detalles de un individuo [!UICONTROL trait] ofrece información general sobre [!UICONTROL trait] detalles, como la [!UICONTROL trait] nombre, ID, métricas de rendimiento y expresiones que definen el [!UICONTROL trait], segmentos a los que pertenece y [!UICONTROL trait] registro de auditoría. Para ver estos detalles, vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** y haga clic en el nombre del [!UICONTROL trait] desea trabajar con.

## [!UICONTROL Trait] Herramientas de administración {#trait-management-tools}

La parte superior de la [!UICONTROL trait] página de detalles aloja las herramientas que puede utilizar para administrar sus [!UICONTROL traits]:

1. **[!UICONTROL Add New]**: utilice esta opción para crear nuevas [!UICONTROL rule-based], [!UICONTROL algorithmic], o [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]**: utilice esta opción para cambiar la configuración del actual [!UICONTROL trait].
3. **[!UICONTROL Delete]**: utilice esta opción para eliminar el actual [!UICONTROL trait] desde su cuenta de Audience Manager.
4. **[!UICONTROL Marketplace Recommendations]**: utilice esta opción para buscar elementos similares [!UICONTROL traits] a la que estás viendo, desde [!UICONTROL Audience Marketplace] tarifas de datos a las que no está suscrito. Consulte [Audience Marketplace para compradores de datos](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) para aprender a desplazarse por el [!UICONTROL Marketplace] y buscar rasgos similares.

![basic-trait-information](assets/basic-trait-information.png)

## [!UICONTROL Trait] Información {#basics}

El [!UICONTROL Trait Information] Esta sección muestra detalles sobre los campos obligatorios y opcionales que ha completado al crear el [!UICONTROL trait]. Esto incluye cosas como [!UICONTROL trait] tipo, [!UICONTROL trait] ID, descripción, [!UICONTROL data source]y otros metadatos. Estos detalles varían en función de [!UICONTROL trait] type ([!UICONTROL folder], [!UICONTROL onboarded], o [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

El [!UICONTROL Trait Graph] proporciona métricas de rendimiento de un vistazo para el [!UICONTROL trait]. Mantenga el cursor sobre una línea de tendencia para ver datos adicionales del [!UICONTROL trait].

[!UICONTROL Unique Trait Realizations] representan un recuento de usuarios únicos que agregaron esto [!UICONTROL trait] a su perfil durante el intervalo de tiempo dado. El [!UICONTROL Total Trait Population] indica el número de usuarios únicos cualificados actualmente para esto [!UICONTROL trait].

Para [!UICONTROL rule-based traits], [!UICONTROL trait] La calificación de se produce en tiempo real, ya que los usuarios cumplen los requisitos para una [!UICONTROL trait] en su explorador.

Para [!UICONTROL onboarded traits], [!UICONTROL trait] la calificación se produce después de procesar un archivo entrante, es decir, cuando el archivo entrante es [introducido en el Audience Manager](../../faq/faq-inbound-data-ingestion.md) y es entonces cuando el [!UICONTROL trait] la calificación se produce.

El [!UICONTROL Trait Graph] muestra la siguiente información:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: seleccione esta opción para ver los resultados de [!UICONTROL traits] que recopilan datos para perfiles autenticados. Al seleccionar esta opción, solo se ven datos en la [!UICONTROL Cross-Device ID] informe, y no habrá datos presentes en el [!UICONTROL Device ID] informe.
   * **[!UICONTROL Device ID]**: seleccione esta opción para ver los resultados de [!UICONTROL traits] que recopilan datos para perfiles de dispositivos. Al seleccionar esta opción, solo se ven datos en la [!UICONTROL Device ID] informe, y no habrá datos presentes en el [!UICONTROL Cross-Device ID] informe.

      ![gráfico de rasgos](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: un recuento de usuarios únicos que agregaron esto [!UICONTROL trait] a su perfil durante el intervalo de tiempo dado.
* **[!UICONTROL Total Trait Population]**: el número de usuarios únicos cualificados actualmente para esto [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**: las tres primeras entradas muestran las tres principales [!UICONTROL cross-device data sources] con el recuento de población más alto que cumplen los requisitos para la [!UICONTROL trait], en orden descendente. La cuarta entrada muestra la suma de todas las demás [!DNL DPUUIDs] ([!DNL CRM IDs]) que cumplen los requisitos para la [!UICONTROL trait], desde el [!UICONTROL cross-device data sources] que no están entre los tres primeros. Este informe solo aparece si selecciona [!UICONTROL Cross-device ID] en el [!UICONTROL Show Results By] menú desplegable en la parte superior derecha de la página. La opción desplegable predeterminada es [!UICONTROL Device ID], donde no se muestra este informe.

   ![gráfico de rasgos](assets/trait-identity.png)

   >[!NOTE]
   >
   >El Audience Manager solo muestra la variable [!UICONTROL Identity Type Breakdown] informar si tiene [!UICONTROL cross-device] ID cualificados para [!UICONTROL trait].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Expresión {#trait-expression}

El [!UICONTROL Trait Expression] Esta sección muestra los criterios que los usuarios deben cumplir para poder optar a la [!UICONTROL trait]. Estas reglas se establecen cuando [crear o editar una característica](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait]Segmentos  {#trait-segments}

El [!UICONTROL Segments with this Trait] enumera todos los segmentos seleccionados [!UICONTROL trait] pertenece a. Puede hacer clic en un nombre de segmento para ver detalles sobre ese segmento.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Registro de auditoría/historial {#trait-audit-history}

Para [!UICONTROL rule-based] y [!UICONTROL onboarded traits], el [!UICONTROL Trait Expression Change History] muestra los últimos 10 cambios realizados en [!UICONTROL trait] reglas de expresión y quién las creó. Si su [!UICONTROL trait] tiene más de 10 cambios, haga clic en **[!UICONTROL Export to CSV]** para descargar todo el registro de auditoría. El registro de auditoría no está disponible para [!UICONTROL folder] o [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] en el [!UICONTROL By User] columna significa que se ha eliminado la cuenta de ese usuario.

![](assets/traitHistory.png)
