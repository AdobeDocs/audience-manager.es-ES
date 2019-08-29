---
description: La página de detalles de una característica individual proporciona información general sobre información como el nombre de característica, el ID, las métricas de rendimiento, las expresiones que definen el rasgo, los segmentos a los que pertenece y el registro de auditoría de características. Para examinar estos detalles, vaya a Datos de audiencia > Características y haga clic en el nombre de la característica con la que desee trabajar.
seo-description: La página de detalles de una característica individual proporciona información general sobre información como el nombre de característica, el ID, las métricas de rendimiento, las expresiones que definen el rasgo, los segmentos a los que pertenece y el registro de auditoría de características. Para examinar estos detalles, vaya a Datos de audiencia > Características y haga clic en el nombre de la característica con la que desee trabajar.
seo-title: Página Detalles de características
solution: Audience Manager
title: Página Detalles de características
uuid: 23301376-c 1 cc -4778-b 8 c 4-9831 f 6739 db 9
translation-type: tm+mt
source-git-commit: 3130882116d39e94b446679999144f1eb55edc77

---


# Página Detalles de características {#trait-details-page}

La página de detalles de una característica individual proporciona información general sobre información como el nombre de característica, el ID, las métricas de rendimiento, las expresiones que definen el rasgo, los segmentos a los que pertenece y el registro de auditoría de características. Para examinar estos detalles, vaya a [!UICONTROL Audience Data > Traits] y haga clic en el nombre de la característica con la que desee trabajar.

## Información básica {#basics}

La [!UICONTROL Basic Information] sección muestra detalles sobre los campos opcionales y requeridos que ha completado al crear la característica. Esto incluye el tipo de característica, el ID de características, la descripción, la fuente de datos y otros metadatos. Estos detalles varían según el tipo de característica (carpeta, infiltrado o basado en reglas).

![](assets/basicInfo.png)

## Gráfico de características {#trait-graph}

[!UICONTROL Trait Graph] Proporciona métricas de rendimiento de vistazo para el rasgo seleccionado. Mantenga el cursor sobre una línea de tendencias para ver datos adicionales para el rasgo seleccionado.

[!UICONTROL Unique Trait Realizations] representan un recuento de usuarios únicos que han agregado esta característica a su perfil durante un intervalo de tiempo determinado. [!UICONTROL Total Trait Population] Indica el número de usuarios únicos que están actualmente cualificados para esta característica.

* Para las características basadas en reglas, la cualificación de características se produce en tiempo real, ya que los usuarios cumplen los requisitos de un rasgo en el navegador.
* Para características integradas, la cualificación de características se produce después de procesar un archivo entrante, es decir, el archivo entrante [se alimenta en Audience Manager](../../faq/faq-inbound-data-ingestion.md) y es cuando se produce la cualificación de características.
* **[!UICONTROL Unique Trait Realizations]**: Recuento de usuarios únicos que agregaron esta característica a su perfil durante un intervalo de tiempo determinado.
* **[!UICONTROL Total Trait Population]**: Número de usuarios únicos que actualmente están cualificados para esta característica.

   ![trait-graph](assets/trait-summary.png)

* **[!UICONTROL Identity Type Breakdown]**: Las tres primeras entradas muestran las tres fuentes de datos entre dispositivos principales con el recuento de población más alto que se califica para el rasgo, en orden descendente. La cuarta entrada muestra la suma de todos los demás [!DNL DPUUIDs] ([!DNL CRM IDs]) que califican para la característica, de las fuentes de datos entre dispositivos que no están en los tres primeros. Este informe aparece únicamente si selecciona ID entre dispositivos en el menú [!UICONTROL Show Results By] desplegable en la parte superior derecha de la página. La [!UICONTROL Device ID]opción desplegable predeterminada es, donde no se muestra este informe.

   ![trait-graph](assets/trait-identity.png)
   > [!NOTE]
   > Audience Manager solo muestra el [!UICONTROL Identity Type Breakdown] informe si tiene ID entre dispositivos cualificado para la característica.

## Expresión de rasgos {#trait-expression}

La [!UICONTROL Trait Expression] sección muestra los criterios que los usuarios deben cumplir para cumplir con la característica. Estas reglas se establecen al [crear o editar un rasgo](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## Segmentos de características {#trait-segments}

La [!UICONTROL Segments with this Trait] sección enumera todos los segmentos a los que pertenece el rasgo seleccionado. Puede hacer clic en un nombre de segmento para ver los detalles de ese segmento.

![](assets/traitSegments.png)

## Registro de características/auditoría de características {#trait-audit-history}

Para características basadas en reglas e integradas, los [!UICONTROL Trait Expression Change History] últimos 10 cambios realizados en las reglas de expresión de características y los que han realizado. Si su característica tiene más de 10 cambios, haga clic **[!UICONTROL Export to CSV]** en para descargar el registro de auditoría completo. El registro de auditoría no está disponible para características de carpeta o algoritmos.

>[!NOTE]
>
>[!UICONTROL Not Available] en [!UICONTROL By User] la columna significa que se ha eliminado la cuenta de ese usuario.

![](assets/traitHistory.png)