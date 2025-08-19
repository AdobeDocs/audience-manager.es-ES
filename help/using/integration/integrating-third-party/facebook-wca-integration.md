---
description: Esta página ilustra el proceso de creación de píxeles de audiencias personalizadas del sitio web de Facebook (WCA) para el envío de segmentos de audiencia de Audience Manager basados en la web a Facebook, para la segmentación de anuncios en línea con una transparencia mejorada.
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Integración de WCA de Facebook
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 6dc931b88666515cf51ab89ce1a54bbcf9995679
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 1%

---

# Integración de [!DNL Facebook WCA] {#facebook-wca-integration}

Este Página ilustra el proceso de creación [!DNL Facebook Website Custom Audiences] de ([!DNL WCA]) píxeles para enviar segmentos de audiencia basados en [!DNL Audience Manager] web a [!DNL Facebook], para en línea anuncios direccionamiento con transparencia mejorada.

>[!IMPORTANT]
>
>No se trata de una integración de producto entre Audience Manager y Facebook.

## Información general {#overview}

[Facebook Website Custom Audiences (WCA)](https://www.facebook.com/business/help/610516375684216?id=2469097953376494) le permite crear un lista de personas que han visitado ciertas páginas o realizado acciones particulares en su sitio web. [!DNL Audience Manager] Permite activación usar [!DNL WCA] [!DNL URL] destinos, con los que puede configurar una integración personalizada basada en píxeles para enviar audiencias basadas en web a [!DNL Facebook] para direccionamiento.

![Integración de WCA de Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Esta capacidad requiere que seleccione la opción audiencia [!UICONTROL Website] para plataformas sociales en [URL destinos](/help/using/features/destinations/create-url-destination.md). Social plataformas requieren que remitente del reenvío información se desenmascare cuando se envía a su plataforma. Tenga en cuenta que esto significa que la plataforma/socio de destino podrá ver información en su remitente del reenvío [!DNL URL].

## Requisitos previos {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] lista, listos para asignar a su nuevo [!DNL Facebook] destino. Así es [como crear un segmento](/help/using/features/segments/segment-builder.md) en el [!DNL Audience Manager] IU.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Versión 4.1.0 o posterior. Descargue la última versión **[aquí](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) versión 9.0 o posterior, se puede descargar desde **[aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Alternativamente, si usa [Reenvío del lado del servidor (SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=es) para importar datos en [!DNL Audience Manager], debe usar la versión 2.12 o posterior de AppMeasurement. Descargar [!DNL AppMeasurement] con el [Administrador de códigos de Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html?lang=es).

Le recomendamos que instale o actualice las bibliotecas en los pasos 3 y 4 con [Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es).

## Paso 1: Crear una [!UICONTROL Facebook Destination] entrada [!DNL Audience Manager] {#step-1-create-facebook-destination}

Crear un nuevo [!UICONTROL URL Destination] en [!DNL Audience Manager] y asígnele [!DNL Facebook Website Custom Audiences]el nombre . Utilice la configuración siguiente al crear el destino. También puede consultar la página [Configurar un destino de URL](/help/using/features/destinations/create-url-destination.md).

### Información básica

* **[!UICONTROL Category]**: personalizado
* **[!UICONTROL Type]**: [!DNL URL]
* Active la casilla de verificación **[!UICONTROL Auto-fill Destination Mapping]** y, a continuación, seleccione **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Seleccione la opción **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Esta etiqueta de exportación evita que datos de terceros y datos derivados de gráficos de dispositivos se incluyan en los segmentos.

### Configuración

* **[!UICONTROL URL type]**: Seleccione **[!UICONTROL Website audience for social platforms]**. Al seleccionar esta [!UICONTROL URL Type] opción, [!DNL Audience Manager] no se oculta la información remitente del reenvío [!DNL URL] al activar un [!DNL Facebook WCA] píxel.
* **[!UICONTROL Serialize]**: Seleccione **[!UICONTROL Enable]**.
* En el **[!UICONTROL Base URL]** campo y **[!UICONTROL Secure URL]** , introduzca el [!DNL Facebook WCA] píxel.
* **[!UICONTROL Delimiter]**: `,`

Ejemplo base [!DNL URL] : `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Ejemplo de píxel disparado desde el Página. En este ejemplo se muestra un usuario que cumple los requisitos para tres [!DNL Audience Manager] segmentos, con los ID 3401321, 2993399 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parámetro | Descripción |
|---------|----------|
| `id` | Su ID de píxel [!DNL Facebook], que puede encontrar en la interfaz de usuario [!DNL Facebook Ad Manager] al crear píxeles de audiencia. |
| `ev` | Evento. Se trata de un valor arbitrario que aparecerá en la interfaz de usuario [!DNL Facebook Ad Manager] cuando el píxel comience a activarse en el sitio. Consulte el [!UICONTROL Include] elemento del [paso 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience) para obtener más información. |
| `cd[segID]` | Un parámetro adicional, que comenzará a rellenarse dentro de la interfaz usuario una vez que el píxel comience a activarse en el [!DNL Facebook Ad Manager] sitio. `segID` también es arbitrario. |
| `%ALIAS%` | Una [!DNL Audience Manager] macro, que se reemplazará dinámicamente por los ID para los [!DNL Audience Manager] [!UICONTROL segment] que califica el visitante del sitio, delimitada por comas , |

Su [!UICONTROL URL destination] configuración debe verse gustar en la imagen de abajo:

![Configuración de destino](/help/using/integration/assets/facebook-wca.png)

Guardar el [!UICONTROL destination]archivo . A continuación, puede continuar con el **paso Asignaciones de** segmentos.

## Paso 2: Asignaciones de segmentos: asignación de segmentos a destinos {#step-2-segment-mappings}

En la [flujo de trabajo Configurar URL destino](/help/using/features/destinations/create-url-destination.md), asigne el segmento aplicable al archivo .[!UICONTROL destination] Observe que el valor asignado se rellena automáticamente con el [!DNL Audience Manager] [!UICONTROL segment ID].

Ingrese una fecha de finalización si corresponde; de lo contrario, déjela en blanco para que no haya fecha de finalización.

## Paso 3: Crear un [!UICONTROL Audience][!DNL Facebook Ads Manager] {#step-3-create-audience}

Consulte [Crear una audiencia](https://www.facebook.com/business/help/666509013483225) personalizada de sitio web en la documentación de [!DNL Facebook] ayuda. Seleccione las opciones de [!UICONTROL Create Audience] la siguiente tabla:

| Elemento | Descripción |
|---------|----------|
| Tráfico del sitio web | Combinación personalizada |
| Inclusión | <ul><li>Seleccione **[!UICONTROL Event]** > Seleccionar **[!UICONTROL Adobe-Audience-Manager-Segment]**. Este fue el valor del parámetro en el píxel de `ev` ejemplo en el paso 1. Tenga en cuenta que si el píxel aún no se ha activado, es posible que la **[!UICONTROL Event]** opción o **[!UICONTROL Adobe-Audience-Manager-Segment]** no aparezca en la interfaz de usuario [!DNL Facebook] .</li><li>Agregar un parámetro: seleccione `segID`.</li><li><p>Seleccione el operador **contains**.</p><p>Esto es importante, teniendo en cuenta que los visitantes pueden cumplir los requisitos para varios segmentos, puede haber varios [!UICONTROL segment IDs] en el parámetro de píxel. Es posible que el uso del operador igual a (`=`) no califique a los visitantes para la audiencia y observará un volumen menor.</p></li><li>Agregar un valor: Escriba el identificador del segmento [!DNL Audience Manager].</li></ul> |
| Añadir nueva condición | Configuración opcional. |
| En los últimos | Configuración opcional. |
| Nombre de audiencia | Le recomendamos que use el mismo [!DNL Audience Manager] nombre de segmento para mantener la coherencia, a menos que vaya a añadir condiciones adicionales a esta audiencia. |

## Paso 4: Asignar [!UICONTROL Audience] el a un [!UICONTROL Campaign][!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Después de crear el [!DNL Custom Audience], asígnelo a un campaña de anuncios. Crear una nueva campaña o edite una existente y encontrará que la audiencia recién creada aparece en la interfaz de [!DNL Facebook] usuario. Tu campaña de anuncios destino usuarios que hayan visto el píxel dispararse en su explorador al visitar tu sitio, si [!DNL Audience Manager] los incluye en el segmento.

## Resumen {#summary}

Ahora que ha asignado su [!DNL Audience Manager] [!DNL Facebook WCA] segmento al destino, [!DNL Audience Manager] activará selectivamente el [!DNL Facebook WCA] píxel a los usuarios de un segmento determinado con el ID de segmento respectivo en el píxel para rellenar el [!DNL Facebook Audience]. Esto se traduce en un aumento gradual de cuanto [!DNL Facebook Audience] más se activa el etiqueta al audiencia aplicable en su sitio.

>[!NOTE]
>
> Si un usuario queda fuera del segmento [!DNL Audience Manager], actualmente no hay forma de que [!DNL Audience Manager] informe a [!DNL Facebook] para quitar al usuario de [!DNL Custom Audience].
>
