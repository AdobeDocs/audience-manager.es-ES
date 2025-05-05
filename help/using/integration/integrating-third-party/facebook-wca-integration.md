---
description: Esta página ilustra el proceso de creación de píxeles de audiencias personalizadas del sitio web de Facebook (WCA) con el fin de enviar segmentos de audiencia de Audience Manager basados en la web a Facebook para una segmentación de anuncios en línea con una transparencia mejorada.
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Integración de WCA de facebook
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 6dc931b88666515cf51ab89ce1a54bbcf9995679
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 1%

---

# Integración de [!DNL Facebook WCA] {#facebook-wca-integration}

Esta página ilustra el proceso de creación de [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) píxeles con el fin de enviar segmentos de audiencia de [!DNL Audience Manager] basados en la web a [!DNL Facebook] para la segmentación de anuncios en línea con una transparencia mejorada.

>[!IMPORTANT]
>
>No se trata de una integración de productos entre Audience Manager y Facebook.

## Información general {#overview}

[Audiencias personalizadas del sitio web de Facebook (WCA)](https://www.facebook.com/business/help/610516375684216?id=2469097953376494) le permite crear una lista de personas que han visitado determinadas páginas o han realizado acciones concretas en el sitio web. [!DNL Audience Manager] habilita la activación en [!DNL WCA] usando [!DNL URL] destinos, con los cuales puede configurar una integración personalizada basada en píxeles para enviar audiencias basadas en web a [!DNL Facebook] para el direccionamiento.

![Integración de WCA de Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Esta capacidad requiere que seleccione la opción [!UICONTROL Website] audiencia para plataformas sociales en [destinos de URL](/help/using/features/destinations/create-url-destination.md). Las plataformas sociales requieren que la información del referente se desenmascara cuando se envía a su plataforma. Tenga en cuenta que esto significa que la plataforma o el socio de destino podrá ver información en su referente [!DNL URL].

## Requisitos previos {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segmentos, listos para asignar a su nuevo destino [!DNL Facebook]. A continuación se muestra [cómo crear un segmento](/help/using/features/segments/segment-builder.md) en la interfaz de usuario de [!DNL Audience Manager].
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Versión 4.1.0 o posterior. Descargue la versión más reciente **[aquí](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) versión 9.0 o posterior, se puede descargar desde **[aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Alternativamente, si usa [Reenvío del lado del servidor (SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=es) para importar datos en [!DNL Audience Manager], debe usar la versión de AppMeasurement 2.12 o posterior. Descargar [!DNL AppMeasurement] con el [Administrador de códigos de Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html?lang=es).

Le recomendamos que instale o actualice las bibliotecas en los pasos 3 y 4 con [Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es).

## Paso 1: Creación de un(a) [!UICONTROL Facebook Destination] en [!DNL Audience Manager] {#step-1-create-facebook-destination}

Cree un nuevo(a) [!UICONTROL URL Destination] en [!DNL Audience Manager] y asígnele el nombre [!DNL Facebook Website Custom Audiences]. Utilice la siguiente configuración al crear el destino. También puede consultar la página [Configurar un destino de URL](/help/using/features/destinations/create-url-destination.md).

### Información básica

* **[!UICONTROL Category]**: personalizado
* **[!UICONTROL Type]**: [!DNL URL]
* Active la casilla de verificación **[!UICONTROL Auto-fill Destination Mapping]** y, a continuación, seleccione **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Seleccione la opción **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Esta etiqueta de exportación evita que los datos de terceros y los datos derivados de los gráficos de dispositivos se incluyan en los segmentos.

### Configuración

* **[!UICONTROL URL type]**: seleccione **[!UICONTROL Website audience for social platforms]**. Al seleccionar esta opción [!UICONTROL URL Type], [!DNL Audience Manager] no oculta la información del referente [!DNL URL] al activar un píxel [!DNL Facebook WCA].
* **[!UICONTROL Serialize]**: seleccione **[!UICONTROL Enable]**.
* En el campo **[!UICONTROL Base URL]** y **[!UICONTROL Secure URL]**, introduzca el píxel [!DNL Facebook WCA].
* **[!UICONTROL Delimiter]**: `,`

Ejemplo de base [!DNL URL]: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Ejemplo de píxel activado desde la página. Este ejemplo muestra un usuario que cumple los requisitos para tres segmentos de [!DNL Audience Manager], con los ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parámetro | Descripción |
|---------|----------|
| `id` | Su ID de píxel [!DNL Facebook], que puede encontrar en la interfaz de usuario [!DNL Facebook Ad Manager] al crear píxeles de audiencia. |
| `ev` | Evento. Se trata de un valor arbitrario que aparecerá en la interfaz de usuario [!DNL Facebook Ad Manager] cuando el píxel comience a activarse en el sitio. Consulte el elemento [!UICONTROL Include] en [Paso 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), para obtener más información. |
| `cd[segID]` | Un parámetro adicional, que empezará a rellenarse dentro de la interfaz de usuario [!DNL Facebook Ad Manager] una vez que el píxel comience a activarse en el sitio. `segID` también es arbitrario. |
| `%ALIAS%` | Una macro [!DNL Audience Manager], que se reemplazará dinámicamente por los identificadores [!DNL Audience Manager] [!UICONTROL segment] a los que el visitante del sitio pertenece, delimitados por comas, |

La configuración de [!UICONTROL URL destination] debe ser similar a la que se muestra en la siguiente imagen:

![Configuración de destino](/help/using/integration/assets/facebook-wca.png)

Guarde [!UICONTROL destination]. A continuación, puede continuar con el paso **Asignaciones de segmentos**.

## Paso 2: Asignaciones de segmentos: Asignar segmentos a destino {#step-2-segment-mappings}

En el flujo de trabajo [Configurar destino de URL](/help/using/features/destinations/create-url-destination.md), asigne el segmento aplicable a su [!UICONTROL destination] recién creada. Observe que el valor de asignación se rellena automáticamente con [!DNL Audience Manager] [!UICONTROL segment ID].

Introduzca una fecha de finalización si corresponde; en caso contrario, déjelo en blanco para indicar que no hay fecha de finalización.

## Paso 3: Creación de un(a) [!UICONTROL Audience] en [!DNL Facebook Ads Manager] {#step-3-create-audience}

Consulte [Crear una audiencia personalizada de sitio web](https://www.facebook.com/business/help/666509013483225) en la documentación de ayuda de [!DNL Facebook]. Seleccione las opciones [!UICONTROL Create Audience] de la tabla siguiente:

| Elemento | Descripción |
|---------|----------|
| Tráfico del sitio web | Combinación personalizada |
| Inclusión | <ul><li>Seleccione **[!UICONTROL Event]** > Seleccionar **[!UICONTROL Adobe-Audience-Manager-Segment]**. Este era el valor del parámetro `ev` en el píxel de ejemplo del paso 1. Tenga en cuenta que si el píxel aún no se ha activado, es posible que la opción **[!UICONTROL Event]** o **[!UICONTROL Adobe-Audience-Manager-Segment]** no aparezcan en la interfaz de usuario [!DNL Facebook].</li><li>Agregar un parámetro: seleccione `segID`.</li><li><p>Seleccione el operador **contains**.</p><p>Esto es importante, teniendo en cuenta que los visitantes pueden cumplir los requisitos para varios segmentos, puede haber varios [!UICONTROL segment IDs] en el parámetro de píxel. Es posible que el uso del operador igual a (`=`) no califique a los visitantes para la audiencia y observará un volumen menor.</p></li><li>Agregar un valor: Escriba el identificador del segmento [!DNL Audience Manager].</li></ul> |
| Añadir nueva condición | Configuración opcional. |
| En los últimos | Configuración opcional. |
| Nombre de audiencia | Le recomendamos que utilice el mismo nombre de segmento [!DNL Audience Manager] para mantener la coherencia, a menos que esté agregando condiciones adicionales a esta audiencia. |

## Paso 4: Asignar [!UICONTROL Audience] a [!UICONTROL Campaign] en [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Después de crear [!DNL Custom Audience], asígnelo a una campaña de publicidad. Cree una nueva campaña o edite una existente y verá que la audiencia recién creada aparece en la interfaz de usuario [!DNL Facebook]. Su campaña de publicidad se dirigirá a los usuarios que hayan visto el píxel activarse en su explorador al visitar el sitio, si [!DNL Audience Manager] los incluye en el segmento.

## Resumen {#summary}

Ahora que ha asignado el segmento [!DNL Audience Manager] al destino [!DNL Facebook WCA], [!DNL Audience Manager] activará selectivamente el píxel [!DNL Facebook WCA] a los usuarios de un segmento determinado con el ID de segmento respectivo en el píxel para rellenar [!DNL Facebook Audience]. Esto resulta en un aumento gradual de [!DNL Facebook Audience] cuanto más se dispara la etiqueta a la audiencia aplicable en su sitio.

>[!NOTE]
>
> Si un usuario queda fuera del segmento [!DNL Audience Manager], actualmente no hay forma de que [!DNL Audience Manager] informe a [!DNL Facebook] para quitar al usuario de [!DNL Custom Audience].
>
