---
description: Esta página ilustra el proceso de creación de píxeles de Audiencias personalizadas del sitio web de Facebook (WCA) con el fin de enviar segmentos de audiencia de Audience Manager basados en web a Facebook, para la segmentación de anuncios en línea con una transparencia mejorada.
seo-description: Esta página ilustra el proceso de creación de píxeles de Audiencias personalizadas del sitio web de Facebook (WCA) con el fin de enviar segmentos de audiencia de Audience Manager basados en web a Facebook, para la segmentación de anuncios en línea con una transparencia mejorada.
seo-title: Integración de WCA de Facebook
solution: Audience Manager
title: Integración de WCA de Facebook
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 2%

---


# Integración de WCA de Facebook {#facebook-wca-integration}

Esta página ilustra el proceso de creación de [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) píxeles con el fin de enviar segmentos de [!DNL Audience Manager] audiencia basados en web a [!DNL Facebook], para la segmentación de anuncios en línea con una transparencia mejorada.

## Información general {#overview}

[Audiencias personalizadas del sitio web de Facebook (WCA)](https://www.facebook.com/business/help/449542958510885) le permite crear una lista de personas que han visitado determinadas páginas o han realizado determinadas acciones en el sitio web. [!DNL Audience Manager] habilita la activación en [!DNL WCA] el uso de [!DNL URL] destinos, con la cual puede configurar una integración personalizada basada en píxeles para enviar audiencias basadas en web a [!DNL Facebook] para su objetivo.

![Integración de WCA de Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Esta función requiere que seleccione la opción audiencia del sitio web para plataformas sociales en los destinos [de](/help/using/features/destinations/create-url-destination.md)URL. Las plataformas sociales requieren que la información de remitente del reenvío se desenmascara al enviarla a su plataforma. Tenga en cuenta que esto significa que la plataforma/socio de destino podrá ver la información en su remitente del reenvío [!DNL URL].

## Requisitos previos {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] , listo para asignar a su nuevo [!DNL Facebook] destino. A continuación se muestra [cómo crear un segmento](/help/using/features/segments/segment-builder.md) en la [!DNL Audience Manager] interfaz de usuario.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Versión 4.1.0 o posterior. Descargue la versión más reciente **[aquí](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) versión 9.0 o posterior, descargable desde **[aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Como alternativa, si utiliza el reenvío[del lado del servidor (SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)para importar datos en[!DNL Audience Manager], debe utilizar AppMeasurement versión 2.12 o posterior. Descargue[!DNL AppMeasurement]mediante el Administrador[de códigos de](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html)Analytics.

Le recomendamos que instale o actualice las bibliotecas en los pasos 3 y 4 con [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) o [Adobe Dynamic Tag Management](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html).

## Paso 1: Creación de un destino de Facebook en el Audience Manager {#step-1-create-facebook-destination}

Cree un nuevo [!UICONTROL URL Destination] en [!DNL Audience Manager] y asígnele un nombre [!DNL Facebook Website Custom Audiences]. Utilice la configuración siguiente al crear el destino. También puede consultar la página [Configurar un destino](/help/using/features/destinations/create-url-destination.md) de URL.

### Información básica

* **[!UICONTROL Category]**: Personalizado
* **[!UICONTROL Type]**: URL
* Seleccione la **[!UICONTROL Auto-fill Destination Mapping]** casilla de verificación y, a continuación, seleccione **[!UICONTROL Segment ID]**.

### Etiquetas de exportación de datos

Seleccione la opción **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Esta etiqueta de exportación evita que los datos y datos derivados de gráficos de dispositivos se incluyan en los segmentos.

### Configuración

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. Al seleccionar esta [!UICONTROL URL Type] opción, [!DNL Audience Manager] no oculta la información del remitente del reenvío [!DNL URL] al activar un [!DNL Facebook WCA] píxel.
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* En el campo **[!UICONTROL Base URL]** y **[!UICONTROL Secure URL]** , introduzca el [!DNL Facebook WCA] píxel.
* **[!UICONTROL Delimiter]**: ,

Ejemplo [!DNL URL] básico: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Ejemplo de píxel activado desde la página. Este ejemplo muestra un usuario que cumple los requisitos para tres [!DNL Audience Manager] segmentos, con los ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parámetro | Descripción |
---------|----------|
| `id` | Su ID [!DNL Facebook] de píxel, que puede encontrar en la interfaz de usuario al crear píxeles de audiencia [!DNL Facebook Ad Manager] . |
| `ev` | Event.     Se trata de un valor arbitrario que aparecerá en la interfaz de usuario una vez que el píxel empiece a activarse en el sitio. [!DNL Facebook Ad Manager] Consulte el [!UICONTROL Include] elemento del [paso 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)para obtener más información. |
| `cd[segID]` | Parámetro adicional que comenzará a rellenarse en la interfaz de usuario una vez que el píxel empiece a activarse en el sitio [!DNL Facebook Ad Manager] . `segID` también es arbitraria. |
| `%ALIAS%` | Una [!DNL Audience Manager] macro, que se reemplazará dinámicamente con las ID de los [!DNL Audience Manager] segmentos a los que se califica el visitante del sitio, delimitada por comas, |

La [!UICONTROL URL destination] configuración debería verse en la siguiente imagen:

![Configuración de destino](/help/using/integration/assets/facebook-wca.png)

Guarde el destino. A continuación, puede continuar con el paso Asignaciones **de segmentos** .

## Paso 2: Asignaciones de segmentos - Asignar segmento al destino {#step-2-segment-mappings}

En el flujo de trabajo [Configurar destino](/help/using/features/destinations/create-url-destination.md) de URL, asigne el segmento aplicable al destino recién creado. Observe que el valor de asignación se rellena automáticamente con la ID del [!DNL Audience Manager] segmento.

Introduzca una fecha de finalización, si corresponde; de lo contrario, deje en blanco sin fecha de finalización.

## Paso 3: Crear una Audiencia dentro del Administrador de publicidades para Facebook {#step-3-create-audience}

Consulte [Creación de una Audiencia](https://www.facebook.com/business/help/666509013483225) personalizada de sitio web en la documentación de la [!DNL Facebook] ayuda. Seleccione las [!UICONTROL Create Audience] opciones de la tabla siguiente:

| Elemento | Descripción |
---------|----------|
| Tráfico del sitio web | Combinación personalizada |
| Inclusión | <ul><li>Seleccione **Evento** > Seleccionar **Adobe-Audiencia-Manager-Segmento**. Este era el valor del parámetro ev en el píxel de ejemplo del paso 1. Tenga en cuenta que si el píxel aún no se ha activado, es posible que la opción de **Evento** o **Adobe-Audiencia-Manager-Segment** no aparezcan en la interfaz de usuario de Facebook.</li><li>Añadir un parámetro: Seleccione `segID`.</li><li><p>Seleccione el operador **contiene** .</p><p>Esto es importante, teniendo en cuenta que los visitantes pueden calificar para varios segmentos, puede haber varios ID de segmento en el parámetro pixel. Es posible que el uso del operador igual (=) no califique sus visitantes para la audiencia y observará un volumen menor.</p></li><li>Añadir un valor: Introduzca el ID del [!DNL Audience Manager] segmento.</li></ul> |
| Añadir nueva condición | Configuración opcional. |
| En el último | Configuración opcional. |
| Nombre de Audiencia | Le recomendamos que utilice el mismo nombre de segmento para mantener la coherencia, a menos que agregue condiciones adicionales a esta Audiencia. [!DNL Audience Manager] |

## Paso 4: Asignar la Audiencia a una Campaña en el Administrador de publicidades para Facebook {#step-4-assign-audience-to-campaign}

Después de crear el [!DNL Custom Audience], asígnelo a una campaña de publicidad. Cree una nueva campaña o edite una existente y encontrará que la audiencia recién creada se encuentra en la interfaz de [!DNL Facebook] usuario. La campaña de publicidad dará destinatario a los usuarios que hayan visto el incendio de píxeles en el explorador al visitar el sitio, si [!DNL Audience Manager] los incluye en el segmento.

## Resumen {#summary}

Ahora que ha asignado su [!DNL Audience Manager] segmento al [!DNL Facebook WCA] destino, [!DNL Audience Manager] activará el [!DNL Facebook WCA] píxel de forma selectiva para los usuarios de un segmento determinado con el ID de segmento correspondiente en el píxel para rellenar el [!DNL Facebook Audience]. Esto resulta en un aumento gradual en cuanto [!DNL Facebook Audience] más se activa la etiqueta en la audiencia aplicable del sitio.

>[!NOTE]
>
> Si un usuario se sale del [!DNL Audience Manager] segmento, no hay forma de [!DNL Audience Manager] informar [!DNL Facebook] para eliminar del [!DNL Custom Audience].