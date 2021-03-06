---
description: Información general sobre el DIL y su funcionamiento.
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil l, '
solution: Audience Manager
title: Explicación de la biblioteca de integración de datos (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 11%

---

# Información sobre [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

Información general, introducción y métodos de código disponibles en la [!DNL Audience Manager DIL] biblioteca de códigos.

>[!IMPORTANT]
>
>A partir de la versión 8.0 (publicada en agosto de 2018), [!UICONTROL DIL] tiene una fuerte dependencia de la variable [Servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html), versión 3.3 o superior. Se basa en el [!DNL ID Service] para activar sincronizaciones de ID y destinos URL. Se produce un error si la variable [!DNL ID Service] falta, es antiguo o no está configurado.
>
>Le recomendamos que use [!DNL Adobe Experience Platform Tags] para implementar y administrar su [!DNL DIL] y [!DNL Adobe Experience Platform Identity Service] bibliotecas.

Sin embargo, también puede descargar el Experience Cloud más reciente y [!DNL DIL] versiones desde nuestra página de GitHub. Consulte los vínculos de descarga siguientes:

* Descargue el [Servicio de identidad de Adobe Experience Platform](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Descargar [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Objetivo del DIL {#purpose-dil}

[!UICONTROL DIL] es una biblioteca de API. Puede pensarlo como un cuerpo de código de ayuda para [!DNL Adobe Audience Manager]. No es necesario utilizar [!DNL Audience Manager], pero los métodos y funciones [!UICONTROL DIL] significa que no tiene que desarrollar su propio código para enviar datos a [!DNL Audience Manager]. Además, [!UICONTROL DIL] es diferente a la API proporcionada por el [Servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html). Ese servicio está diseñado para administrar la identidad de los visitantes entre diferentes [!DNL Experience Cloud] soluciones. Por el contrario, [!UICONTROL DIL] está diseñado para:

* Realizar llamadas de evento y enviar datos a [Servidor de recopilación de datos](../reference/system-components/components-data-collection.md).
* Enviar datos a [destinos](../features/destinations/destinations.md).

## Obtención e implementación del código del DIL {#get-implement-dil-code}

[!UICONTROL DIL] el código está disponible para su descarga **[here](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Tenga en cuenta que a partir de la versión 8.0 (publicada en agosto de 2018), [!UICONTROL DIL] tiene una fuerte dependencia de la variable [Servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html), versión 3.3 o superior. Se basa en el [!DNL ID Service] para activar sincronizaciones de ID y [!DNL URL destinations]. Se produce un error si la variable [!DNL ID Service] falta, es antiguo o no está configurado.

En lugar de trabajar con [!UICONTROL DIL] y configurar [!DNL Audience Manager] manualmente, le recomendamos que utilice [Etiquetas de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) en su lugar. [!DNL Adobe Experience Platform Tags] es la herramienta de implementación recomendada porque simplifica la implementación, la colocación y la administración de versiones del código. Obtenga más información sobre [Extensión de Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) en [!DNL Adobe Experience Platform Tags].

## Ejemplo de llamada {#sample-code}

[!UICONTROL DIL] envía datos a [!DNL Audience Manager] en una llamada de evento. Una llamada de evento es una solicitud HTTP XML de la página. Utiliza un `POST` para enviar datos en el cuerpo de la solicitud.

| Elemento Llamada de evento | Descripción |
|--- |--- |
| URL | Las llamadas de evento de DIL utilizan la siguiente sintaxis: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Cuerpo | Como se muestra en el ejemplo siguiente, el DIL pasa los datos como pares clave-valor. Los caracteres de prefijo especial identifican los pares clave-valor como variables de Audience Manager o socio.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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
