---
description: Agregue el módulo Gestión de público a AppMeasurement de Adobe Analytics para reenviar datos de Analytics a Audience Manager en lugar de hacer que el código DIL (Biblioteca de integración de datos de Audience Manager) envíe un píxel desde la página.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Agregue el módulo Gestión de público a AppMeasurement de Adobe Analytics para reenviar datos de Analytics a Audience Manager en lugar de hacer que el código DIL (Biblioteca de integración de datos de Audience Manager) envíe un píxel desde la página.
seo-title: Implementar el módulo Gestión de público
solution: Audience Manager
title: Implementar el módulo Gestión de público
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Cómo reenviar datos de Adobe Analytics a Audience Manager {#implement-the-audience-management-module}

Siga los pasos de este tutorial para reenviar [!DNL Analytics] datos a Audience Manager en lugar de hacer que el código de Audience Manager [!UICONTROL Data Integration Library] ([!UICONTROL DIL]) envíe un píxel desde la página.

>[!TIP]
>
>Le recomendamos que utilice [!DNL Adobe Experience Platform Launch] para reenviar [!UICONTROL Analytics] datos a Audience Manager. Al usar [!UICONTROL Launch], no es necesario copiar el código manualmente en [!UICONTROL AppMeasurement], como se muestra en esta página.

## Requisitos previos {#prereqs}

Además de habilitar las extensiones o implementar el código descrito en este documento, también debe:

* Implemente el servicio [de identidad de la plataforma de](https://marketing.adobe.com/resources/help/en_US/mcvid/)Adobe Experience.
* Habilite el reenvío [del lado del](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) servidor para los grupos de informes en la [!UICONTROL Adobe Analytics Admin Console].

## Implementación {#implementation}

Existen dos métodos para implementar el reenvío de datos de Adobe Analytics a Audience Manager, según la solución de administración de etiquetas que utilice.

### Implementación mediante Adobe Experience Platform Launch

Adobe recomienda utilizar la extensión [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) para instrumentar Adobe Analytics y Audience Manager en sus propiedades. En este caso, no es necesario copiar manualmente ningún código. En su lugar, debe habilitar el uso compartido de datos en la extensión de inicio de Analytics, como se muestra en la siguiente imagen. Consulte también la documentación de [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) .

>[!TIP]
>
>Si instala la extensión de Adobe Analytics, *no instale* también la extensión de Audience Manager. El reenvío de datos desde la extensión Analytics sustituye a la funcionalidad de extensión de Audience Manager.

![Cómo habilitar el uso compartido de datos desde la extensión Adobe Analytics a Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

### Implementación mediante Adobe Digital Tag Management (DTM) o cualquier otra solución de administración de etiquetas


>[!WARNING]
>
>Adobe ha lanzado los planes para dejar de utilizar la DTM a finales de 2020. Para obtener más información y programar, consulte Planes de DTM para un atardecer en los foros [de la comunidad de](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset)Adobe.

Para implementar el [!UICONTROL Audience Management Module] uso de [Adobe DTM](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) u otra solución de administración de etiquetas:

1. Descargue [!UICONTROL AppMeasurement] mediante el Administrador [de códigos](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) de Analytics (requiere la versión 1.5 o posterior).
1. Actualice su [!UICONTROL AppMeasurement] código a la versión incluida en el archivo zip descargado.
1. Copie todo el código desde `AppMeasurement_Module_AudienceManagement.js` el archivo zip. Pegue el archivo en el `appMeasurement.js` archivo justo encima del texto, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Agregue el código, `s.loadModule("AudienceManagement");`, justo encima del `AppMeasurement_Module_AudienceManagement.js` código que acaba de agregar en el paso anterior.
1. Actualice y copie el código siguiente y agréguelo a la `doPlugins` función del `AppMeasurement.js` archivo.

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
>La `audienceManagement.setup` función comparte parámetros con la función Audience Manager `DIL.create` , que puede configurar en este código. Para obtener más información sobre estos parámetros, consulte [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

## Elementos de código definidos {#code-elements-defined}

La siguiente tabla define variables importantes en el ejemplo de código.

| Parámetro | Descripción |
|--- |--- |
| `partner` | Requerido. Es un nombre de socio que Adobe le asigna. A veces se le denomina &quot;ID de socio&quot; o &quot;subdominio de socio&quot;.  Póngase en contacto con su asesor de Adobe o con el Servicio de atención [al cliente](https://helpx.adobe.com/marketing-cloud/contact-support.html) si no conoce el nombre de su socio. |
| `containerNSID` | Requerido. La mayoría de los clientes pueden establecer `"containerNSID":0` . Sin embargo, si su empresa necesita personalizar la sincronización de ID con un contenedor diferente, puede especificar ese ID de contenedor aquí. |
| `uuidCookie` | Opcional. Esta configuración le permite establecer una cookie de Adobe en el dominio de origen. Esta cookie contiene el [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Requerido. El `namespace` parámetro es obligatorio si utiliza el módulo AudienceManagement incluido con [!UICONTROL AppMeasurement] la versión 2.10 o posterior. Este [!UICONTROL AudienceManagement] módulo requiere que utilice [!UICONTROL Adobe Experience Platform Identity Service] 3.3 o posterior. <br> El [!UICONTROL Experience Cloud Organization ID] es el ID que se proporciona a una empresa al registrarse para el [!UICONTROL Experience Cloud]. Descubra el identificador de organización de su empresa en [Organizaciones y vinculación](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)de cuentas. |

## Resultados: Reenvío de datos a Audience Manager {#results-data-forwarding}

La [!DNL Analytics] implementación envía datos a Audience Manager después de:

* Habilitado [!UICONTROL Server-Side Forwarding] (consulte con su asesor sobre esta función);
* Se ha implementado el servicio de identidad de Adobe Experience Platform;
* Se han seguido los pasos de implementación de este tutorial.

Este proceso envía datos a [!DNL Audience Manager]:

* En las llamadas de vista de página;
* Desde vínculos rastreados;
* Desde las vistas de vídeo de hito y latido.

>[!NOTE]
>
>Las variables enviadas a Audience Manager desde [!DNL Analytics] utilizan prefijos especiales. Debe comprender y tener en cuenta estos prefijos al crear características de Audience Manager. Para obtener más información sobre estos prefijos, consulte Requisitos de [prefijo para variables](../../features/traits/trait-variable-prefixes.md)clave.