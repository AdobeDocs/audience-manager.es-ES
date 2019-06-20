---
description: Esta página ilustra el proceso de crear píxeles de Audiencias personalizadas de sitios Web de Facebook (WCA) con el fin de enviar segmentos de audiencia de Audience Manager basados en la Web a Facebook, para direccionar anuncios en línea con transparencia mejorada.
seo-description: Esta página ilustra el proceso de crear píxeles de Audiencias personalizadas de sitios Web de Facebook (WCA) con el fin de enviar segmentos de audiencia de Audience Manager basados en la Web a Facebook, para direccionar anuncios en línea con transparencia mejorada.
seo-title: Integración de WCA de Facebook
solution: Audience Manager
title: Integración de WCA de Facebook
translation-type: tm+mt
source-git-commit: 56999c1968a486bed0e2e672a4de1774d049e09d

---


# Facebook WCA Integration {#facebook-wca-integration}

Esta página ilustra el proceso de crear píxeles de Audiencias personalizadas de sitios Web de Facebook (WCA) con el fin de enviar segmentos de audiencia de Audience Manager basados en la Web a Facebook, para direccionar anuncios en línea con transparencia mejorada.

## Información general {#overview}

[Audiencias personalizadas del sitio Web de Facebook (WCA)](https://www.facebook.com/business/help/449542958510885) permite crear una lista de personas que han visitado determinadas páginas o han realizado determinadas acciones en su sitio Web. Audience Manager permite la activación en WCA mediante destinos URL, con los que se puede configurar una integración basada en píxeles personalizados para enviar audiencias basadas en la Web a Facebook para la segmentación.

![Integración de WCA de Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> This capability requires that you select the Website audience for social platforms option in [URL destinations](/help/using/features/destinations/manage-destinations.md#configure-url-destination). Las plataformas sociales requieren que la información del referente se deje sin máscara cuando se envía a su plataforma. Tenga en cuenta que esto significa que la plataforma o socio de destino podrá ver la información en su URL de referente.

## Requisitos previos {#prerequisites}

1. Cuenta de publicidad de Facebook
2. Segmentos de Audience Manager, listos para asignarse al nuevo destino de Facebook. Here is [how to create a segment](/help/using/features/segments/segment-builder.md) in the Audience Manager UI.
3. Adobe Experience Cloud ID Service (ECID) versión 4.1.0 o posterior. Download the latest version **[here](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. Audience Manager Data Integration Library (DIL) version 9.0 or newer, downloadable from **[here](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Alternatively, if you use [Server-Side Forwarding (SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) to import data into Audience Manager, you must use AppMeasurement version 2.12 or newer. Download AppMeasurement using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).

We recommend that you install or upgrade the libraries in steps 3 and 4 using [Adobe Launch](https://docs.adobelaunch.com/) or [Adobe Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

## Step 1 - Create a Facebook Destination in Audience Manager {#step-1-create-facebook-destination}

Cree un nuevo destino de URL en Audience Manager y asígnele el nombre Audiencias personalizadas del sitio Web de Facebook. Utilice los ajustes siguientes al crear el destino. You can also refer to the [Configure a URL Destination](/help/using/features/destinations/manage-destinations.md#configure-url-destination) page.

**Información básica**

* **Categoría**: Personalizado
* **Tipo**: URL
* Select the **Auto-fill Destination Mapping** check box, then select **Segment ID**.

**Etiquetas de exportación de datos**

Select the option **This destination may enable a combination with personally identifiable information (PII)**.

>[!NOTE]
>
> Esta etiqueta de exportación evita que los datos de terceros y los datos derivados de los gráficos de dispositivos se incluyan en los segmentos.

**Configuración**

* **Tipo de URL**: Seleccione **audiencia de sitio web para plataformas sociales**. Al seleccionar esta opción de tipo de URL, Audience Manager no oscurecerá la información de URL del referente al activar un píxel WCA de Facebook.
* **Serializar**: Seleccione **Habilitar**.
* In the **Base URL** and **Secure URL** field, enter the Facebook WCA pixel.
* **Delimitador**: ,

Base URL example: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Se ha activado el píxel de ejemplo desde la página. Este ejemplo muestra un usuario que califica para tres segmentos de Audience Manager, con los ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Parámetro | Descripción |
---------|----------|
| `id` | Su ID de píxeles de Facebook, que se encuentra en la interfaz de usuario del Administrador de publicidad de Facebook al crear píxeles de audiencia. |
| `ev` | Evento. Este es un valor arbitrario, que aparecerá en la interfaz de usuario del Administrador de publicidad de Facebook una vez que el píxel empiece a activarse en el sitio. See the Include item in [Step 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), for more information. |
| `cd[segID]` | Parámetro adicional que comenzará a rellenarse dentro de la interfaz de usuario del Administrador de publicidad de Facebook una vez que el píxel empieza a activarse en el sitio. `segID` también es arbitrario. |
| `%ALIAS%` | Una macro de Audience Manager que se reemplazará dinámicamente por los ID de segmento de Audience Manager para los que el visitante del sitio esté cualificado, delimitado por coma, |

La configuración de destino de URL debería verse en la siguiente imagen:

![Configuración de la destinación](/help/using/integration/assets/facebook-wca.png)

Guarde el destino. Then, you can proceed to the **Segment Mappings** step.

## Step 2 - Segment Mappings - Map Segment to Destination {#step-2-segment-mappings}

In the [Configure URL destination](/help/using/features/destinations/manage-destinations.md#configure-url-destination) workflow, map the applicable segment to your newly created destination. Observe que el valor de asignación se rellena automáticamente con el ID de segmento de Audience Manager.

Ingrese una fecha de finalización, si corresponde, y deje en blanco sin fecha de finalización.

## Step 3 - Create an Audience within Facebook Ads Manager {#step-3-create-audience}

See [Create a Website Custom Audience](https://www.facebook.com/business/help/666509013483225) in the Facebook help documentation. Seleccione las opciones Crear audiencia en la tabla siguiente:


| Elemento | Descripción |
---------|----------|
| Tráfico del sitio web | Combinación personalizada |
| Inclusión | <ul><li>Select **Event** &gt; Select **Adobe-Audience-Manager-Segment**. Este era el valor del parámetro ev en el píxel de ejemplo del paso 1. Note that if the pixel is yet to fire, the **Event** option or **Adobe-Audience-Manager-Segment** may not appear in the Facebook UI.</li><li>Add a parameter: Select `segID`.</li><li><p>Select the **contains** operator.</p><p>Esto es importante, teniendo en cuenta que los visitantes pueden calificar para varios segmentos, puede haber varios ID de segmento en el parámetro de píxeles. El uso del operador igual (=) podría no calificar a los visitantes para la audiencia y verá un volumen menor.</p></li><li>Añada un valor: Introduzca el ID de segmento de Audience Manager.</li></ul> |
| Agregar nueva condición | Configuración opcional. |
| En el último | Configuración opcional. |
| Nombre de audiencia | Le recomendamos que utilice el mismo nombre de segmento de Audience Manager para mantener la coherencia, a menos que agregue condiciones adicionales a esta audiencia. |

## Step 4 - Assign the Audience to a Campaign in Facebook Ads Manager {#step-4-assign-audience-to-campaign}

Después de crear la audiencia personalizada, asígnela a una campaña de publicidad. Cree una nueva campaña o edite una existente y encontrará la audiencia recién creada aparece en la interfaz de usuario de Facebook. La campaña de publicidad dirigirá a los usuarios que hayan visto el píxel en el navegador cuando visiten el sitio, si Audience Manager los incluye en el segmento.

## Resumen {#summary}

Ahora que ha asignado el segmento de Audience Manager al destino de Facebook WCA, Audience Manager activará de forma selectiva el píxel de Facebook WCA a los usuarios de un segmento determinado con el ID de segmento respectivo en el píxel para rellenar la audiencia de Facebook. Esto produce un aumento gradual en la audiencia de Facebook en el que más la etiqueta se activa a la audiencia aplicable en el sitio.

>[!NOTE]
>
> Si un usuario cae fuera del segmento de Audience Manager, actualmente no hay manera de que Audience Manager notifique a Facebook para eliminar al usuario de la audiencia personalizada.

