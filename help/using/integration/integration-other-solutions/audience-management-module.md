---
description: Añada el módulo Gestión de público al AppMeasurement de Adobe Analytics para reenviar datos de Analytics al Audience Manager en lugar de hacer que el código de Data Integration Library del Audience Manager (DIL) envíe un píxel desde la página.
keywords: audience analytics; analytics; ssf; reenvío del lado del servidor
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: Implementación del módulo Gestión de público
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 1%

---

# Reenviar datos de [!DNL Adobe Analytics] a [!DNL Audience Manager] {#implement-the-audience-management-module}

Siga los pasos de este tutorial para reenviar los datos de [!DNL Analytics] a [!DNL Audience Manager] en lugar de hacer que el código de [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) envíe un píxel desde la página.

>[!TIP]
>
>Le recomendamos que use [!DNL Adobe Experience Platform Tags] para reenviar datos de [!UICONTROL Analytics] a [!DNL Audience Manager]. Al usar [!UICONTROL Tags], no tiene que copiar código manualmente en [!DNL AppMeasurement], como se muestra en esta página.

## Requisitos previos {#prereqs}

Además de habilitar las extensiones o implementar el código descrito en este documento, también debe hacer lo siguiente:

* Implemente el [servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html).
* Habilite el [reenvío del lado del servidor](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) para los grupos de informes en [!UICONTROL Adobe Analytics Admin Console].

## Implementación {#implementation}

Existen dos métodos para implementar el reenvío de datos de [!DNL Adobe Analytics] a [!DNL Audience Manager], según la solución de administración de etiquetas que utilice.

### Implementación mediante [!DNL Adobe Experience Platform Tags]

[!DNL Adobe] recomienda usar la extensión [Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) para instrumentar [!DNL Adobe Analytics] y [!DNL Audience Manager] en sus propiedades. En este caso, no es necesario copiar manualmente ningún código. En su lugar, debe habilitar el uso compartido de datos en la extensión [!DNL Analytics], como se muestra en la imagen siguiente. Consulte también la documentación de [Adobe Analytics Extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html#adobe-audience-manager).

>[!TIP]
>
>Si instala la extensión [!DNL Adobe Analytics], *no* instale también la extensión [!DNL Audience Manager]. El reenvío de datos desde la extensión [!DNL Analytics] reemplaza la funcionalidad de extensión [!DNL Audience Manager].

![Cómo habilitar el uso compartido de datos desde la extensión de Adobe Analytics al Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## Elementos de código definidos {#code-elements-defined}

La siguiente tabla define variables importantes en el ejemplo de código.

| Parámetro | Descripción |
|--- |--- |
| `partner` | Requerido. Este es un nombre de socio asignado a usted por [!DNL Adobe]. A veces se denomina [!UICONTROL partner ID] o subdominio de socio.  Póngase en contacto con su asesor de [!DNL Adobe] o con [Atención al cliente](https://helpx.adobe.com/es/marketing-cloud/contact-support.html) si no conoce el nombre de su socio. |
| `containerNSID` | Requerido. La mayoría de los clientes solo pueden establecer `"containerNSID":0` Sin embargo, si su empresa necesita personalizar las sincronizaciones de ID con un contenedor diferente, puede especificar ese ID de contenedor aquí. |
| `uuidCookie` | Opcional. Esta configuración le permite establecer una cookie [!DNL Adobe] en el dominio de origen. Este(a) [!DNL cookie] contiene el [UUID](../../reference/ids-in-aam.md) |
| `visitorService` - `namespace` | Requerido. El parámetro `namespace` es necesario si usa el módulo [!DNL AudienceManagement] empaquetado con [!UICONTROL AppMeasurement] versión 2.10 o posterior. Este módulo de [!UICONTROL AudienceManagement] requiere que use [!UICONTROL Adobe Experience Platform Identity Service] 3.3 o posterior. <br><br>El [!UICONTROL Experience Cloud Organization ID] es el identificador que se proporciona a una compañía al registrarse en [!UICONTROL Experience Cloud]. Descubra el identificador de organización de su compañía en [Organizaciones y vinculación de cuentas](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html). |

## Resultados: Reenvío de datos a [!DNL Audience Manager] {#results-data-forwarding}

Su implementación de [!DNL Analytics] envía datos a [!DNL Audience Manager] después de que usted haya:

* Habilitó [!UICONTROL Server-Side Forwarding] (hable con su consultor sobre esta característica);
* Implementó [!DNL Adobe Experience Platform Identity Service];
* Se han seguido los pasos de implementación de este tutorial.

Este proceso envía datos a [!DNL Audience Manager]:

* En llamadas de vista de página;
* A partir de vínculos rastreados;
* Desde las vistas de vídeo de Milestone y Heartbeat.

>[!NOTE]
>
>Las variables enviadas a [!DNL Audience Manager] desde [!DNL Analytics] utilizan prefijos especiales. Debe comprender y tener en cuenta estos prefijos al crear [!DNL Audience Manager] rasgos. Para obtener más información acerca de estos prefijos, vea [Requisitos de prefijo para variables clave](../../features/traits/trait-variable-prefixes.md).
