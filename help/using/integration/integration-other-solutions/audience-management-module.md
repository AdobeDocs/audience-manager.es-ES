---
description: Agregue el módulo Gestión de público a AppMeasurement de Adobe Analytics para reenviar datos de Analytics al Audience Manager en lugar de hacer que el código de Data Integration Library de Audience Manager (DIL) envíe un píxel desde la página.
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
source-wordcount: '492'
ht-degree: 2%

---

# Reenviar datos desde [!DNL Adobe Analytics] a [!DNL Audience Manager] {#implement-the-audience-management-module}

Siga los pasos de este tutorial para avanzar [!DNL Analytics] datos a [!DNL Audience Manager] en lugar de tener la variable [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) el código envía un píxel desde la página.

>[!TIP]
>
>Le recomendamos que use [!DNL Adobe Experience Platform Tags] para reenviar [!UICONTROL Analytics] datos en [!DNL Audience Manager]. Usando [!UICONTROL Tags], no es necesario copiar manualmente el código en [!DNL AppMeasurement], tal y como se muestra en esta página.

## Requisitos previos {#prereqs}

Además de habilitar las extensiones o implementar el código descrito en este documento, también debe:

* Implementación de [Servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html).
* Habilitar [Reenvío del lado del servidor](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) para grupos de informes en la variable [!UICONTROL Adobe Analytics Admin Console].

## Implementación {#implementation}

Existen dos métodos para implementar el reenvío de datos desde [!DNL Adobe Analytics] a [!DNL Audience Manager], según la solución de administración de etiquetas que utilice.

### Implementación mediante [!DNL Adobe Experience Platform Tags]

[!DNL Adobe] recomienda usar la variable [Etiquetas](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) extensión al instrumento [!DNL Adobe Analytics] y [!DNL Audience Manager] en sus propiedades. En este caso, no es necesario copiar manualmente ningún código. En su lugar, debe habilitar el uso compartido de datos en la variable [!DNL Analytics] como se muestra en la imagen siguiente. Consulte también la [Extensión de Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html#adobe-audience-manager) documentación.

>[!TIP]
>
>Si instala la variable [!DNL Adobe Analytics] extensión, *no* también instale el [!DNL Audience Manager] extensión. Reenvío de datos desde el [!DNL Analytics] reemplaza a la función [!DNL Audience Manager] funcionalidad de extensión.

![Habilitación del uso compartido de datos desde la extensión de Adobe Analytics al Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## Elementos de código definidos {#code-elements-defined}

La siguiente tabla define variables importantes en el ejemplo de código.

| Parámetro | Descripción |
|--- |--- |
| `partner` | Requerido. Es un nombre de socio que le ha asignado [!DNL Adobe]. A veces se denomina [!UICONTROL partner ID] o subdominio de socio.  Póngase en contacto con su [!DNL Adobe] consultor o [Servicio de atención al cliente](https://helpx.adobe.com/es/marketing-cloud/contact-support.html) si no conoce su nombre de socio. |
| `containerNSID` | Requerido. La mayoría de los clientes pueden configurar  `"containerNSID":0` . Sin embargo, si su empresa necesita personalizar las sincronizaciones de ID con un contenedor diferente, puede especificar ese ID de contenedor aquí. |
| `uuidCookie` | Opcional. Esta configuración le permite establecer una [!DNL Adobe] en el dominio de origen. Esta [!DNL cookie] contiene el [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Requerido. La variable `namespace` es obligatorio si utiliza la variable [!DNL AudienceManagement] módulo empaquetado con [!UICONTROL AppMeasurement] versión 2.10 o posterior. Esta [!UICONTROL AudienceManagement] requiere que utilice [!UICONTROL Adobe Experience Platform Identity Service] 3.3 o posterior. <br><br>La variable [!UICONTROL Experience Cloud Organization ID] es el ID con el que se proporciona a una empresa al registrarse para el [!UICONTROL Experience Cloud]. Descubra el identificador de organización de su empresa en [Organizaciones y vinculación de cuentas](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html). |

## Resultados: Reenvío de datos a [!DNL Audience Manager] {#results-data-forwarding}

Su [!DNL Analytics] la implementación envía datos a [!DNL Audience Manager] después de:

* Habilitado [!UICONTROL Server-Side Forwarding] (póngase en contacto con su asesor sobre esta función);
* Se ha implementado el [!DNL Adobe Experience Platform Identity Service];
* Seguimos los pasos de implementación de este tutorial.

Este proceso envía datos a [!DNL Audience Manager]:

* En las llamadas de vista de página;
* Desde vínculos rastreados;
* A partir de las vistas de vídeo de hito y latido.

>[!NOTE]
>
>Las variables enviadas a [!DNL Audience Manager] from [!DNL Analytics] utilice prefijos especiales. Debe comprender y tener en cuenta estos prefijos al crear [!DNL Audience Manager] características. Para obtener más información sobre estos prefijos, consulte [Requisitos de prefijo para variables clave](../../features/traits/trait-variable-prefixes.md).
