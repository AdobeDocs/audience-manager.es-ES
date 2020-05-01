---
description: Información general sobre DIL y cómo funciona.
seo-description: Información general sobre DIL y cómo funciona.
seo-title: Explicación de la biblioteca de integración de datos (DIL)
keywords: dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil,
solution: Audience Manager
title: Explicación de la biblioteca de integración de datos (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Explicación de la biblioteca de integración de datos (DIL){#understanding-the-data-integration-library-dil}

Información general, introducción y métodos de código disponibles en la biblioteca de códigos DIL del Administrador de Audiencias.

>[!IMPORTANT]
>
>A partir de la versión 8.0 (publicada en agosto de 2018), [!UICONTROL DIL] tiene una dependencia sólida de [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html), versión 3.3 o superior. Depende del servicio de ID para activar sincronizaciones de ID y destinos de URL. Se produce un error si falta el servicio de ID, es antiguo o no está configurado.
>
>Le recomendamos que utilice Adobe Experience Platform Launch para implementar y administrar sus bibliotecas DIL y Adobe Experience Platform Identity Service.

Sin embargo, también puede descargar las últimas versiones de Experience Cloud y DIL desde nuestra página de GitHub. Consulte los vínculos de descarga siguientes:

* Descargar el servicio de identidad de [Adobe Experience Platform](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Descargar [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Objetivo del DIL {#purpose-dil}

[!UICONTROL DIL] es una biblioteca de API. Pueden pensarlo como un cuerpo de código de ayuda para [!DNL Adobe Audience Manager]. No es necesario usarla [!DNL Audience Manager], pero los métodos y funciones [!UICONTROL DIL] proporcionan medios que no necesita desarrollar su propio código para enviar datos a [!DNL Audience Manager]. Además, [!UICONTROL DIL] es diferente de la API proporcionada por el servicio [de identidad de la plataforma de](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience Platform. Ese servicio está diseñado para administrar la identidad de visitante en diferentes [!DNL Experience Cloud] soluciones. Por el contrario, [!UICONTROL DIL] está diseñado para:

* Realice llamadas de evento y envíe datos al servidor [de recopilación de datos](../reference/system-components/components-data-collection.md).
* Enviar datos a [destinos](../features/destinations/destinations.md).

## Obtención e implementación de código DIL {#get-implement-dil-code}

[!UICONTROL DIL] está disponible para su descarga **[aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Tenga en cuenta que, a partir de la versión 8.0 (publicada en agosto de 2018),[!UICONTROL DIL]tiene una fuerte dependencia del servicio[de identidad de la plataforma de experiencia de](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe, versión 3.3 o superior. Depende del servicio de ID para activar sincronizaciones de ID y destinos de URL. Se produce un error si falta el servicio de ID, es antiguo o no está configurado.

En lugar de trabajar [!UICONTROL DIL] y configurarse [!DNL Audience Manager] manualmente, le recomendamos que utilice [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) . [!DNL Adobe Experience Platform Launch] es la herramienta de implementación recomendada, ya que simplifica la implementación, colocación y administración de versiones del código. Obtenga más información sobre la extensión [Administrador de](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) Audiencias en Adobe Experience Platform Launch.

Adobe Experience Platform Launch es el sucesor del Administrador [dinámico de etiquetas de](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html) Adobe ([!DNL DTM]).

## Llamada de muestra {#sample-code}

[!UICONTROL DIL] envía datos a [!DNL Audience Manager] en una llamada de evento. Una llamada de evento es una solicitud HTTP XML de la página. Utiliza un `POST` método para enviar datos en el cuerpo de la solicitud.

| Elemento Llamada de Evento | Descripción |
|--- |--- |
| URL | Las llamadas DIL evento utilizan la siguiente sintaxis: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Cuerpo | Como se muestra en el ejemplo siguiente, DIL pasa los datos como pares clave-valor. Los caracteres de prefijo especial identifican los pares clave-valor como el Administrador de Audiencias o las variables de socio.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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