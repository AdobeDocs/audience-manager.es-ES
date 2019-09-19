---
description: Información general sobre DIL y cómo funciona.
seo-description: Información general sobre DIL y cómo funciona.
seo-title: ' Explicación de la biblioteca de integración de datos (DIL)'
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil l, '
solution: Audience Manager
title: ' Explicación de la biblioteca de integración de datos (DIL)'
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


#  Explicación de la biblioteca de integración de datos (DIL){#understanding-the-data-integration-library-dil}

Información general, introducción y métodos de código disponibles en la biblioteca de códigos DIL de Audience Manager.

>[!IMPORTANT]
>
>Starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Depende del servicio de ID para activar sincronizaciones de ID y destinos de URL. Se produce un error si falta el servicio de ID, es antiguo o no está configurado.
>
>Le recomendamos que utilice Adobe Launch para implementar y administrar sus bibliotecas DIL y del servicio de ID de Experience Cloud.

Sin embargo, también puede descargar las últimas versiones de Experience Cloud y DIL desde nuestra página de GitHub. Consulte los vínculos de descarga siguientes:

* Descargar el servicio [Experience Cloud ID](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Descargar [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Objetivo del DIL {#purpose-dil}

[!UICONTROL DIL] es una biblioteca de API. Pueden pensarlo como un cuerpo de código de ayuda para [!DNL Adobe Audience Manager]. No es necesario usarla [!DNL Audience Manager], pero los métodos y funciones [!UICONTROL DIL] proporcionan medios que no necesita desarrollar su propio código para enviar datos a [!DNL Audience Manager]. Además, [!UICONTROL DIL] es diferente de la API proporcionada por el servicio [de ID de](https://marketing.adobe.com/resources/help/en_US/mcvid/)Experience Cloud. Ese servicio está diseñado para administrar la identidad del visitante en diferentes [!DNL Experience Cloud] soluciones. Por el contrario, [!UICONTROL DIL] está diseñado para:

* Realice llamadas de evento y envíe datos al servidor [de recopilación de datos](../reference/system-components/components-data-collection.md).
* Enviar datos a [destinos](../features/destinations/destinations.md).

## Obtención e implementación de código DIL {#get-implement-dil-code}

[!UICONTROL DIL] está disponible para su descarga **[aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Please note that starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Depende del servicio de ID para activar sincronizaciones de ID y destinos de URL. Se produce un error si falta el servicio de ID, es antiguo o no está configurado.

En lugar de trabajar [!UICONTROL DIL] y configurarse [!DNL Audience Manager] manualmente, le recomendamos que utilice [Adobe Launch](https://docs.adobelaunch.com/) en su lugar. [!DNL Adobe Launch] es la herramienta de implementación recomendada, ya que simplifica la implementación, colocación y administración de versiones del código. Obtenga más información sobre la extensión [de](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) Audience Manager en Adobe Launch.

Adobe Launch es el sucesor de [Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]).

## Llamada de muestra {#sample-code}

[!UICONTROL DIL] envía datos a [!DNL Audience Manager] en una llamada de evento. Una llamada de evento es una solicitud HTTP XML de la página. Utiliza un `POST` método para enviar datos en el cuerpo de la solicitud.

| Elemento de llamada de evento | Descripción |
|--- |--- |
| URL | Las llamadas a eventos DIL utilizan la siguiente sintaxis: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Cuerpo | Como se muestra en el ejemplo siguiente, DIL pasa los datos como pares clave-valor. Los caracteres de prefijo especial identifican los pares clave-valor como variables de Audience Manager o de socio.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Consulte también:
* [Requisitos de prefijo para variables clave](../features/traits/trait-variable-prefixes.md)
* [Atributos admitidos para llamadas de API de DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Vínculos relacionados

* [Casos de uso DIL y ejemplos de código](/help/using/dil/dil-use-cases.md)
* [Métodos DIL de nivel de clase](/help/using/dil/dil-class-overview/dil-start.md)
* [Métodos DIL de nivel de instancia](/help/using/dil/dil-instance-methods.md)
* [Módulos DIL](/help/using/dil/dil-modules.md)
* [Herramientas DIL](/help/using/dil/dil-tools.md)
* [DIL Flash](/help/using/dil/dil-flash.md)