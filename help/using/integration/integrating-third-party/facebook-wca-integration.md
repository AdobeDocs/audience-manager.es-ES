---
description: Esta página ilustra el proceso de creación de píxeles de Audiencias personalizadas del sitio web de Facebook (WCA) para el envío de segmentos de audiencia de Audience Manager basados en web a Facebook, para la segmentación de anuncios en línea con una transparencia mejorada.
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Integración de WCA de Facebook
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 8780083474d68717fe3bd4dc632d96da89929122
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!DNL Facebook WCA] de CRM {#facebook-wca-integration}

Esta página ilustra el proceso de creación [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) píxeles para enviar datos basados en web [!DNL Audience Manager] segmentos de audiencia a [!DNL Facebook], para la segmentación de anuncios en línea con una transparencia mejorada.

## Información general {#overview}

[Audiencias personalizadas del sitio web de facebook (WCA)](https://www.facebook.com/business/help/610516375684216?id=2469097953376494) permite crear una lista de personas que han visitado determinadas páginas o que han realizado acciones concretas en el sitio web. [!DNL Audience Manager] habilita la activación en [!DNL WCA] using [!DNL URL] destinos, con los que puede configurar una integración personalizada basada en píxeles para enviar audiencias basadas en web a [!DNL Facebook] para la segmentación.

![Integración de WCA de Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Esta capacidad requiere que seleccione la variable [!UICONTROL Website] opción audiencia para plataformas sociales en [Destinos de URL](/help/using/features/destinations/create-url-destination.md). Las plataformas sociales requieren que la información del referente se desenmascara cuando se envía a su plataforma. Tenga en cuenta que esto significa que la plataforma/socio de destino podrá ver la información en el referente [!DNL URL].

## Requisitos previos {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segmentos, listos para asignar a los nuevos [!DNL Facebook] destino. Aquí está [cómo crear un segmento](/help/using/features/segments/segment-builder.md) en el [!DNL Audience Manager] IU.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Versión 4.1.0 o posterior. Descargue la versión más reciente **[aquí](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) versión 9.0 o posterior, descargable desde **[here](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Alternativamente, si usa [Reenvío del lado del servidor (SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) para importar datos en [!DNL Audience Manager], debe utilizar la versión 2.12 o posterior de AppMeasurement. Descargar [!DNL AppMeasurement] usando la variable [Administrador de códigos de Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).

Le recomendamos que instale o actualice las bibliotecas en los pasos 3 y 4 mediante [Etiquetas de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

## Paso 1: Creación de un [!UICONTROL Facebook Destination] en [!DNL Audience Manager] {#step-1-create-facebook-destination}

Cree una nueva [!UICONTROL URL Destination] en [!DNL Audience Manager] y asígnele un nombre [!DNL Facebook Website Custom Audiences]. Utilice la configuración siguiente al crear el destino. También puede consultar la [Configuración de un destino de URL](/help/using/features/destinations/create-url-destination.md) página.

### Información básica

* **[!UICONTROL Category]**: Personalizado
* **[!UICONTROL Type]**: [!DNL URL]
* Seleccione el **[!UICONTROL Auto-fill Destination Mapping]** casilla de verificación y, a continuación, seleccione **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Seleccione la opción **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Esta etiqueta de exportación evita que los datos de terceros y los datos derivados de gráficos de dispositivos se incluyan en los segmentos.

### Configuración

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. Seleccionando esta [!UICONTROL URL Type] , [!DNL Audience Manager] no oscurece al referente [!DNL URL] información al activar un [!DNL Facebook WCA] píxel.
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* En el **[!UICONTROL Base URL]** y **[!UICONTROL Secure URL]** , introduzca la variable [!DNL Facebook WCA] píxel.
* **[!UICONTROL Delimiter]**: `,`

Base [!DNL URL] ejemplo: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Ejemplo de píxel activado desde la página. Este ejemplo muestra un usuario que cumple los requisitos para tres [!DNL Audience Manager] segmentos, con los ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parámetro | Descripción |
|---------|----------|
| `id` | Su [!DNL Facebook] ID de píxel, que puede encontrar en la variable [!DNL Facebook Ad Manager] interfaz de usuario al crear píxeles de audiencia. |
| `ev` | Event.     Este es un valor arbitrario que aparecerá en la variable [!DNL Facebook Ad Manager] una vez que el píxel empieza a activarse en el sitio. Consulte la [!UICONTROL Include] elemento en [Paso 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), para obtener más información. |
| `cd[segID]` | Un parámetro adicional, que empezará a rellenarse en la variable [!DNL Facebook Ad Manager] una vez que el píxel empieza a activarse en el sitio. `segID` también es arbitrario. |
| `%ALIAS%` | Un [!DNL Audience Manager] macro, que se reemplazará dinámicamente por la variable [!DNL Audience Manager] [!UICONTROL segment] ID para los que el visitante del sitio es apto, delimitados por coma , |

Su [!UICONTROL URL destination] la configuración debe ser similar a la de la siguiente imagen:

![Configuración del destino](/help/using/integration/assets/facebook-wca.png)

Guarde el [!UICONTROL destination]. A continuación, puede continuar con el **Asignaciones de segmentos** paso a paso.

## Paso 2: Asignaciones de segmentos: Asignación de segmentos al destino {#step-2-segment-mappings}

En el [Configurar destino de URL](/help/using/features/destinations/create-url-destination.md) flujo de trabajo, asigne el segmento aplicable a su segmento recién creado [!UICONTROL destination]. Observe que el valor de asignación se rellena automáticamente con la variable [!DNL Audience Manager] [!UICONTROL segment ID].

Introduzca una fecha de finalización si corresponde; de lo contrario, deje en blanco sin fecha de finalización.

## Paso 3: Creación de un [!UICONTROL Audience] en [!DNL Facebook Ads Manager] {#step-3-create-audience}

Consulte [Crear una audiencia personalizada de sitio web](https://www.facebook.com/business/help/666509013483225) en el [!DNL Facebook] documentación de ayuda. Seleccione el [!UICONTROL Create Audience] opciones de la tabla siguiente:

| Elemento | Descripción |
|---------|----------|
| Tráfico del sitio web | Combinación personalizada |
| Inclusión | <ul><li>Select **[!UICONTROL Event]** > Seleccionar **[!UICONTROL Adobe-Audience-Manager-Segment]**. Este era el valor de la variable `ev` en el píxel de ejemplo del paso 1. Tenga en cuenta que si el píxel aún no se ha activado, la variable **[!UICONTROL Event]** o **[!UICONTROL Adobe-Audience-Manager-Segment]** puede no aparecer en el [!DNL Facebook] interfaz de usuario.</li><li>Añada un parámetro: Select `segID`.</li><li><p>Seleccione el **contains** operador.</p><p>Esto es importante, teniendo en cuenta que los visitantes pueden cumplir los requisitos para pertenecer a varios segmentos, es posible que haya varios [!UICONTROL segment IDs] en el parámetro de píxel. Uso de es igual a (`=`) puede que no clasifique a los visitantes para la audiencia y que observe un volumen menor.</p></li><li>Agregue un valor: Introduzca la variable [!DNL Audience Manager] ID de segmento.</li></ul> |
| Agregar nueva condición | Configuración opcional. |
| En el último | Configuración opcional. |
| Nombre de audiencia | Le recomendamos que use el mismo [!DNL Audience Manager] nombre del segmento para mantener la coherencia, a menos que agregue condiciones adicionales a esta audiencia. |

## Paso 4: Asignación de la variable [!UICONTROL Audience] a [!UICONTROL Campaign] en [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Después de crear la variable [!DNL Custom Audience], asígnelo a una campaña de publicidad. Cree una campaña nueva o edite una existente y verá que la audiencia recién creada aparece en la sección [!DNL Facebook] interfaz de usuario. La campaña de publicidad se dirigirá a los usuarios que hayan visto activarse los píxeles en el explorador al visitar el sitio, si es que [!DNL Audience Manager] los incluye en el segmento.

## Resumen {#summary}

Ahora ha asignado su [!DNL Audience Manager] para [!DNL Facebook WCA] destino, [!DNL Audience Manager] activará de forma selectiva el [!DNL Facebook WCA] píxeles para los usuarios de un segmento determinado con el ID de segmento respectivo en el píxel para rellenar la variable [!DNL Facebook Audience]. Esto da lugar a un aumento gradual del [!DNL Facebook Audience] cuanto más se active la etiqueta a la audiencia aplicable del sitio.

>[!NOTE]
>
> Si un usuario sale de la función [!DNL Audience Manager] no hay forma de [!DNL Audience Manager] para informar [!DNL Facebook] para quitar el usuario del [!DNL Custom Audience].
