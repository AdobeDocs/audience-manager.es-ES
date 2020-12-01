---
description: La página de detalles de una característica individual proporciona información general sobre el nombre de la característica, el ID, las métricas de rendimiento, las expresiones que definen la característica, los segmentos a los que pertenece y el registro de auditoría de características. Para ver estos detalles, vaya a Datos de Audiencia > Características y haga clic en el nombre de la característica con la que desee trabajar.
seo-description: La página de detalles de una característica individual proporciona información general sobre el nombre de la característica, el ID, las métricas de rendimiento, las expresiones que definen la característica, los segmentos a los que pertenece y el registro de auditoría de características. Para ver estos detalles, vaya a Datos de Audiencia > Características y haga clic en el nombre de la característica con la que desee trabajar.
seo-title: Página Detalles de rasgos
solution: Audience Manager
title: Página Detalles de rasgos
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 1%

---


# [!UICONTROL Trait] Página Detalles  {#trait-details-page}

La página de detalles de un [!UICONTROL trait] individual proporciona una visión general de los detalles [!UICONTROL trait], como el nombre [!UICONTROL trait], el ID, las métricas de rendimiento, las expresiones que definen el [!UICONTROL trait], los segmentos a los que pertenece y el registro de auditoría [!UICONTROL trait]. Para vista de estos detalles, vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** y haga clic en el nombre del [!UICONTROL trait] con el que desee trabajar.

## [!UICONTROL Trait] Herramientas de administración  {#trait-management-tools}

La parte superior de la página de detalles [!UICONTROL trait] aloja las herramientas que puede utilizar para administrar su [!UICONTROL traits]:

1. **[!UICONTROL Add New]**:: Utilice esta opción para crear nuevos  [!UICONTROL rule-based] [!UICONTROL algorithmic], o  [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]**:: Utilice esta opción para cambiar la configuración de la  [!UICONTROL trait].
3. **[!UICONTROL Delete]**:: Utilice esta opción para eliminar la cuenta actual  [!UICONTROL trait] de su cuenta de Audience Manager.
4. **[!UICONTROL Marketplace Recommendations]**:: Utilice esta opción  [!UICONTROL traits] para encontrar algo similar al que está viendo, a partir de las tarifas de  [!UICONTROL Audience Marketplace] datos a las que no está suscrito. Consulte [Audience Marketplace para Data Buyers](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) para obtener información sobre cómo navegar por [!UICONTROL Marketplace] y encontrar características similares.

![basic-trait-information](assets/basic-trait-information.png)

## [!UICONTROL Trait] Información {#basics}

La sección [!UICONTROL Trait Information] muestra detalles sobre los campos opcionales y requeridos que completó al generar el [!UICONTROL trait]. Esto incluye elementos como el tipo [!UICONTROL trait], el identificador [!UICONTROL trait], la descripción, [!UICONTROL data source] y otros metadatos. Estos detalles varían según el tipo [!UICONTROL trait] ([!UICONTROL folder], [!UICONTROL onboarded] o [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

El [!UICONTROL Trait Graph] proporciona métricas de rendimiento de un vistazo para el [!UICONTROL trait] seleccionado. Mantenga el cursor sobre una línea de tendencia para ver datos adicionales para el [!UICONTROL trait] seleccionado.

[!UICONTROL Unique Trait Realizations] representan un recuento de usuarios únicos que agregaron esto  [!UICONTROL trait] a su perfil en un intervalo de tiempo determinado. El [!UICONTROL Total Trait Population] indica el número de usuarios únicos que actualmente cumplen los requisitos para este [!UICONTROL trait].

Para [!UICONTROL rule-based traits], la calificación [!UICONTROL trait] se produce en tiempo real, ya que los usuarios cumplen los requisitos para [!UICONTROL trait] en su explorador.

Para [!UICONTROL onboarded traits], la calificación [!UICONTROL trait] se produce después de procesar un archivo de entrada, es decir, el archivo de entrada se [introduce en Audience Manager](../../faq/faq-inbound-data-ingestion.md) y es ahí cuando se produce la calificación [!UICONTROL trait].

El [!UICONTROL Trait Graph] muestra la siguiente información:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**:: seleccione esta opción para ver los resultados de  [!UICONTROL traits] los que recopilan datos para perfiles autenticados. Cuando selecciona esta opción, sólo ve los datos en el informe [!UICONTROL Cross-Device ID] y no habrá datos en el informe [!UICONTROL Device ID].
   * **[!UICONTROL Device ID]**:: seleccione esta opción para ver los resultados de  [!UICONTROL traits] los que recopilan datos para perfiles de dispositivos. Cuando selecciona esta opción, sólo ve los datos en el informe [!UICONTROL Device ID] y no habrá datos en el informe [!UICONTROL Cross-Device ID].

      ![gráfico de características](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**:: Recuento de usuarios únicos que agregaron esto  [!UICONTROL trait] a su perfil en un intervalo de tiempo determinado.
* **[!UICONTROL Total Trait Population]**:: El número de usuarios únicos cualificados actualmente para esto  [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**:: Las tres primeras entradas muestran los tres primeros  [!UICONTROL cross-device data sources] con el recuento de población más alto que se ha clasificado para el  [!UICONTROL trait], en orden descendente. La cuarta entrada muestra la suma de todos los demás [!DNL DPUUIDs] ([!DNL CRM IDs]) que califican para [!UICONTROL trait], de los [!UICONTROL cross-device data sources] que no están entre los tres primeros. Este informe aparece solamente si selecciona [!UICONTROL Cross-device ID] en el menú desplegable [!UICONTROL Show Results By] en la parte superior derecha de la página. La opción desplegable predeterminada es [!UICONTROL Device ID], donde no se muestra este informe.

   ![gráfico de características](assets/trait-identity.png)

   >[!NOTE]
   >
   >El Audience Manager sólo muestra el informe [!UICONTROL Identity Type Breakdown] si tiene [!UICONTROL cross-device] ID calificados para [!UICONTROL trait].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Expresión {#trait-expression}

La sección [!UICONTROL Trait Expression] le muestra los criterios que los usuarios deben cumplir para cumplir con los requisitos de [!UICONTROL trait]. Estas reglas se establecen cuando [crea o edita una característica](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait]Segmentos {#trait-segments}

La sección [!UICONTROL Segments with this Trait] lista todos los segmentos a los que pertenece el [!UICONTROL trait] seleccionado. Puede hacer clic en el nombre de un segmento para ver los detalles de dicho segmento.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Registro de auditoría e historial  {#trait-audit-history}

Para [!UICONTROL rule-based] y [!UICONTROL onboarded traits], el [!UICONTROL Trait Expression Change History] muestra los últimos 10 cambios realizados en las reglas de expresión [!UICONTROL trait] y quién los realizó. Si su [!UICONTROL trait] tiene más de 10 cambios, haga clic en **[!UICONTROL Export to CSV]** para descargar el registro de auditoría completo. El registro de auditoría no está disponible para [!UICONTROL folder] o [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] en la  [!UICONTROL By User] columna significa que la cuenta de ese usuario se ha eliminado.

![](assets/traitHistory.png)