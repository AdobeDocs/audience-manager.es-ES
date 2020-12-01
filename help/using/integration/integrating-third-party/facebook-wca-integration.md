---
description: Esta página ilustra el proceso de creación de píxeles de Audiencias personalizadas del sitio web de Facebook (WCA) con el fin de enviar segmentos de audiencia de Audience Manager basados en web a Facebook, para la segmentación de anuncios en línea con una transparencia mejorada.
seo-description: Esta página ilustra el proceso de creación de píxeles de Audiencias personalizadas del sitio web de Facebook (WCA) con el fin de enviar segmentos de audiencia de Audience Manager basados en web a Facebook, para la segmentación de anuncios en línea con una transparencia mejorada.
seo-title: Integración de WCA de Facebook
solution: Audience Manager
title: Integración de WCA de Facebook
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 6%

---


# [!DNL Facebook WCA] de CRM {#facebook-wca-integration}

Esta página ilustra el proceso de creación de [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) píxeles con el fin de enviar segmentos de audiencia [!DNL Audience Manager] basados en Web a [!DNL Facebook], para objetivos de publicidad en línea con una mayor transparencia.

## Información general {#overview}

[Las Audiencias personalizadas del sitio web de Facebook (WCA) ](https://www.facebook.com/business/help/449542958510885) permiten crear una lista de personas que han visitado determinadas páginas o han realizado determinadas acciones en el sitio web. [!DNL Audience Manager] permite la activación en  [!DNL WCA] el uso de  [!DNL URL] destinos, con los que se puede configurar una integración personalizada basada en píxeles para enviar audiencias basadas en web a  [!DNL Facebook] para la segmentación.

![Integración de WCA de Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Esta capacidad requiere que seleccione la opción [!UICONTROL Website] audiencia para plataformas sociales en [destinos URL](/help/using/features/destinations/create-url-destination.md). Las plataformas sociales requieren que la información de remitente del reenvío se desenmascara al enviarla a su plataforma. Tenga en cuenta que esto significa que la plataforma/socio de destino podrá ver la información en su remitente del reenvío [!DNL URL].

## Requisitos previos {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] , listo para asignar a su nuevo  [!DNL Facebook] destino. A continuación se muestra [cómo crear un segmento](/help/using/features/segments/segment-builder.md) en la [!DNL Audience Manager] interfaz de usuario.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Versión 4.1.0 o posterior. Descargue la versión más reciente **[aquí](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) versión 9.0 o posterior, descargable desde  **[aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Como alternativa, si utiliza [reenvío del lado del servidor (SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) para importar datos en [!DNL Audience Manager], debe utilizar AppMeasurement versión 2.12 o posterior. Descargue [!DNL AppMeasurement] con el [Administrador de códigos de Analytics](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html).

Le recomendamos que instale o actualice las bibliotecas en los pasos 3 y 4 con [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) o [Administración dinámica de etiquetas de Adobe](https://docs.adobe.com/content/help/es-ES/dtm/using/dtm-home.html).

## Paso 1: Crear un [!UICONTROL Facebook Destination] en [!DNL Audience Manager] {#step-1-create-facebook-destination}

Cree un nuevo [!UICONTROL URL Destination] en [!DNL Audience Manager] y asígnele el nombre [!DNL Facebook Website Custom Audiences]. Utilice la configuración siguiente al crear el destino. También puede consultar la página [Configurar un destino de URL](/help/using/features/destinations/create-url-destination.md).

### Información básica

* **[!UICONTROL Category]**: Personalizado
* **[!UICONTROL Type]**::  [!DNL URL]
* Seleccione la casilla de verificación **[!UICONTROL Auto-fill Destination Mapping]** y luego seleccione **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Seleccione la opción **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Esta etiqueta de exportación evita que los datos y datos derivados de gráficos de dispositivos se incluyan en los segmentos.

### Configuración

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. Al seleccionar esta opción [!UICONTROL URL Type], [!DNL Audience Manager] no oculta la información del remitente del reenvío [!DNL URL] al activar un píxel [!DNL Facebook WCA].
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* En los campos **[!UICONTROL Base URL]** y **[!UICONTROL Secure URL]**, introduzca el píxel [!DNL Facebook WCA].
* **[!UICONTROL Delimiter]**::  `,`

Ejemplo base [!DNL URL]: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Ejemplo de píxel activado desde la página. Este ejemplo muestra un usuario que cumple los requisitos para tres segmentos [!DNL Audience Manager], con los ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parámetro | Descripción |
---------|----------|
| `id` | Su [!DNL Facebook] ID de píxel, que puede encontrar en la interfaz de usuario [!DNL Facebook Ad Manager] al crear píxeles de audiencia. |
| `ev` | Event.     Se trata de un valor arbitrario que aparecerá en la interfaz de usuario [!DNL Facebook Ad Manager] una vez que el píxel se active en el sitio. Consulte el elemento [!UICONTROL Include] en [Paso 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience) para obtener más información. |
| `cd[segID]` | Un parámetro adicional que comenzará a rellenarse en la interfaz de usuario [!DNL Facebook Ad Manager] una vez que el píxel comience a activarse en el sitio. `segID` también es arbitraria. |
| `%ALIAS%` | Una macro [!DNL Audience Manager], que se reemplazará dinámicamente con los [!DNL Audience Manager] [!UICONTROL segment] ID para los que el visitante del sitio cumple los requisitos, delimitada por comas, |

La configuración [!UICONTROL URL destination] debe verse como en la siguiente imagen:

![Configuración de destino](/help/using/integration/assets/facebook-wca.png)

Guarde el [!UICONTROL destination]. A continuación, puede continuar con el paso **Asignaciones de segmentos**.

## Paso 2 - Asignaciones de segmentos - Asignar segmento al destino {#step-2-segment-mappings}

En el flujo de trabajo [Configurar destino de URL](/help/using/features/destinations/create-url-destination.md), asigne el segmento aplicable a su [!UICONTROL destination] recién creado. Observe que el valor de asignación se rellena automáticamente con [!DNL Audience Manager] [!UICONTROL segment ID].

Introduzca una fecha de finalización, si corresponde; de lo contrario, deje en blanco sin fecha de finalización.

## Paso 3: Crear un [!UICONTROL Audience] dentro de [!DNL Facebook Ads Manager] {#step-3-create-audience}

Consulte [Creación de una Audiencia personalizada de sitio web](https://www.facebook.com/business/help/666509013483225) en la [!DNL Facebook] documentación de ayuda. Seleccione las opciones [!UICONTROL Create Audience] en la tabla siguiente:

| Elemento | Descripción |
---------|----------|
| Tráfico del sitio web | Combinación personalizada |
| Inclusión | <ul><li>Seleccione **[!UICONTROL Event]** > Seleccionar **[!UICONTROL Adobe-Audience-Manager-Segment]**. Este era el valor del parámetro `ev` en el píxel de ejemplo del paso 1. Tenga en cuenta que si el píxel aún no se ha activado, es posible que la opción **[!UICONTROL Event]** o **[!UICONTROL Adobe-Audience-Manager-Segment]** no aparezcan en la interfaz de usuario [!DNL Facebook].</li><li>Añadir un parámetro: Seleccione `segID`.</li><li><p>Seleccione el operador **contiene**.</p><p>Esto es importante, teniendo en cuenta que los visitantes pueden calificar para varios segmentos, puede haber varios [!UICONTROL segment IDs] en el parámetro pixel. El uso del operador igual (`=`) puede no calificar sus visitantes para la audiencia y observará un volumen menor.</p></li><li>Añadir un valor: Introduzca el ID de segmento [!DNL Audience Manager].</li></ul> |
| Añadir nueva condición | Configuración opcional. |
| En el último | Configuración opcional. |
| Nombre de audiencia | Le recomendamos que utilice el mismo [!DNL Audience Manager] nombre de segmento para mantener la coherencia, a menos que agregue condiciones adicionales a esta Audiencia. |

## Paso 4: Asigne el [!UICONTROL Audience] a un [!UICONTROL Campaign] en [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Después de crear el [!DNL Custom Audience], asígnelo a una campaña de publicidad. Cree una nueva campaña o edite una existente y encontrará que la audiencia recién creada aparece en la interfaz de usuario [!DNL Facebook]. La campaña de publicidad hará un destinatario de los usuarios que hayan visto la activación de píxeles en el explorador al visitar el sitio, si [!DNL Audience Manager] los incluye en el segmento.

## Resumen {#summary}

Ahora que ha asignado el segmento [!DNL Audience Manager] al destino [!DNL Facebook WCA], [!DNL Audience Manager] activará el píxel [!DNL Facebook WCA] de forma selectiva para los usuarios de un segmento determinado con el ID de segmento correspondiente en el píxel para rellenar el [!DNL Facebook Audience]. Esto resulta en un aumento gradual en el [!DNL Facebook Audience] cuanto más se active la etiqueta en la audiencia aplicable del sitio.

>[!NOTE]
>
> Si un usuario se encuentra fuera del segmento [!DNL Audience Manager], actualmente no hay forma de que [!DNL Audience Manager] informe a [!DNL Facebook] para eliminar al usuario del segmento [!DNL Custom Audience].

