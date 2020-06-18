---
description: Información general sobre DIL y cómo funciona.
seo-description: Información general sobre DIL y cómo funciona.
seo-title: Explicación de la biblioteca de integración de datos (DIL)
keywords: dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil,
solution: Audience Manager
title: Explicación de la biblioteca de integración de datos (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
translation-type: tm+mt
source-git-commit: ef098c35da49ae663d201b9b7f96034fb5c76323
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 2%

---


# Explicación de la [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

Información general, introducción y métodos de código disponibles en la biblioteca de [!DNL Audience Manager DIL] códigos.

>[!IMPORTANT]
>
>A partir de la versión 8.0 (publicada en agosto de 2018), [!UICONTROL DIL] tiene una dependencia sólida del servicio [de identidad de](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience Platform, versión 3.3 o superior. Se basa en el [!DNL ID Service] para activar sincronizaciones de ID y destinos de URL. Se produce un error si [!DNL ID Service] falta, es antiguo o no está configurado.
>
>Le recomendamos que utilice [!DNL Adobe Experience Platform Launch] para implementar y administrar sus [!DNL DIL] y [!DNL Adobe Experience Platform Identity Service] bibliotecas.

Sin embargo, también puede descargar el Experience Cloud y las [!DNL DIL] versiones más recientes desde nuestra página de GitHub. Consulte los vínculos de descarga siguientes:

* Descargar el servicio [Adobe Experience Platform Identity](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Descargar [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Objetivo del DIL {#purpose-dil}

[!UICONTROL DIL] es una biblioteca de API. Pueden pensarlo como un cuerpo de código de ayuda para [!DNL Adobe Audience Manager]. No es necesario usarla [!DNL Audience Manager], pero los métodos y funciones [!UICONTROL DIL] proporcionan medios que no necesita desarrollar su propio código para enviar datos a [!DNL Audience Manager]. Además, [!UICONTROL DIL] es diferente de la API proporcionada por el servicio [de identidad de](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience Platform. Ese servicio está diseñado para administrar la identidad de visitante en diferentes [!DNL Experience Cloud] soluciones. Por el contrario, [!UICONTROL DIL] está diseñado para:

* Realice llamadas de evento y envíe datos al servidor [de recopilación de datos](../reference/system-components/components-data-collection.md).
* Enviar datos a [destinos](../features/destinations/destinations.md).

## Obtención e implementación de código DIL {#get-implement-dil-code}

[!UICONTROL DIL] está disponible para su descarga **[aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Tenga en cuenta que, a partir de la versión 8.0 (publicada en agosto de 2018),[!UICONTROL DIL]tiene una fuerte dependencia del servicio[de identidad de](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience Platform, versión 3.3 o superior. Se basa en el[!DNL ID Service]para activar sincronizaciones de ID y[!DNL URL destinations]. Se produce un error si[!DNL ID Service]falta, es antiguo o no está configurado.

En lugar de trabajar [!UICONTROL DIL] y configurarse [!DNL Audience Manager] manualmente, le recomendamos que utilice Iniciar [Adobe Experience Platform](https://docs.adobelaunch.com/) en su lugar. [!DNL Adobe Experience Platform Launch] es la herramienta de implementación recomendada, ya que simplifica la implementación, colocación y administración de versiones del código. Obtenga más información sobre la extensión [del](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) Audience Manager en [!DNL Adobe Experience Platform Launch].

[!DNL Adobe Experience Platform Launch] es el sucesor del Administrador [dinámico de etiquetas de](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html) Adobe ([!DNL DTM]).

## Llamada de muestra {#sample-code}

[!UICONTROL DIL] envía datos a [!DNL Audience Manager] en una llamada de evento. Una llamada de evento es una solicitud HTTP XML de la página. Utiliza un `POST` método para enviar datos en el cuerpo de la solicitud.

| Elemento Llamada de Evento | Descripción |
|--- |--- |
| URL | Las llamadas DIL evento utilizan la siguiente sintaxis: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Cuerpo | Como se muestra en el ejemplo siguiente, DIL pasa los datos como pares clave-valor. Los caracteres de prefijo especial identifican los pares clave-valor como variables de Audience Manager o socio.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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