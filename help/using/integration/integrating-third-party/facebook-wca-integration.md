---
description: Esta página ilustra el proceso de crear píxeles de Audiencias personalizadas de sitios Web de Facebook (WCA) con el fin de enviar segmentos de audiencia de Audience Manager basados en la Web a Facebook, para direccionar anuncios en línea con transparencia mejorada.
seo-description: Esta página ilustra el proceso de crear píxeles de Audiencias personalizadas de sitios Web de Facebook (WCA) con el fin de enviar segmentos de audiencia de Audience Manager basados en la Web a Facebook, para direccionar anuncios en línea con transparencia mejorada.
seo-title: Integración de WCA de Facebook
solution: Audience Manager
title: Integración de WCA de Facebook
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Integración de WCA de Facebook {#facebook-wca-integration}

Esta página ilustra el proceso de crear píxeles de Audiencias personalizadas de sitios Web de Facebook (WCA) con el fin de enviar segmentos de audiencia de Audience Manager basados en la Web a Facebook, para direccionar anuncios en línea con transparencia mejorada.

## Información general {#overview}

[Audiencias personalizadas del sitio Web de Facebook (WCA)](https://www.facebook.com/business/help/449542958510885) permite crear una lista de personas que han visitado determinadas páginas o han realizado determinadas acciones en su sitio Web. Audience Manager permite la activación en WCA mediante destinos URL, con los que se puede configurar una integración basada en píxeles personalizados para enviar audiencias basadas en la Web a Facebook para la segmentación.

![Integración de WCA de Facebook](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Esta capacidad requiere que seleccione la audiencia de sitio Web para las plataformas sociales en [destinos URL](/help/using/features/destinations/create-url-destination.md). Las plataformas sociales requieren que la información del referente se deje sin máscara cuando se envía a su plataforma. Tenga en cuenta que esto significa que la plataforma o socio de destino podrá ver la información en su URL de referente.

## Requisitos previos {#prerequisites}

1. Cuenta de publicidad de Facebook
2. Segmentos de Audience Manager, listos para asignarse al nuevo destino de Facebook. A continuación se [muestra cómo crear un segmento](/help/using/features/segments/segment-builder.md) en la interfaz de usuario de Audience Manager.
3. Adobe Experience Cloud ID Service (ECID) versión 4.1.0 o posterior. Descargue aquí la versión **[más reciente](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. Biblioteca de integración de datos de Audience Manager (DIL) versión 9.0 o posterior, descargable desde **[aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Como alternativa, si utiliza [Reenvío de servidor (SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) para importar datos en Audience Manager, debe utilizar appmeasurement versión 2.12 o posterior. Descargue appmeasurement usando el [Administrador de códigos de Analytics](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).

Le recomendamos que instale o actualice las bibliotecas en los pasos 3 y 4 con [Adobe Launch](https://docs.adobelaunch.com/) o [la administración dinámica de etiquetas de Adobe](https://marketing.adobe.com/resources/help/en_US/dtm/).

## Paso 1: Creación de un destino de Facebook en Audience Manager {#step-1-create-facebook-destination}

Cree un nuevo destino de URL en Audience Manager y asígnele el nombre Audiencias personalizadas del sitio Web de Facebook. Utilice los ajustes siguientes al crear el destino. También puede consultar la página [Configurar una dirección URL de destino](/help/using/features/destinations/create-url-destination.md) .

**Información básica**

* **Categoría**: Personalizado
* **Tipo**: URL
* Seleccione la **casilla de** verificación Asignación de destinos de relleno automático y, a continuación, seleccione **ID de segmento**.

**Etiquetas de exportación de datos**

Seleccione la opción **Este destino puede activar una combinación con información personal (PII)**.

>[!NOTE]
>
> Esta etiqueta de exportación evita que los datos de terceros y los datos derivados de los gráficos de dispositivos se incluyan en los segmentos.

**Configuración**

* **Tipo de URL**: Seleccione **audiencia de sitio web para plataformas sociales**. Al seleccionar esta opción de tipo de URL, Audience Manager no oscurecerá la información de URL del referente al activar un píxel WCA de Facebook.
* **Serializar**: Seleccione **Habilitar**.
* En el campo URL **base** y **URL** segura, introduzca el píxel de Facebook WCA.
* **Delimitador**: ,

Ejemplo de URL base: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Se ha activado el píxel de ejemplo desde la página. Este ejemplo muestra un usuario que califica para tres segmentos de Audience Manager, con los ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Parámetro | Descripción |
---------|----------|
| `id` | Su ID de píxeles de Facebook, que se encuentra en la interfaz de usuario del Administrador de publicidad de Facebook al crear píxeles de audiencia. |
| `ev` | Evento. Este es un valor arbitrario, que aparecerá en la interfaz de usuario del Administrador de publicidad de Facebook una vez que el píxel empiece a activarse en el sitio. Consulte el elemento Incluir en [el paso 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)para obtener más información. |
| `cd[segID]` | Parámetro adicional que comenzará a rellenarse dentro de la interfaz de usuario del Administrador de publicidad de Facebook una vez que el píxel empieza a activarse en el sitio. `segID` también es arbitrario. |
| `%ALIAS%` | Una macro de Audience Manager que se reemplazará dinámicamente por los ID de segmento de Audience Manager para los que el visitante del sitio esté cualificado, delimitado por coma, |

La configuración de destino de URL debería verse en la siguiente imagen:

![Configuración de la destinación](/help/using/integration/assets/facebook-wca.png)

Guarde el destino. A continuación, puede continuar con **el paso Asignaciones** de segmentos.

## Paso 2 - Asignaciones de segmentos - Asignar segmento al destino {#step-2-segment-mappings}

En [el flujo de trabajo Configurar URL de](/help/using/features/destinations/create-url-destination.md#) destino, asigne el segmento correspondiente al destino recién creado. Observe que el valor de asignación se rellena automáticamente con el ID de segmento de Audience Manager.

Ingrese una fecha de finalización, si corresponde, y deje en blanco sin fecha de finalización.

## Paso 3: Creación de una audiencia dentro del Administrador publicitario de Facebook {#step-3-create-audience}

Consulte [Creación de una audiencia personalizada del sitio web](https://www.facebook.com/business/help/666509013483225) en la documentación de ayuda de Facebook. Seleccione las opciones Crear audiencia en la tabla siguiente:


| Elemento | Descripción |
---------|----------|
| Tráfico del sitio web | Combinación personalizada |
| Inclusión | <ul><li>Seleccione **Evento** &gt; Seleccionar **Adobe-Audience-Manager-Segment**. Este era el valor del parámetro ev en el píxel de ejemplo del paso 1. Tenga en cuenta que si el píxel aún no se ha activado, **es posible que la** opción Evento o **Adobe-Audience-Manager-Segment** no aparezcan en la interfaz de usuario de Facebook.</li><li>Agregue un parámetro: Seleccione `segID`.</li><li><p>Seleccione el operador **contiene** .</p><p>Esto es importante, teniendo en cuenta que los visitantes pueden calificar para varios segmentos, puede haber varios ID de segmento en el parámetro de píxeles. El uso del operador igual (=) podría no calificar a los visitantes para la audiencia y verá un volumen menor.</p></li><li>Añada un valor: Introduzca el ID de segmento de Audience Manager.</li></ul> |
| Agregar nueva condición | Configuración opcional. |
| En el último | Configuración opcional. |
| Nombre de audiencia | Le recomendamos que utilice el mismo nombre de segmento de Audience Manager para mantener la coherencia, a menos que agregue condiciones adicionales a esta audiencia. |

## Paso 4: Asignar la audiencia a una campaña en el administrador publicitario de Facebook {#step-4-assign-audience-to-campaign}

Después de crear la audiencia personalizada, asígnela a una campaña de publicidad. Cree una nueva campaña o edite una existente y encontrará la audiencia recién creada aparece en la interfaz de usuario de Facebook. La campaña de publicidad dirigirá a los usuarios que hayan visto el píxel en el navegador cuando visiten el sitio, si Audience Manager los incluye en el segmento.

## Resumen {#summary}

Ahora que ha asignado el segmento de Audience Manager al destino de Facebook WCA, Audience Manager activará de forma selectiva el píxel de Facebook WCA a los usuarios de un segmento determinado con el ID de segmento respectivo en el píxel para rellenar la audiencia de Facebook. Esto produce un aumento gradual en la audiencia de Facebook en el que más la etiqueta se activa a la audiencia aplicable en el sitio.

>[!NOTE]
>
> Si un usuario cae fuera del segmento de Audience Manager, actualmente no hay manera de que Audience Manager notifique a Facebook para eliminar al usuario de la audiencia personalizada.

