---
description: Agregue el módulo Gestión de público a Adobe Analytics appmeasurement para reenviar datos de Analytics a Audience Manager en lugar de tener un código de biblioteca de integración de datos (DIL) de Audience Manager que envíe un píxel desde la página.
keywords: audience analytics; analytics; ssf; reenvío de servidor
seo-description: Agregue el módulo Gestión de público a Adobe Analytics appmeasurement para reenviar datos de Analytics a Audience Manager en lugar de tener un código de biblioteca de integración de datos (DIL) de Audience Manager que envíe un píxel desde la página.
seo-title: Implementación del módulo Gestión de público
solution: Audience Manager
title: Implementación del módulo Gestión de público
uuid: 08846427-def 3-4 a 15-88 e 5-08882 d 8 d 57 ce
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Implement the Audience Management Module {#implement-the-audience-management-module}

Add the [!UICONTROL Audience Management Module] to [!DNL Adobe Analytics] [!UICONTROL AppMeasurement] to forward [!DNL Analytics] data to Audience Manager instead of having the Audience Manager [!UICONTROL Data Integration Library] ([!UICONTROL DIL]) code send a pixel from the page.

## Requisitos previos {#prereqs}

Además de implementar el código descrito en este documento, también debe:

* Implement the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* Enable [!UICONTROL Server-Side Forwarding] for report suites in the [!UICONTROL Adobe Analytics Admin Console].

## Implementación {#implementation}

To implement the [!UICONTROL Audience Management Module]:

1. Download [!UICONTROL AppMeasurement] using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) (requires version 1.5 or later).
1. Update your [!UICONTROL AppMeasurement] code to the version included in the downloaded zip file.
1. Copy all of the code from `AppMeasurement_Module_AudienceManagement.js` from the zip file. Paste it into the `appMeasurement.js` file just above the text, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Add the code, `s.loadModule("AudienceManagement");`, just above the `AppMeasurement_Module_AudienceManagement.js` code you just added in the previous step.
1. Update and copy the code below and add it to the `doPlugins` function in your `AppMeasurement.js` file.

```js
s.AudienceManagement.setup({ 
     "partner":"partner name", 
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
>The `audienceManagement.setup` function shares parameters with the Audience Manager `DIL.create` function, which you can configure in this code. For more information about these parameters, see [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

## Code Elements Defined {#code-elements-defined}

La tabla siguiente define las variables importantes en la muestra de código.

| Parámetro | Descripción |
|--- |--- |
| `partner` | Requerido. Es un nombre asociado que Adobe le asigna. A veces se denomina «ID de socio» o «subdominio asociado». Contact your Adobe consultant or [Customer Care](https://helpx.adobe.com/marketing-cloud/contact-support.html) if you don't know your partner name. |
| `containerNSID` | Requerido. Most customers can just set  `"containerNSID":0` . Sin embargo, si su empresa necesita personalizar sincronizaciones de ID con otro contenedor, puede especificar ese ID de contenedor aquí. |
| `uuidCookie` | Opcional. Esta configuración permite establecer una cookie de Adobe en el dominio de origen. This cookie contains the [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Requerido. The `namespace` parameter is required if you use the AudienceManagement module bundled with [!UICONTROL AppMeasurement] version 2.10 or newer. This [!UICONTROL AudienceManagement] module requires that you use [!UICONTROL Experience Cloud ID Service] 3.3 or newer. <br>Es [!UICONTROL Experience Cloud Organization ID] el ID con el que se proporciona una empresa al registrarse para [!UICONTROL Experience Cloud]. Find out your company's Organization ID in [Organizations and Account Linking](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html). |

## Results: Data Forwarding to Audience Manager {#results-data-forwarding}

[!DNL Analytics] La implementación envía datos a Audience Manager una vez que haya:

* Enabled [!UICONTROL Server-Side Forwarding] (talk to your consultant about this feature);
* Se ha implementado el servicio de ID;
* Installed the [!UICONTROL Audience Management Module].

This process sends data to [!DNL Audience Manager]:

* En las llamadas de vista de página;
* Desde vínculos rastreados;
* Desde las vistas de vídeo de hitos de vídeo y de latidos.

>[!NOTE]
>
>The variables sent to Audience Manager from [!DNL Analytics] use special prefixes. Debe comprender y tener en cuenta estos prefijos al crear características de Audience Manager. For more information on these prefixes, see [Prefix Requirements for Key Variables](../../features/traits/trait-variable-prefixes.md).