---
description: Información general sobre DIL y cómo funciona.
seo-description: Información general sobre DIL y cómo funciona.
seo-title: Explicación de la biblioteca de integración de datos (DIL)
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, di, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil '
solution: Audience Manager
title: Explicación de la biblioteca de integración de datos (DIL)
uuid: 77 b 12 f 35-81 e 4-4639-ada 6-bf 982 f 27 b 36 e
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Explicación de la biblioteca de integración de datos (DIL){#understanding-the-data-integration-library-dil}

Información general, introducción y métodos de código disponibles en la biblioteca de código DIL de Audience Manager.

>[!IMPORTANT]
>
>Starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Depende del servicio de ID para activar sincronizaciones de ID y destinos URL. Se produce un error si falta el servicio de ID, antiguo o no está configurado.
>
>Le recomendamos utilizar Adobe Launch para implementar y gestionar sus bibliotecas de servicio DIL y Experience Cloud ID.

Sin embargo, también puede descargar las versiones más recientes de Experience Cloud y DIL desde nuestra página de github. Consulte vínculos de descarga a continuación:

* Descargar [el servicio Experience Cloud ID](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Descargar [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Objetivo de DIL {#purpose-dil}

[!UICONTROL DIL] es una biblioteca de API. Puede pensarlo como cuerpo del código de ayuda para [!DNL Adobe Audience Manager]. No es necesario utilizar [!DNL Audience Manager], pero los métodos y funciones [!UICONTROL DIL] proporcionan significa que no es necesario desarrollar su propio código para enviar datos. [!DNL Audience Manager] Además, [!UICONTROL DIL] es diferente a la API proporcionada por [el servicio Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/). Este servicio está diseñado para administrar la identidad de los visitantes en [!DNL Experience Cloud] distintas soluciones. Por el contrario, [!UICONTROL DIL] está diseñado para:

* Hacer llamadas de evento y enviar datos al servidor de recopilación [de datos](../reference/system-components/components-data-collection.md).
* Enviar datos a [los destinos](../features/destinations/destinations.md).

## Obtención e implementación de código DIL {#get-implement-dil-code}

[!UICONTROL DIL] el código está disponible para su descarga **[aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Please note that starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Depende del servicio de ID para activar sincronizaciones de ID y destinos URL. Se produce un error si falta el servicio de ID, antiguo o no está configurado.

En lugar de trabajar [!UICONTROL DIL] con y configurar [!DNL Audience Manager] manualmente, le recomendamos que utilice [Adobe Launch](https://docs.adobelaunch.com/) en su lugar. [!DNL Adobe Launch] es la herramienta de implementación recomendada porque simplifica la implementación del código, la ubicación y la administración de versiones. Obtenga más información sobre la extensión [de Audience Manager](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) en Adobe Launch.

Adobe Launch es el sucesor del [Administrador dinámico de etiquetas de Adobe](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]).

## Llamada de muestra {#sample-code}

[!UICONTROL DIL] envía datos a [!DNL Audience Manager] una llamada de evento. Una llamada de evento es una solicitud HTTP XML de su página. Utiliza un `POST` método para enviar datos en el cuerpo de la solicitud.

| Elemento Llamada de evento | Descripción |
|--- |--- |
| URL | Las llamadas de evento DIL utilizan la siguiente sintaxis: `https://adobe.demdex.net/event?_ts =`*`UNIX UTC timestamp`* |
| Cuerpo | Como se muestra en la muestra siguiente, DIL pasa los datos como pares clave-valor. Los caracteres de prefijo especiales identifican los pares clave-valor como variables de socios o de Audience Manager.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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