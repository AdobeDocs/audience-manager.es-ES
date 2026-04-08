---
description: Información general sobre DIL y su funcionamiento.
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil
solution: Audience Manager
title: Explicación de Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
TQID: https://experienceleague.adobe.com/SyaOtcmDa6IwaoPVjv-G6zvdnFa7ZVDaGP7MaX4RaBk
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2:
  - id: d7e573ad-4eda-46ec-90c4-239e75362af9
  - id: f8c1669e-86ba-49c4-b622-9dfa07854df8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 473
ht-degree: 1%

---

# Explicación de [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

>[!WARNING]
>
>Desde julio de 2023, Adobe ha interrumpido el desarrollo de la extensión [!DNL Data Integration Library (DIL)] y [!DNL DIL].
>
>Los clientes existentes pueden seguir usando su implementación de [!DNL DIL]. Sin embargo, Adobe no desarrollará [!DNL DIL] más allá de este punto. Se recomienda a los clientes evaluar [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) para su estrategia de recopilación de datos a largo plazo.
>
>Los clientes que deseen implementar nuevas integraciones de recopilación de datos a partir de julio de 2023 deben utilizar [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) en su lugar.

Información general, introducción y métodos de código disponibles en la biblioteca de código [!DNL Audience Manager DIL].

>[!IMPORTANT]
>
>A partir de la versión 8.0 (lanzada en agosto de 2018), [!UICONTROL DIL] depende en gran medida del [servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html), versión 3.3 o superior. Se basa en [!DNL ID Service] para activar sincronizaciones de ID y destinos de URL. Se produce un error si falta [!DNL ID Service], es antiguo o no está configurado.
>
>Le recomendamos que use [!DNL Adobe Experience Platform Tags] para implementar y administrar sus bibliotecas de [!DNL DIL] y [!DNL Adobe Experience Platform Identity Service].

Sin embargo, también puede descargar las últimas versiones de Experience Cloud y [!DNL DIL] desde nuestra página de GitHub. Consulte los vínculos de descarga a continuación:

* Descargar el [servicio de identidad de Adobe Experience Platform](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Descargar [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Finalidad de DIL {#purpose-dil}

[!UICONTROL DIL] es una biblioteca de API. Se puede considerar como un cuerpo de código de ayuda para [!DNL Adobe Audience Manager]. No es necesario usar [!DNL Audience Manager], pero los métodos y funciones que [!UICONTROL DIL] proporciona significan que no tiene que desarrollar su propio código para enviar datos a [!DNL Audience Manager]. Además, [!UICONTROL DIL] es diferente a la API proporcionada por el [servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html). Ese servicio está diseñado para administrar la identidad de los visitantes en diferentes soluciones de [!DNL Experience Cloud]. Por el contrario, [!UICONTROL DIL] está diseñado para:

* Realice llamadas de evento y envíe datos al [servidor de recopilación de datos](../reference/system-components/components-data-collection.md).
* Enviar datos a [destinos](../features/destinations/destinations.md).

## Obtención e implementación de código DIL {#get-implement-dil-code}

El código de [!UICONTROL DIL] está disponible para la descarga **[aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Tenga en cuenta que a partir de la versión 8.0 (lanzada en agosto de 2018), [!UICONTROL DIL] depende en gran medida del [servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html), versión 3.3 o superior. Se basa en [!DNL ID Service] para activar las sincronizaciones de ID y [!DNL URL destinations]. Se produce un error si falta [!DNL ID Service], es antiguo o no está configurado.

En lugar de trabajar con [!UICONTROL DIL] y configurar [!DNL Audience Manager] manualmente, le recomendamos que utilice [Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html). [!DNL Adobe Experience Platform Tags] es la herramienta de implementación recomendada porque simplifica la implementación, la ubicación y la administración de versiones del código. Obtenga más información sobre la [extensión de Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) en [!DNL Adobe Experience Platform Tags].

## Ejemplo de llamada {#sample-code}

[!UICONTROL DIL] envía datos a [!DNL Audience Manager] en una llamada de evento. Una llamada de evento es una solicitud HTTP XML desde la página. Utiliza un método `POST` para enviar datos en el cuerpo de la solicitud.

| Elemento de llamada de evento | Descripción |
|--- |--- |
| URL | Las llamadas de evento de DIL utilizan la siguiente sintaxis: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Cuerpo | Como se muestra en el ejemplo siguiente, DIL pasa los datos como pares clave-valor. Los caracteres de prefijo especial identifican los pares clave-valor como variables de Audience Manager o de socio.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Consulte también:

* [Requisitos de prefijo para variables clave](../features/traits/trait-variable-prefixes.md)
* [Atributos admitidos para llamadas a la API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Vínculos relacionados

* [Casos de uso de DIL y ejemplos de código](/help/using/dil/dil-use-cases.md)
* [Métodos DIL de nivel de clase](/help/using/dil/dil-class-overview/dil-start.md)
* [Métodos DIL de nivel de instancia](/help/using/dil/dil-instance-methods.md)
* [Módulos DIL](/help/using/dil/dil-modules.md)
* [Herramientas de DIL](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)
