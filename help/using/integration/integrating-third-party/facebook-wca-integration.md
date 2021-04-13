---
description: Esta página ilustra el proceso de creación de píxeles de Audiencias personalizadas de sitio web de Facebook (WCA) con el fin de enviar segmentos de audiencia de Audience Manager basados en web a Facebook, para la segmentación de anuncios en línea con una transparencia mejorada.
seo-description: Esta página ilustra el proceso de creación de píxeles de Audiencias personalizadas de sitio web de Facebook (WCA) con el fin de enviar segmentos de audiencia de Audience Manager basados en web a Facebook, para la segmentación de anuncios en línea con una transparencia mejorada.
seo-title: Integración de WCA de Facebook
solution: Audience Manager
title: Integración de WCA de Facebook
feature: Integración de terceros
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 6%

---

# [!DNL Facebook WCA] de CRM {#facebook-wca-integration}

Esta página ilustra el proceso de creación de píxeles [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) con el fin de enviar segmentos de audiencia [!DNL Audience Manager] basados en web a [!DNL Facebook], para la segmentación de anuncios en línea con una transparencia mejorada.

## Información general {#overview}

[Audiencias personalizadas del sitio web de Facebook (WCA)](https://www.facebook.com/business/help/449542958510885)  le permite crear una lista de personas que han visitado determinadas páginas o que han realizado acciones concretas en el sitio web. [!DNL Audience Manager] activa la activación en  [!DNL WCA] mediante  [!DNL URL] destinos, con la cual puede configurar una integración personalizada basada en píxeles para enviar audiencias basadas en web a  [!DNL Facebook] para el objetivo.

![Integración de WCA de Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Esta capacidad requiere que seleccione la opción [!UICONTROL Website] audiencia para plataformas sociales en [destinos URL](/help/using/features/destinations/create-url-destination.md). Las plataformas sociales requieren que la información del referente se desenmascara cuando se envía a su plataforma. Tenga en cuenta que esto significa que la plataforma/socio de destino podrá ver la información en el referente [!DNL URL].

## Requisitos previos {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segmentos, listos para asignar al nuevo  [!DNL Facebook] destino. A continuación se indica [cómo crear un segmento](/help/using/features/segments/segment-builder.md) en la interfaz de usuario [!DNL Audience Manager].
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Versión 4.1.0 o posterior. Descargue la versión más reciente **[aquí](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) versión 9.0 o posterior, descargable desde  **[aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Alternativamente, si utiliza [Reenvío del lado del servidor (SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) para importar datos en [!DNL Audience Manager], debe utilizar la versión 2.12 o posterior de AppMeasurement. Descargue [!DNL AppMeasurement] mediante el [Administrador de códigos de Analytics](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html).

Le recomendamos que instale o actualice las bibliotecas en los pasos 3 y 4 mediante [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html) o [Dynamic Tag Management de Adobe](https://docs.adobe.com/content/help/es-ES/dtm/using/dtm-home.html).

## Paso 1: Crear un [!UICONTROL Facebook Destination] en [!DNL Audience Manager] {#step-1-create-facebook-destination}

Cree un nuevo [!UICONTROL URL Destination] en [!DNL Audience Manager] y asígnele el nombre [!DNL Facebook Website Custom Audiences]. Utilice la configuración siguiente al crear el destino. También puede consultar la página [Configure a URL Destination](/help/using/features/destinations/create-url-destination.md) .

### Información básica

* **[!UICONTROL Category]**: Personalizado
* **[!UICONTROL Type]**:  [!DNL URL]
* Seleccione la casilla de verificación **[!UICONTROL Auto-fill Destination Mapping]** y, a continuación, seleccione **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Seleccione la opción **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Esta etiqueta de exportación evita que los datos de terceros y los datos derivados de gráficos de dispositivos se incluyan en los segmentos.

### Configuración

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. Al seleccionar esta opción [!UICONTROL URL Type], [!DNL Audience Manager] no oculta la información del referente [!DNL URL] al activar un píxel [!DNL Facebook WCA].
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* En los campos **[!UICONTROL Base URL]** y **[!UICONTROL Secure URL]** , introduzca el píxel [!DNL Facebook WCA] .
* **[!UICONTROL Delimiter]**:  `,`

Ejemplo base [!DNL URL]: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Ejemplo de píxel activado desde la página. Este ejemplo muestra un usuario que cumple los requisitos para tres segmentos [!DNL Audience Manager], con los ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parámetro | Descripción |
---------|----------|
| `id` | Su ID de píxel [!DNL Facebook], que puede encontrar en la interfaz de usuario [!DNL Facebook Ad Manager] al crear píxeles de audiencia. |
| `ev` | Event.     Se trata de un valor arbitrario que aparecerá en la interfaz de usuario [!DNL Facebook Ad Manager] una vez que el píxel empiece a activarse en el sitio. Consulte el elemento [!UICONTROL Include] en [Paso 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience) para obtener más información. |
| `cd[segID]` | Un parámetro adicional, que empezará a rellenarse en la interfaz de usuario [!DNL Facebook Ad Manager] una vez que el píxel empiece a activarse en el sitio. `segID` también es arbitrario. |
| `%ALIAS%` | Una macro [!DNL Audience Manager], que se sustituirá de forma dinámica por los [!DNL Audience Manager] [!UICONTROL segment] ID para los que el visitante del sitio es apto, delimitada por comas , |

La configuración de [!UICONTROL URL destination] debería ser como en la siguiente imagen:

![Configuración del destino](/help/using/integration/assets/facebook-wca.png)

Guarde el [!UICONTROL destination]. A continuación, puede continuar con el paso **Asignaciones de segmentos**.

## Paso 2: Asignaciones de segmentos: Asignación de segmentos al destino {#step-2-segment-mappings}

En el flujo de trabajo [Configure URL destination](/help/using/features/destinations/create-url-destination.md) , asigne el segmento aplicable a su [!UICONTROL destination] recién creado. Observe que el valor de asignación se rellena automáticamente con [!DNL Audience Manager] [!UICONTROL segment ID].

Introduzca una fecha de finalización si corresponde; de lo contrario, deje en blanco sin fecha de finalización.

## Paso 3: Crear un [!UICONTROL Audience] dentro de [!DNL Facebook Ads Manager] {#step-3-create-audience}

Consulte [Crear una audiencia personalizada de sitio web](https://www.facebook.com/business/help/666509013483225) en la documentación de ayuda de [!DNL Facebook]. Seleccione las opciones de [!UICONTROL Create Audience] en la siguiente tabla:

| Elemento | Descripción |
---------|----------|
| Tráfico del sitio web | Combinación personalizada |
| Inclusión | <ul><li>Seleccione **[!UICONTROL Event]** > Seleccionar **[!UICONTROL Adobe-Audience-Manager-Segment]**. Este era el valor del parámetro `ev` en el píxel de ejemplo del paso 1. Tenga en cuenta que si el píxel aún no se ha activado, es posible que la opción **[!UICONTROL Event]** o **[!UICONTROL Adobe-Audience-Manager-Segment]** no aparezcan en la interfaz de usuario [!DNL Facebook].</li><li>Añada un parámetro: Seleccione `segID`.</li><li><p>Seleccione el operador **contains** .</p><p>Esto es importante, teniendo en cuenta que los visitantes pueden cumplir los requisitos para varios segmentos, puede haber varios [!UICONTROL segment IDs] en el parámetro de píxeles. Es posible que el uso del operador equals (`=`) no califique a los visitantes para la audiencia y que observe un volumen menor.</p></li><li>Agregue un valor: Introduzca el ID de segmento [!DNL Audience Manager].</li></ul> |
| Agregar nueva condición | Configuración opcional. |
| En el último | Configuración opcional. |
| Nombre de audiencia | Le recomendamos que utilice el mismo nombre de segmento [!DNL Audience Manager] para mantener la coherencia, a menos que agregue condiciones adicionales a esta audiencia. |

## Paso 4: Asignar el [!UICONTROL Audience] a un [!UICONTROL Campaign] en [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Después de crear el [!DNL Custom Audience], asígnelo a una campaña de publicidad. Cree una campaña nueva o edite una existente y encontrará que la audiencia recién creada aparece en la interfaz de usuario [!DNL Facebook] . La campaña de publicidad se dirigirá a los usuarios que hayan visto el incendio de píxeles en su explorador cuando visiten el sitio, si [!DNL Audience Manager] los incluye en el segmento.

## Resumen {#summary}

Ahora que ha asignado su segmento [!DNL Audience Manager] al destino [!DNL Facebook WCA], [!DNL Audience Manager] activará de forma selectiva el píxel [!DNL Facebook WCA] para los usuarios de un segmento determinado con el ID de segmento correspondiente en el píxel para rellenar el [!DNL Facebook Audience]. Esto resulta en un aumento gradual en el [!DNL Facebook Audience] cuanto más se active la etiqueta a la audiencia aplicable del sitio.

>[!NOTE]
>
> Si un usuario queda fuera del segmento [!DNL Audience Manager], actualmente no hay forma de que [!DNL Audience Manager] informe a [!DNL Facebook] para eliminar al usuario del [!DNL Custom Audience].

