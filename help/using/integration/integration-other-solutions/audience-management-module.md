---
description: Añada el módulo de administración de Audiencias a Adobe Analytics AppMeasurement para reenviar datos de Analytics al Audience Manager en lugar de hacer que el código de Data Integration Library del Audience Manager (DIL) envíe un píxel desde la página.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Añada el módulo de administración de Audiencias a Adobe Analytics AppMeasurement para reenviar datos de Analytics al Audience Manager en lugar de hacer que el código de Data Integration Library del Audience Manager (DIL) envíe un píxel desde la página.
seo-title: Implementar el módulo de administración de Audiencias
solution: Audience Manager
title: Implementar el módulo de administración de Audiencias
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Integration with Analytics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 5%

---


# Cómo reenviar datos de [!DNL Adobe Analytics] a [!DNL Audience Manager] {#implement-the-audience-management-module}

Siga los pasos de este tutorial para reenviar [!DNL Analytics] datos a [!DNL Audience Manager] en lugar de hacer que el código [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) envíe un píxel desde la página.

>[!TIP]
>
>Le recomendamos que utilice [!DNL Adobe Experience Platform Launch] para reenviar [!UICONTROL Analytics] datos a [!DNL Audience Manager]. Al utilizar [!UICONTROL Launch], no es necesario copiar código manualmente en [!DNL AppMeasurement], como se muestra en esta página.

## Requisitos previos {#prereqs}

Además de habilitar las extensiones o implementar el código descrito en este documento, también debe:

* Implementar el [servicio de identidad de Adobe Experience Platform](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html).
* Habilite [Reenvío del lado del servidor](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) para grupos de informes en [!UICONTROL Adobe Analytics Admin Console].

## Implementación {#implementation}

Existen dos métodos para implementar el reenvío de datos de [!DNL Adobe Analytics] a [!DNL Audience Manager], según la solución de administración de etiquetas que utilice.

### Implementación mediante [!DNL Adobe Experience Platform Launch]

[!DNL Adobe] recomienda utilizar la extensión  [](https://docs.adobe.com/content/help/en/launch/using/overview.html) Launchextension para instrumentar  [!DNL Adobe Analytics] y  [!DNL Audience Manager] en sus propiedades. En este caso, no es necesario copiar manualmente ningún código. En su lugar, debe habilitar el uso compartido de datos en la extensión [!DNL Analytics Launch], como se muestra en la siguiente imagen. Consulte también la documentación de [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager).

>[!TIP]
>
>Si instala la extensión [!DNL Adobe Analytics], *no* también instale la extensión [!DNL Audience Manager]. El reenvío de datos desde la extensión [!DNL Analytics] reemplaza la funcionalidad de extensión [!DNL Audience Manager].

![Cómo habilitar el uso compartido de datos desde la extensión Adobe Analytics al Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

### Implementación mediante [!DNL Adobe Digital Tag Management (DTM)] o cualquier otra solución de administración de etiquetas

>[!WARNING]
>
>[!DNL Adobe] ha lanzado los planes de extinción  [!DNL DTM] para finales de 2020. Para obtener más información y programar, consulte [!DNL DTM] Planes para un atardecer en los [foros de la comunidad de Adobe](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset).

Para implementar [!UICONTROL Audience Management Module] mediante [Adobe DTM](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) u otra solución de administración de etiquetas:

1. Descargue [!UICONTROL AppMeasurement] con el [Administrador de códigos de Analytics](https://docs.adobe.com/content/help/es-ES/analytics/admin/admin-tools/code-manager-admin.html) (requiere la versión 1.5 o posterior).
1. Actualice el código [!UICONTROL AppMeasurement] a la versión incluida en el archivo zip descargado.
1. Copie todo el código de `AppMeasurement_Module_AudienceManagement.js` del archivo zip. Pegue el archivo `appMeasurement.js` justo encima del texto, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Añada el código, `s.loadModule("AudienceManagement");`, justo encima del código `AppMeasurement_Module_AudienceManagement.js` que acaba de agregar en el paso anterior.
1. Actualice y copie el código siguiente y agréguelo a la función `doPlugins` del archivo `AppMeasurement.js`.

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
| `partner` | Requerido. Es un nombre de socio que [!DNL Adobe] le asigna. A veces se le denomina subdominio [!UICONTROL partner ID] o de socio.  Póngase en contacto con su [!DNL Adobe] asesor o [Servicio de atención al cliente](https://helpx.adobe.com/es/marketing-cloud/contact-support.html) si no conoce el nombre de su socio. |
| `containerNSID` | Requerido. La mayoría de los clientes puede establecer `"containerNSID":0`. Sin embargo, si la compañía necesita personalizar la sincronización de ID con un contenedor diferente, puede especificar ese ID de contenedor aquí. |
| `uuidCookie` | Opcional. Esta configuración le permite establecer una cookie [!DNL Adobe] en el dominio de origen. Este [!DNL cookie] contiene el [UUID](../../reference/ids-in-aam.md). |
| `visitorService` -  `namespace` | Requerido. El parámetro `namespace` es necesario si utiliza el módulo [!DNL AudienceManagement] incorporado con [!UICONTROL AppMeasurement] versión 2.10 o posterior. Este módulo [!UICONTROL AudienceManagement] requiere que utilice [!UICONTROL Adobe Experience Platform Identity Service] 3.3 o posterior. <br><br>El  [!UICONTROL Experience Cloud Organization ID] es el ID con el que se proporciona una compañía al registrarse para el  [!UICONTROL Experience Cloud]. Descubra el identificador de organización de su compañía en [Organizaciones y vinculación de cuentas](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html). |

## Resultados: Reenvío de datos a [!DNL Audience Manager] {#results-data-forwarding}

Su implementación [!DNL Analytics] envía datos a [!DNL Audience Manager] después de:

* Habilitado [!UICONTROL Server-Side Forwarding] (consulte con su asesor sobre esta función);
* Se implementó el [!DNL Adobe Experience Platform Identity Service];
* Se han seguido los pasos de implementación de este tutorial.

Este proceso envía datos a [!DNL Audience Manager]:

* En llamadas de vista de página;
* Desde vínculos rastreados;
* Desde vistas de vídeo de hito de vídeo y latidos.

>[!NOTE]
>
>Las variables enviadas a [!DNL Audience Manager] desde [!DNL Analytics] utilizan prefijos especiales. Debe comprender y tener en cuenta estos prefijos al crear características [!DNL Audience Manager]. Para obtener más información sobre estos prefijos, consulte [Requisitos de prefijo para variables clave](../../features/traits/trait-variable-prefixes.md).
