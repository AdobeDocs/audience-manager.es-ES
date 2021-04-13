---
description: Agregue el módulo Gestión de público a AppMeasurement de Adobe Analytics para reenviar datos de Analytics al Audience Manager en lugar de hacer que el código de Data Integration Library de Audience Manager (DIL) envíe un píxel desde la página.
keywords: audience analytics; analytics; ssf; reenvío del lado del servidor
seo-description: Agregue el módulo Gestión de público a AppMeasurement de Adobe Analytics para reenviar datos de Analytics al Audience Manager en lugar de hacer que el código de Data Integration Library de Audience Manager (DIL) envíe un píxel desde la página.
seo-title: Implementación del módulo Gestión de público
solution: Audience Manager
title: Implementación del módulo Gestión de público
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Integración de Adobe Analytics
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 5%

---

# Reenviar datos de [!DNL Adobe Analytics] a [!DNL Audience Manager] {#implement-the-audience-management-module}

Siga los pasos de este tutorial para reenviar datos [!DNL Analytics] a [!DNL Audience Manager] en lugar de hacer que el código [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) envíe un píxel desde la página.

>[!TIP]
>
>Se recomienda utilizar [!DNL Adobe Experience Platform Launch] para reenviar [!UICONTROL Analytics] datos a [!DNL Audience Manager]. Al utilizar [!UICONTROL Launch], no es necesario copiar manualmente el código en [!DNL AppMeasurement], como se muestra en esta página.

## Requisitos previos {#prereqs}

Además de habilitar las extensiones o implementar el código descrito en este documento, también debe:

* Implemente el [Servicio de identidad de Adobe Experience Platform](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html).
* Habilite [Reenvío del lado del servidor](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) para los grupos de informes en [!UICONTROL Adobe Analytics Admin Console].

## Implementación {#implementation}

Existen dos métodos para implementar el reenvío de datos de [!DNL Adobe Analytics] a [!DNL Audience Manager], según la solución de administración de etiquetas que utilice.

### Implementación mediante [!DNL Adobe Experience Platform Launch]

[!DNL Adobe] recomienda utilizar la extensión de  [](https://docs.adobe.com/content/help/en/launch/using/overview.html) Launch para instrumentar  [!DNL Adobe Analytics] y  [!DNL Audience Manager] en sus propiedades. En este caso, no es necesario copiar manualmente ningún código. En su lugar, debe habilitar el uso compartido de datos en la extensión [!DNL Analytics Launch] , como se muestra en la imagen siguiente. Consulte también la documentación de [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager).

>[!TIP]
>
>Si instala la extensión [!DNL Adobe Analytics], *do not* también instala la extensión [!DNL Audience Manager]. El reenvío de datos desde la extensión [!DNL Analytics] reemplaza la funcionalidad de extensión [!DNL Audience Manager].

![Habilitación del uso compartido de datos desde la extensión de Adobe Analytics al Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

### Implementación mediante [!DNL Adobe Digital Tag Management (DTM)] o cualquier otra solución de administración de etiquetas

>[!WARNING]
>
>[!DNL Adobe] ha anunciado que planea la puesta  [!DNL DTM] en marcha a finales de 2020. Para obtener más información y programar, consulte [!DNL DTM] Planes para un ocaso en los [foros de la comunidad de Adobe](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset).

Para implementar [!UICONTROL Audience Management Module] mediante [Adobe DTM](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) u otra solución de administración de etiquetas:

1. Descargue [!UICONTROL AppMeasurement] mediante el [Administrador de códigos de Analytics](https://docs.adobe.com/content/help/es-ES/analytics/admin/admin-tools/code-manager-admin.html) (requiere la versión 1.5 o posterior).
1. Actualice el código [!UICONTROL AppMeasurement] a la versión incluida en el archivo zip descargado.
1. Copie todo el código desde `AppMeasurement_Module_AudienceManagement.js` desde el archivo zip. Péguelo en el archivo `appMeasurement.js` justo encima del texto, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Agregue el código, `s.loadModule("AudienceManagement");`, justo encima del código `AppMeasurement_Module_AudienceManagement.js` que acaba de agregar en el paso anterior.
1. Actualice y copie el código siguiente y agréguelo a la función `doPlugins` en su archivo `AppMeasurement.js`.

```js
s.AudienceManagement.setup({ 
     "partner":"INSERT-YOUR-PARTNER-NAME-HERE", 
     "containerNSID":0, 
     "uuidCookie": { 
          "name":"aam_uuid", 
          "days":30
     },
     "visitorService": {
          "namespace": "INSERT-EXPERIENCE-CLOUD-ORGID-HERE" 
     } 
});
```

>[!TIP]
>
>La función `audienceManagement.setup` comparte parámetros con la función [!DNL Audience Manager] `DIL.create`, que puede configurar en este código. Para obtener más información sobre estos parámetros, consulte [Creación de DIL](../../dil/dil-class-overview/dil-create.md#dil-create).

## Elementos de código definidos {#code-elements-defined}

La siguiente tabla define variables importantes en el ejemplo de código.

| Parámetro | Descripción |
|--- |--- |
| `partner` | Requerido. Es un nombre de socio que [!DNL Adobe] le asigna. A veces se denomina subdominio de [!UICONTROL partner ID] o socio.  Póngase en contacto con su asesor de [!DNL Adobe] o [Servicio de atención al cliente](https://helpx.adobe.com/es/marketing-cloud/contact-support.html) si no conoce el nombre de su socio. |
| `containerNSID` | Requerido. La mayoría de los clientes solo pueden configurar `"containerNSID":0` . Sin embargo, si su empresa necesita personalizar las sincronizaciones de ID con un contenedor diferente, puede especificar ese ID de contenedor aquí. |
| `uuidCookie` | Opcional. Esta configuración le permite establecer una cookie [!DNL Adobe] en el dominio de origen. Este [!DNL cookie] contiene el [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` -  `namespace` | Requerido. El parámetro `namespace` es necesario si utiliza el módulo [!DNL AudienceManagement] incluido con la versión 2.10 o posterior de [!UICONTROL AppMeasurement]. Este módulo [!UICONTROL AudienceManagement] requiere que utilice [!UICONTROL Adobe Experience Platform Identity Service] 3.3 o posterior. <br><br>El  [!UICONTROL Experience Cloud Organization ID] es el ID que se proporciona a una empresa al registrarse en  [!UICONTROL Experience Cloud]. Descubra el identificador de organización de su empresa en [Organizaciones y vinculación de cuentas](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html). |

## Resultados: Reenvío de datos a [!DNL Audience Manager] {#results-data-forwarding}

Su implementación [!DNL Analytics] envía datos a [!DNL Audience Manager] después de:

* Habilitado [!UICONTROL Server-Side Forwarding] (póngase en contacto con su asesor sobre esta función);
* Se ha implementado el [!DNL Adobe Experience Platform Identity Service];
* Seguimos los pasos de implementación de este tutorial.

Este proceso envía datos a [!DNL Audience Manager]:

* En las llamadas de vista de página;
* Desde vínculos rastreados;
* A partir de las vistas de vídeo de hito y latido.

>[!NOTE]
>
>Las variables enviadas a [!DNL Audience Manager] desde [!DNL Analytics] utilizan prefijos especiales. Debe comprender y tener en cuenta estos prefijos al crear características [!DNL Audience Manager]. Para obtener más información sobre estos prefijos, consulte [Requisitos de prefijo para variables clave](../../features/traits/trait-variable-prefixes.md).
