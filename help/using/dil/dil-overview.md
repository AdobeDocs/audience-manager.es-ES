---
description: Información general sobre DIL y cómo funciona.
seo-description: Información general sobre DIL y cómo funciona.
seo-title: Explicación de la biblioteca de integración de datos (DIL)
solution: Audience Manager
title: Explicación de la biblioteca de integración de datos (DIL)
uuid: 77 b 12 f 35-81 e 4-4639-ada 6-bf 982 f 27 b 36 e
translation-type: tm+mt
source-git-commit: 8f2cbf8a31335762f03cad278114d9ab7c520763

---


# Understanding the Data Integration Library (DIL){#understanding-the-data-integration-library-dil}

Información general, introducción y métodos de código disponibles en la biblioteca de código DIL de Audience Manager.

>[!IMPORTANT]
>
>Starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Depende del servicio de ID para activar sincronizaciones de ID y destinos URL. Se produce un error si falta el servicio de ID, antiguo o no está configurado.
>
>Le recomendamos utilizar Adobe Launch para implementar y gestionar sus bibliotecas de servicio DIL y Experience Cloud ID.

Sin embargo, también puede descargar las versiones más recientes de Experience Cloud y DIL desde nuestra página de github. Consulte vínculos de descarga a continuación:

* Download the [Experience Cloud ID Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Download [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Purpose of DIL {#purpose-dil}

[!UICONTROL DIL] es una biblioteca de API. You can think it as a body of helper code for [!DNL Adobe Audience Manager]. It is not required to use [!DNL Audience Manager], but the methods and functions [!UICONTROL DIL] provides means you don&#39;t have to develop your own code to send data to [!DNL Audience Manager]. Also, [!UICONTROL DIL] is different than the API provided by the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/). That service is designed to manage visitor identity across different [!DNL Experience Cloud] solutions. By contrast, [!UICONTROL DIL] is designed to:

* Make event calls and send data to the [Data Collection Server](../reference/system-components/components-data-collection.md).
* Send data to [destinations](../features/destinations/destinations.md).

## Getting and Implementing DIL Code {#get-implement-dil-code}

[!UICONTROL DIL] el código está disponible para su descarga **[aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Please note that starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Depende del servicio de ID para activar sincronizaciones de ID y destinos URL. Se produce un error si falta el servicio de ID, antiguo o no está configurado.

Rather than work with [!UICONTROL DIL] and set up [!DNL Audience Manager] manually, we recommend that you use [Adobe Launch](https://docs.adobelaunch.com/) instead. [!DNL Adobe Launch] es la herramienta de implementación recomendada porque simplifica la implementación del código, la ubicación y la administración de versiones. Read more about the [Audience Manager extension](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) in Adobe Launch.

Adobe Launch is the successor to [Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]).

## Sample Call {#sample-code}

[!UICONTROL DIL] envía datos a [!DNL Audience Manager] una llamada de evento. Una llamada de evento es una solicitud HTTP XML de su página. It uses a `POST` method to send data in the body of the request.

| Elemento Llamada de evento | Descripción |
|--- |--- |
| URL | DIL event calls use the following syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Cuerpo | Como se muestra en la muestra siguiente, DIL pasa los datos como pares clave-valor. Special prefix characters identify the key-value pairs as Audience Manager or partner variables.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Consulte también:
* [Requisitos de prefijo para variables clave](../features/traits/trait-variable-prefixes.md)
* [Atributos admitidos para llamadas de API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Vínculos relacionados

* [Casos de uso DIL y Muestras de código](/help/using/dil/dil-use-cases.md)
* [Métodos DIL de nivel de clase](/help/using/dil/dil-class-overview/dil-start.md)
* [Métodos DIL de nivel de instancia](/help/using/dil/dil-instance-methods.md)
* [Módulos DIL](/help/using/dil/dil-modules.md)
* [Herramientas DIL](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)