---
description: Información general sobre DIL y su funcionamiento.
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil
solution: Audience Manager
title: Explicación de la biblioteca de integración de datos (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 10%

---

# Explicación de la [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

>[!WARNING]
>
>A partir de julio de 2023, el Adobe ha interrumpido el desarrollo del [!DNL Data Integration Library (DIL)] y el [!DNL DIL] extensión.
>
>Los clientes existentes pueden seguir utilizando su [!DNL DIL] implementación. Sin embargo, el Adobe no se desarrollará [!DNL DIL] más allá de este punto. Se recomienda a los clientes que evalúen [SDK web de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) para su estrategia de recopilación de datos a largo plazo.
>
>Los clientes que deseen implementar nuevas integraciones de recopilación de datos a partir de julio de 2023 deben utilizar [SDK web de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) en su lugar.

Información general, introducción y métodos de código disponibles en la [!DNL Audience Manager DIL] biblioteca de códigos.

>[!IMPORTANT]
>
>A partir de la versión 8.0 (lanzada en agosto de 2018), [!UICONTROL DIL] tiene una fuerte dependencia del [Servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html), versión 3.3 o superior. Se basa en la variable [!DNL ID Service] para activar sincronizaciones de ID y destinos de URL. Se produce un error si la variable [!DNL ID Service] falta, es antigua o no está configurada.
>
>Le recomendamos que utilice [!DNL Adobe Experience Platform Tags] para implementar y administrar su [!DNL DIL] y [!DNL Adobe Experience Platform Identity Service] bibliotecas.

Sin embargo, también puede descargar el Experience Cloud más reciente y [!DNL DIL] Versiones de nuestra página de GitHub. Consulte los vínculos de descarga a continuación:

* Descargue la [Servicio de identidad de Adobe Experience Platform](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Descargar [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Finalidad del DIL {#purpose-dil}

[!UICONTROL DIL] es una biblioteca de API de. Se puede considerar como un cuerpo de código de ayuda para [!DNL Adobe Audience Manager]. No es necesario utilizar [!DNL Audience Manager], pero los métodos y funciones [!UICONTROL DIL] proporciona significa que no tiene que desarrollar su propio código para enviar datos a [!DNL Audience Manager]. Además, [!UICONTROL DIL] es diferente a la API proporcionada por [Servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html). Ese servicio está diseñado para administrar la identidad de los visitantes en diferentes [!DNL Experience Cloud] soluciones. Por el contrario, [!UICONTROL DIL] está diseñado para:

* Realizar llamadas de evento y enviar datos a [Servidor de recopilación de datos](../reference/system-components/components-data-collection.md).
* Envío de datos a [destinos](../features/destinations/destinations.md).

## Obtención e implementación del código de DIL {#get-implement-dil-code}

[!UICONTROL DIL] el código está disponible para descargar **[aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Tenga en cuenta que a partir de la versión 8.0 (lanzada en agosto de 2018), [!UICONTROL DIL] tiene una fuerte dependencia del [Servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html), versión 3.3 o superior. Se basa en la variable [!DNL ID Service] para activar sincronizaciones de ID y [!DNL URL destinations]. Se produce un error si la variable [!DNL ID Service] falta, es antigua o no está configurada.

En lugar de trabajar con [!UICONTROL DIL] y configurar [!DNL Audience Manager] manualmente, le recomendamos que utilice [Etiquetas de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) en su lugar. [!DNL Adobe Experience Platform Tags] es la herramienta de implementación recomendada porque simplifica la implementación, la ubicación y la administración de versiones del código. Más información sobre la [Extensión de Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) in [!DNL Adobe Experience Platform Tags].

## Ejemplo de llamada {#sample-code}

[!UICONTROL DIL] envía datos a [!DNL Audience Manager] en una llamada de evento. Una llamada de evento es una solicitud HTTP XML desde la página. Utiliza un `POST` para enviar datos en el cuerpo de la solicitud.

| Elemento de llamada de evento | Descripción |
|--- |--- |
| URL | Las llamadas de evento de DIL utilizan la siguiente sintaxis: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Cuerpo | Como se muestra en el ejemplo siguiente, DIL pasa los datos como pares clave-valor. Los caracteres de prefijo especiales identifican los pares clave-valor como variables de Audience Manager o socio.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Consulte también:
* [Requisitos de prefijo para variables clave](../features/traits/trait-variable-prefixes.md)
* [Atributos admitidos para llamadas a la API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Vínculos relacionados

* [Casos de uso DIL y ejemplos de código](/help/using/dil/dil-use-cases.md)
* [Métodos DIL de nivel de clase ](/help/using/dil/dil-class-overview/dil-start.md)
* [Métodos DIL de nivel de instancia](/help/using/dil/dil-instance-methods.md)
* [Módulos DIL](/help/using/dil/dil-modules.md)
* [Herramientas DIL](/help/using/dil/dil-tools.md)
* [DIL Flash](/help/using/dil/dil-flash.md)
