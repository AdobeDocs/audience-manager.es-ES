---
description: Esta página ilustra el proceso de creación de píxeles de Audiencias personalizadas (WCA) del sitio web de Facebook con el fin de enviar segmentos de audiencia de Audience Manager basados en web a Facebook, para la segmentación de anuncios en línea con una transparencia mejorada.
seo-description: Esta página ilustra el proceso de creación de píxeles de Audiencias personalizadas (WCA) del sitio web de Facebook con el fin de enviar segmentos de audiencia de Audience Manager basados en web a Facebook, para la segmentación de anuncios en línea con una transparencia mejorada.
seo-title: Integración de WCA de Facebook
solution: Audience Manager
title: Integración de WCA de Facebook
translation-type: tm+mt
source-git-commit: 28d1292140a56cf1627a8921876d9483221876ca

---


# Integración de WCA de Facebook {#facebook-wca-integration}

Esta página ilustra el proceso de creación de píxeles de Audiencias personalizadas (WCA) del sitio web de Facebook con el fin de enviar segmentos de audiencia de Audience Manager basados en web a Facebook, para la segmentación de anuncios en línea con una transparencia mejorada.

## Información general {#overview}

[Audiencias personalizadas del sitio web de Facebook (WCA)](https://www.facebook.com/business/help/449542958510885) le permite crear una lista de personas que han visitado determinadas páginas o han realizado determinadas acciones en el sitio web. Audience Manager habilita la activación en WCA mediante destinos URL, con los que puede configurar una integración personalizada basada en píxeles para enviar audiencias basadas en web a Facebook para su segmentación.

![Integración de WCA de Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Esta capacidad requiere que seleccione la opción Audiencia de sitio web para plataformas sociales en destinos [](/help/using/features/destinations/create-url-destination.md)URL. Las plataformas sociales requieren que la información del referente se desenmascara cuando se envía a su plataforma. Tenga en cuenta que esto significa que la plataforma o socio de destino podrá ver la información en la dirección URL del referente.

## Requisitos previos {#prerequisites}

1. Cuenta de publicidad de Facebook
2. Segmentos de Audience Manager, listos para asignar a su nuevo destino de Facebook. A continuación se muestra [cómo crear un segmento](/help/using/features/segments/segment-builder.md) en la interfaz de usuario de Audience Manager.
3. Servicio de ID de Adobe Experience Cloud (ECID) versión 4.1.0 o posterior. Descargue la última versión **[aquí](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. Biblioteca de integración de datos de Audience Manager (DIL) versión 9.0 o posterior, descargable desde **[aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Como alternativa, si utiliza el reenvío [del lado del servidor (SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) para importar datos en Audience Manager, debe utilizar AppMeasurement versión 2.12 o posterior. Descargue AppMeasurement con el Administrador [de códigos de](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)Analytics.

Le recomendamos que instale o actualice las bibliotecas en los pasos 3 y 4 mediante [Adobe Launch](https://docs.adobelaunch.com/) o la administración [dinámica de etiquetas de](https://marketing.adobe.com/resources/help/en_US/dtm/)Adobe.

## Paso 1: Creación de un destino de Facebook en Audience Manager {#step-1-create-facebook-destination}

Cree un nuevo destino de URL en Audience Manager y asígnele el nombre Audiencias personalizadas del sitio web de Facebook. Utilice la configuración siguiente al crear el destino. También puede consultar la página [Configurar un destino](/help/using/features/destinations/create-url-destination.md) de URL.

**Información básica**

* **Categoría**: Personalizado
* **Tipo**: URL
* Active la casilla de verificación **Rellenar automáticamente Asignación** de destino y, a continuación, seleccione ID **de segmento**.

**Etiquetas de exportación de datos**

Seleccione la opción **Este destino puede habilitar una combinación con información de identificación personal (PII)**.

>[!NOTE]
>
> Esta etiqueta de exportación evita que los datos y datos derivados de gráficos de dispositivos se incluyan en los segmentos.

**Configuración**

* **Tipo** de dirección URL: Seleccione la audiencia **del sitio web para las plataformas** sociales. Al seleccionar esta opción de tipo de URL, Audience Manager no oculta la información de URL del referente al activar un píxel WCA de Facebook.
* **Serializar**: Seleccione **Habilitar**.
* En el campo URL **** base y URL **** segura, introduzca el píxel WCA de Facebook.
* **Delimitador**: ,

Ejemplo de URL base: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Ejemplo de píxel activado desde la página. Este ejemplo muestra un usuario que cumple los requisitos para tres segmentos de Audience Manager, con los ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Parámetro | Descripción |
---------|----------|
| `id` | Su ID de píxel de Facebook, que puede encontrar en la interfaz de usuario del administrador de publicidad de Facebook al crear píxeles de audiencia. |
| `ev` | Evento. Se trata de un valor arbitrario que aparecerá en la interfaz de usuario del administrador de publicidad de Facebook una vez que el píxel se active en el sitio. Consulte el elemento Incluir en el [paso 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)para obtener más información. |
| `cd[segID]` | Parámetro adicional que comenzará a rellenarse en la interfaz de usuario del administrador de publicidad de Facebook una vez que el píxel comience a activarse en el sitio. `segID` también es arbitraria. |
| `%ALIAS%` | Una macro de Audience Manager, que se reemplazará dinámicamente con los ID de segmento de Audience Manager para los que el visitante del sitio califica, delimitada por comas, |

La configuración de destino de la dirección URL debería verse en la siguiente imagen:

![Configuración de destino](/help/using/integration/assets/facebook-wca.png)

Guarde el destino. A continuación, puede continuar con el paso Asignaciones **de segmentos** .

## Paso 2: Asignaciones de segmentos - Asignar segmento al destino {#step-2-segment-mappings}

En el flujo de trabajo [Configurar destino](/help/using/features/destinations/create-url-destination.md) de URL, asigne el segmento aplicable al destino recién creado. Observe que el valor de asignación se rellena automáticamente con el ID de segmento de Audience Manager.

Introduzca una fecha de finalización, si corresponde; de lo contrario, deje en blanco sin fecha de finalización.

## Paso 3: Crear una audiencia dentro del Administrador de publicidades de Facebook {#step-3-create-audience}

Consulte [Crear una audiencia](https://www.facebook.com/business/help/666509013483225) personalizada de sitio web en la documentación de ayuda de Facebook. Seleccione las opciones Crear audiencia en la tabla siguiente:


| Elemento | Descripción |
---------|----------|
| Tráfico del sitio web | Combinación personalizada |
| Inclusión | <ul><li>Seleccione **Evento** &gt; Seleccione **Adobe-Audience-Manager-Segment**. Este era el valor del parámetro ev en el píxel de ejemplo del paso 1. Tenga en cuenta que si el píxel aún no se ha activado, es posible que la opción **Evento** o **Adobe-Audience-Manager-Segment** no aparezcan en la interfaz de usuario de Facebook.</li><li>Agregue un parámetro: Seleccione `segID`.</li><li><p>Seleccione el operador **contiene** .</p><p>Esto es importante, teniendo en cuenta que los visitantes pueden cumplir los requisitos para varios segmentos, puede haber varios ID de segmento en el parámetro pixel. Es posible que el uso del operador igual (=) no califique a los visitantes para la audiencia y que observe un volumen menor.</p></li><li>Agregar un valor: Introduzca el ID de segmento de Audience Manager.</li></ul> |
| Agregar nueva condición | Configuración opcional. |
| En el último | Configuración opcional. |
| Nombre de audiencia | Le recomendamos que utilice el mismo nombre de segmento de Audience Manager para mantener la coherencia, a menos que agregue condiciones adicionales a esta audiencia. |

## Paso 4: Asignar la audiencia a una campaña en el Administrador de publicidades de Facebook {#step-4-assign-audience-to-campaign}

Después de crear la audiencia personalizada, asígnela a una campaña de publicidad. Cree una nueva campaña o edite una existente y encontrará que la audiencia recién creada aparece en la interfaz de usuario de Facebook. La campaña de publicidad se dirigirá a los usuarios que hayan visto el incendio de píxeles en el explorador al visitar el sitio, si Audience Manager los incluye en el segmento.

## Resumen {#summary}

Ahora que ha asignado el segmento de Audience Manager al destino WCA de Facebook, Audience Manager activará de forma selectiva el píxel WCA de Facebook para los usuarios de un segmento determinado con el ID de segmento correspondiente en píxeles para rellenar la audiencia de Facebook. Esto resulta en un aumento gradual en la audiencia de Facebook cuanto más se activa la etiqueta a la audiencia aplicable en su sitio.

>[!NOTE]
>
> Si un usuario se encuentra fuera del segmento de Audience Manager, Audience Manager no puede informar a Facebook para que elimine al usuario de la audiencia personalizada.

