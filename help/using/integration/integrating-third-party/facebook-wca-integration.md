---
description: Esta página ilustra el proceso de creación de píxeles de audiencias personalizadas del sitio web de Facebook (WCA) con el fin de enviar segmentos de audiencia de Audience Manager basados en la web a Facebook para una segmentación de anuncios en línea con una transparencia mejorada.
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Integración de WCA de Facebook
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 8780083474d68717fe3bd4dc632d96da89929122
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 4%

---

# [!DNL Facebook WCA] de CRM {#facebook-wca-integration}

Esta página ilustra el proceso de creación de [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) píxeles para los fines de envío de contenido basado en web [!DNL Audience Manager] segmentos de audiencia a [!DNL Facebook], para la segmentación de anuncios en línea con una transparencia mejorada.

## Información general {#overview}

[Audiencias personalizadas del sitio web de facebook (WCA)](https://www.facebook.com/business/help/610516375684216?id=2469097953376494) permite crear una lista de personas que han visitado determinadas páginas o han realizado acciones concretas en el sitio web. [!DNL Audience Manager] habilita la activación en [!DNL WCA] usando [!DNL URL] destinos, con los que se puede configurar una integración personalizada basada en píxeles para enviar audiencias basadas en web a [!DNL Facebook] para la segmentación.

![Integración de WCA de Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Esta capacidad requiere que seleccione la variable [!UICONTROL Website] opción de audiencia para plataformas sociales en [Destinos URL](/help/using/features/destinations/create-url-destination.md). Las plataformas sociales requieren que la información del referente se desenmascara cuando se envía a su plataforma. Tenga en cuenta que esto significa que la plataforma o el socio de destino podrán ver información en el referente [!DNL URL].

## Requisitos previos {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segmentos, listos para asignar a su nuevo [!DNL Facebook] destino. Aquí está [cómo crear un segmento](/help/using/features/segments/segment-builder.md) en el [!DNL Audience Manager] IU.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Versión 4.1.0 o posterior. Descargue la versión más reciente **[aquí](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) versión 9.0 o posterior, se puede descargar desde **[aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Alternativamente, si utiliza [Reenvío del lado del servidor (SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) para importar datos en [!DNL Audience Manager], debe utilizar AppMeasurement versión 2.12 o posterior. Descargar [!DNL AppMeasurement] uso del [Administrador de códigos de Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).

Le recomendamos que instale o actualice las bibliotecas en los pasos 3 y 4 utilizando [Etiquetas de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

## Paso 1: Creación de una [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

Crear un nuevo [!UICONTROL URL Destination] in [!DNL Audience Manager] y asígnele un nombre [!DNL Facebook Website Custom Audiences]. Utilice la siguiente configuración al crear el destino. También puede consultar la [Configuración de un destino de URL](/help/using/features/destinations/create-url-destination.md) página.

### Información básica

* **[!UICONTROL Category]**: Personalizado
* **[!UICONTROL Type]**: [!DNL URL]
* Seleccione el **[!UICONTROL Auto-fill Destination Mapping]** y, a continuación, seleccione **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Seleccione la opción **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Esta etiqueta de exportación evita que los datos de terceros y los datos derivados de los gráficos de dispositivos se incluyan en los segmentos.

### Configuración

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. Seleccionando esta opción [!UICONTROL URL Type] opción, [!DNL Audience Manager] no oscurece al referente [!DNL URL] información al activar un [!DNL Facebook WCA] píxel.
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* En el **[!UICONTROL Base URL]** y **[!UICONTROL Secure URL]** , introduzca la variable [!DNL Facebook WCA] píxel.
* **[!UICONTROL Delimiter]**: `,`

Base [!DNL URL] ejemplo: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Ejemplo de píxel activado desde la página. Este ejemplo muestra un usuario que cumple los requisitos para tres [!DNL Audience Manager] con los ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parámetro | Descripción |
|---------|----------|
| `id` | Su [!DNL Facebook] ID de píxel, que puede encontrar en la [!DNL Facebook Ad Manager] interfaz de usuario al crear píxeles de audiencia. |
| `ev` | Event.     Este es un valor arbitrario, que aparecerá en el [!DNL Facebook Ad Manager] interfaz de usuario una vez que el píxel empieza a activarse en el sitio. Consulte la [!UICONTROL Include] elemento en [Paso 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), para obtener más información. |
| `cd[segID]` | Un parámetro adicional, que empezará a rellenarse dentro de [!DNL Facebook Ad Manager] interfaz de usuario una vez que el píxel empieza a activarse en el sitio. `segID` también es arbitrario. |
| `%ALIAS%` | Un [!DNL Audience Manager] macro, que se reemplazará dinámicamente con la variable [!DNL Audience Manager] [!UICONTROL segment] ID para los que el visitante del sitio cumple los requisitos, delimitados por comas , |

Su [!UICONTROL URL destination] La configuración de debería ser similar a la de la imagen siguiente:

![Configuración de destino](/help/using/integration/assets/facebook-wca.png)

Guarde el [!UICONTROL destination]. A continuación, puede continuar con la **Asignaciones de segmentos** paso.

## Paso 2: Asignaciones de segmentos: Asignar segmentos a destino {#step-2-segment-mappings}

En el [Configurar destino de URL](/help/using/features/destinations/create-url-destination.md) flujo de trabajo, asigne el segmento aplicable al segmento recién creado [!UICONTROL destination]. Observe que el valor de asignación se rellena automáticamente con la variable [!DNL Audience Manager] [!UICONTROL segment ID].

Introduzca una fecha de finalización si corresponde; en caso contrario, déjelo en blanco para indicar que no hay fecha de finalización.

## Paso 3: Creación de una [!UICONTROL Audience] dentro [!DNL Facebook Ads Manager] {#step-3-create-audience}

Consulte [Crear una audiencia personalizada de sitio web](https://www.facebook.com/business/help/666509013483225) en el [!DNL Facebook] documentación de ayuda. Seleccione el [!UICONTROL Create Audience] opciones de la tabla siguiente:

| Elemento | Descripción |
|---------|----------|
| Tráfico del sitio web | Combinación personalizada |
| Inclusión | <ul><li>Seleccionar **[!UICONTROL Event]** > Seleccionar **[!UICONTROL Adobe-Audience-Manager-Segment]**. Este era el valor de `ev` parámetro en el píxel de ejemplo del paso 1. Tenga en cuenta que si el píxel aún no se ha activado, la variable **[!UICONTROL Event]** opción o **[!UICONTROL Adobe-Audience-Manager-Segment]** puede no aparecer en [!DNL Facebook] interfaz de usuario.</li><li>Añadir un parámetro: seleccione. `segID`.</li><li><p>Seleccione el **contains** operador.</p><p>Esto es importante, teniendo en cuenta que los visitantes pueden cumplir los requisitos para varios segmentos, puede haber varios [!UICONTROL segment IDs] en el parámetro píxel. Uso de igual a (`=`) es posible que el operador no clasifique a sus visitantes para la audiencia y observará un volumen menor.</p></li><li>Añadir un valor: introduzca el [!DNL Audience Manager] ID del segmento.</li></ul> |
| Añadir nueva condición | Configuración opcional. |
| En los últimos | Configuración opcional. |
| Nombre de audiencia | Le recomendamos que utilice el mismo [!DNL Audience Manager] Nombre del segmento para mantener la coherencia, a menos que agregue condiciones adicionales a esta audiencia. |

## Paso 4: Asignación de [!UICONTROL Audience] a un [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Después de crear la variable [!DNL Custom Audience], asígnelo a una campaña de publicidad. Cree una nueva campaña o edite una existente y verá que la audiencia recién creada se enumera en la [!DNL Facebook] interfaz de usuario. Su campaña de publicidad se dirigirá a los usuarios que hayan visto el píxel activarse en su explorador al visitar el sitio, si [!DNL Audience Manager] los incluye en el segmento.

## Resumen {#summary}

Ahora que ha asignado su [!DNL Audience Manager] segmentar a [!DNL Facebook WCA] destino, [!DNL Audience Manager] activará selectivamente el [!DNL Facebook WCA] píxel a los usuarios de un segmento determinado con el ID de segmento respectivo en el píxel para rellenar el [!DNL Facebook Audience]. Esto se traduce en un aumento gradual de la [!DNL Facebook Audience] cuanto más se dispara la etiqueta a la audiencia correspondiente del sitio.

>[!NOTE]
>
> Si un usuario se excluye de la [!DNL Audience Manager] segmento, actualmente no hay forma de [!DNL Audience Manager] para informar [!DNL Facebook] para eliminar al usuario de [!DNL Custom Audience].
